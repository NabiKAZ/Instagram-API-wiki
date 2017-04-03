# **Welcome to the Instagram PHP wiki!**
![wiki](http://s1.postimg.org/gkr9ivfzj/cutmypic.png)
--
| **Instagram Legal** | **Setup Guide** | **Technical Documentation** |
| ------------- | ------------- | ------------- | 
| ![legal](https://github.com/snowplow/snowplow/wiki/images/help.png)| ![setup](https://github.com/snowplow/snowplow/wiki/images/tools.png) | ![technical](https://github.com/snowplow/snowplow/wiki/images/database.png) | ![commit](https://github.com/snowplow/snowplow/wiki/images/users.png)
|  [Instagram EULA](https://help.instagram.com/478745558852511)  | [Dependencies](https://github.com/mgp25/Instagram-API/wiki/Dependencies) | [Technical info.](https://github.com/mgp25/Instagram-API/wiki/Technical-information) 
| Instagram Legal also known as EULA. Contains all terms and conditions. | All the things you need to make Instagram PHP works | Detailed technical documentation about how Instagram works.|

***

**Frequently Asked Questions:** [F.A.Q.](https://github.com/mgp25/Instagram-API/wiki/FAQ)

Here is explained basic concepts about how to use the API. All documentation about what a function does and what it returns, and other info, can be found in the code `Instagram.php`. Also check out the [F.A.Q.](https://github.com/mgp25/Instagram-API/wiki/FAQ) before opening a new issue.

***

* **[Instagram API Documentation]()**
  * **[Getting started]()**
    * [Constructor](#constructor)
    * [Login](#login)
    * [Two Factor Login](#two-factor-login)
    * [Username ID](#username-id)
    * [Managing responses](#managing-responses)
    * [Setting a proxy](#setting-a-proxy)
    * [Pagination](#pagination)
  * **[Some media functions](#uploading-media)**
    * [Uploading photos](#uploading-photos)
    * [Uploading video](#uploading-video)
    * [Uploading media to Stories](#uploading-media-to-stories)
    * [Uploading an album](#uploading-an-album)
    * [Adding tags to a media](#adding-tags-to-a-media)


## Constructor

- `$debug`:         Boolean. Debug mode (Optional)
- `$truncatedDebug`:Boolean. Truncates Instagram's responses to 1000 chars in debug log  (Optional)
- `$storageConfig`: Configuration for the desired user settings storage backend. (Optional)

```php
$i = new \InstagramAPI\Instagram($debug, $truncatedDebug, $storageConfig = []);
```

If you want to use a mySQL storage:

```php
$i = new Instagram(true, true, [
	"storage"      => "mysql",
	"dbhost"       => Config::get('myconfig.DB_HOST'),
	"dbname"   => Config::get('myconfig.DB_DATABASE'),
	"dbusername"   => Config::get('myconfig.DB_USERNAME'),
	"dbpassword"   => Config::get('myconfig.DB_PASSWORD'),
]);
```

## Login

Once you have initialized InstagramAPI class, you can login:
```php
$i->setUser($username, $password);
$i->login();
```

Your session will be stored in `data/username` folder. If you have set any other custom data path, a `data` folder will be created inside it.

```
InstagramAPI
|-- src
|-- sessions 
|    |-- username
|    |    |-- username-cookies.dat
|    |    |-- settings-username.dat
```

- `username-cookies.dat` contains your session.
- `settings-username.dat` contains essential information for the API about your account.

Both files are generated automatically by the API.

If you want to manage more accounts at once, you can switch accounts using this:

```php
$i->setUser($user2, $passwd2);
```

## Two Factor Login

If you have an account with two factor authentication enabled, you need to login this way:

```php
    $ig->setUser($username, $password);
    $loginResponse = $ig->login();

    if (!is_null($loginResponse) && $loginResponse->getTwoFactorRequired()) {
        $twoFactorIdentifier = $loginResponse->getTwoFactorInfo()->getTwoFactorIdentifier();

         // I added this line so i could write in the code in CLI.
         // You can replace this line with the logic you want.
         // Verification code will be received via SMS.
        $verificationCode = trim(fgets(STDIN));
        $ig->twoFactorLogin($verificationCode, $twoFactorIdentifier);
    }
```
Example: [twoFactorLogin.php](https://github.com/mgp25/Instagram-API/blob/master/examples/twoFactorLogin.php)

## Username ID

As you can see while using the API, most of the function requires a param called `$usernameId`. This is a string that represents a unique id for the username. For example:

`MyUsername` ---> `1959226924`

If you don't know how to obtain this id, don't worry about it, you can use `getUsernameId()`.

```php
$a = $i->getUsernameId('MyUsername');
```

`$a` now contains `1959226924`

## Managing responses

When you do a request, you can obtain all the information easily as all responses are objects, for example:

```php
$a = $i->getUsernameInfo($usernameId);
echo $a->getUsername(); // this will print username of user with id $usernameId 
```

You can find all responses and functions [here](https://github.com/mgp25/Instagram-API/tree/master/src/http/Response).

## Setting a proxy

**Note:** Using proxys in the API works fine, so if you don't get any response it's because Instagram server is refusing to connect with it.

```php
// HTTP proxy needing authentication.
$i->setProxy('http://user:pass@iporhost:port');

// HTTP proxy without authentication.
$i->setProxy('http://iporhost:port');

// Encrypted HTTPS proxy needing authentication.
$i->setProxy('https://user:pass@iporhost:port');

// Encrypted HTTPS proxy without authentication.
$i->setProxy('https://iporhost:port');
```

## Pagination

Everytime we scroll down in our devices to load more data(followers, photos, conversations...), that's called pagination.

When you get Instagram's response, it could contain a `next_max_id` key, that means there are more data you can load. In order to paginate, you will have to pass that param to the function. Here is an example:

```php
    $maxId = null;
    do {
        $response = $ig->getSelfUserFollowers($maxId);
        $followers = array_merge($followers, $response->getUsers());
        $maxId = $response->getNextMaxId();
    } while ($maxId !== null);
```

Example: [PaginationExample.php](https://github.com/mgp25/Instagram-API/blob/master/examples/PaginationExample.php)

## Uploading media

### Uploading photos
`uploadTimelinePhoto($photoFile, $metadata)`

`$photoFile` is the path to the photo. ie: `/desktop/cat.jpg`

```php
$metadata = [
              'caption' => 'My awesome caption',
              'location' => $location, // $location must be an instance of Location class
            ];

// if you want only a caption, you can simply do this:

$metadata = ['caption' => 'My awesome caption'];

$i->uploadTimelinePhoto($photoFile, $metadata);
```

### Uploading video
`uploadTimelineVideo($videoFile, $metadata)`

```php
$i->uploadTimelineVideo($videoFile, $metadata);
```

### Uploading media to Stories

`uploadStoryPhoto($photoFile, $metadata)`

`$photoFile` is the path to the photo. ie: `/desktop/cat.jpg`

```php
$metadata = ['caption' => 'My awesome caption'];

$i->uploadStoryPhoto($photoFile, $metadata);
```

Same thing can be done with videos:

```php
$i->uploadStoryVideo($videoFile, $metadata);
```

### Uploading an album

```php
$media = [ // Albums can contain between 2 and 10 photos/videos.
    [
        'type'     => 'photo',
        'file'     => '', // Path to the photo file.
    ],
    [
        'type'     => 'photo',
        'file'     => '', // Path to the photo file.
    ],
    [
        'type'     => 'video',
        'file'     => '', // Path to the video file.
    ],
];

$ig->uploadTimelineAlbum($media, ['caption' => $captionText]);
```

Example: [uploadAlbum.php](https://github.com/mgp25/Instagram-API/blob/master/examples/uploadAlbum.php)


## Adding tags to a media

If you want to remove any user from a media, add them to `removed`.

```php
$captionText = 'This is a test';
$userTags = [
              'removed' => [
                           ],
              'in'      => [
                             'position' => [
                                              0.47097720202318, // x position
                                              0.46537839732884  // y position
                                           ],
                             'user_id'  => [
                                              $userId
                                           ]
                           ]
            ];
$userTags = json_encode($userTags);

$ig->editMedia($mediaId, $captionText, $userTags);
```

## Functions 

**Note:** Not all functions are listed here 

```
  [0]=>
  string(11) "__construct"
  [1]=>
  string(7) "setUser"
  [2]=>
  string(12) "setVerifySSL"
  [3]=>
  string(12) "getVerifySSL"
  [4]=>
  string(8) "setProxy"
  [5]=>
  string(8) "getProxy"
  [6]=>
  string(18) "setOutputInterface"
  [7]=>
  string(18) "getOutputInterface"
  [8]=>
  string(19) "_getSignupChallenge"
  [9]=>
  string(5) "login"
  [10]=>
  string(14) "twoFactorLogin"
  [11]=>
  string(14) "_sendLoginFlow"
  [12]=>
  string(6) "logout"
  [13]=>
  string(16) "requestTwoFactor"
  [14]=>
  string(15) "enableTwoFactor"
  [15]=>
  string(16) "disableTwoFactor"
  [16]=>
  string(22) "getAccountSecurityInfo"
  [17]=>
  string(12) "syncFeatures"
  [18]=>
  string(23) "getAutoCompleteUserList"
  [19]=>
  string(12) "pushRegister"
  [20]=>
  string(14) "getFacebookOTA"
  [21]=>
  string(15) "getTimelineFeed"
  [22]=>
  string(11) "getInsights"
  [23]=>
  string(16) "getMediaInsights"
  [24]=>
  string(15) "getMegaphoneLog"
  [25]=>
  string(15) "getPendingInbox"
  [26]=>
  string(14) "getVisualInbox"
  [27]=>
  string(19) "getRankedRecipients"
  [28]=>
  string(19) "getRecentRecipients"
  [29]=>
  string(10) "getExplore"
  [30]=>
  string(19) "getDiscoverChannels"
  [31]=>
  string(18) "getDiscoverTopLive"
  [32]=>
  string(16) "getTopLiveStatus"
  [33]=>
  string(6) "expose"
  [34]=>
  string(11) "directShare"
  [35]=>
  string(13) "directMessage"
  [36]=>
  string(11) "directPhoto"
  [37]=>
  string(12) "directThread"
  [38]=>
  string(18) "directThreadAction"
  [39]=>
  string(18) "_uploadSinglePhoto"
  [40]=>
  string(19) "uploadTimelinePhoto"
  [41]=>
  string(16) "uploadStoryPhoto"
  [42]=>
  string(18) "_uploadSingleVideo"
  [43]=>
  string(19) "uploadTimelineVideo"
  [44]=>
  string(16) "uploadStoryVideo"
  [45]=>
  string(19) "uploadTimelineAlbum"
  [46]=>
  string(20) "configureSinglePhoto"
  [47]=>
  string(31) "configureSingleVideoWithRetries"
  [48]=>
  string(20) "configureSingleVideo"
  [49]=>
  string(33) "configureTimelineAlbumWithRetries"
  [50]=>
  string(22) "configureTimelineAlbum"
  [51]=>
  string(9) "editMedia"
  [52]=>
  string(7) "tagUser"
  [53]=>
  string(9) "untagUser"
  [54]=>
  string(9) "saveMedia"
  [55]=>
  string(11) "unsaveMedia"
  [56]=>
  string(12) "getSavedFeed"
  [57]=>
  string(13) "removeSelfTag"
  [58]=>
  string(12) "getMediaInfo"
  [59]=>
  string(16) "getBroadcastInfo"
  [60]=>
  string(35) "getBroadcastHeartbeatAndViewerCount"
  [61]=>
  string(11) "deleteMedia"
  [62]=>
  string(20) "disableMediaComments"
  [63]=>
  string(19) "enableMediaComments"
  [64]=>
  string(7) "comment"
  [65]=>
  string(16) "commentBroadcast"
  [66]=>
  string(13) "deleteComment"
  [67]=>
  string(14) "deleteComments"
  [68]=>
  string(11) "likeComment"
  [69]=>
  string(13) "unlikeComment"
  [70]=>
  string(20) "changeProfilePicture"
  [71]=>
  string(20) "removeProfilePicture"
  [72]=>
  string(17) "setPrivateAccount"
  [73]=>
  string(16) "setPublicAccount"
  [74]=>
  string(14) "getCurrentUser"
  [75]=>
  string(11) "editProfile"
  [76]=>
  string(14) "changePassword"
  [77]=>
  string(17) "getRecentActivity"
  [78]=>
  string(26) "getFollowingRecentActivity"
  [79]=>
  string(10) "getV2Inbox"
  [80]=>
  string(11) "getUserTags"
  [81]=>
  string(15) "getSelfUserTags"
  [82]=>
  string(14) "getMediaLikers"
  [83]=>
  string(13) "searchFBUsers"
  [84]=>
  string(11) "searchUsers"
  [85]=>
  string(19) "searchInAddressBook"
  [86]=>
  string(17) "getUserInfoByName"
  [87]=>
  string(15) "getUserInfoById"
  [88]=>
  string(15) "getSelfUserInfo"
  [89]=>
  string(13) "getUsernameId"
  [90]=>
  string(13) "getTagRelated"
  [91]=>
  string(10) "getTagInfo"
  [92]=>
  string(16) "getReelsTrayFeed"
  [93]=>
  string(20) "getUserReelMediaFeed"
  [94]=>
  string(16) "getUserStoryFeed"
  [95]=>
  string(17) "getReelsMediaFeed"
  [96]=>
  string(11) "getUserFeed"
  [97]=>
  string(15) "getSelfUserFeed"
  [98]=>
  string(11) "getGeoMedia"
  [99]=>
  string(15) "getSelfGeoMedia"
  [100]=>
  string(14) "searchLocation"
  [101]=>
  string(21) "searchRelatedLocation"
  [102]=>
  string(16) "searchFBLocation"
  [103]=>
  string(23) "searchFBLocationByPoint"
  [104]=>
  string(15) "getLocationFeed"
  [105]=>
  string(14) "getPopularFeed"
  [106]=>
  string(14) "getHashtagFeed"
  [107]=>
  string(17) "getUserFollowings"
  [108]=>
  string(16) "getUserFollowers"
  [109]=>
  string(21) "getSelfUsersFollowing"
  [110]=>
  string(20) "getSelfUserFollowers"
  [111]=>
  string(28) "getPendingFriendshipRequests"
  [112]=>
  string(4) "like"
  [113]=>
  string(6) "unlike"
  [114]=>
  string(13) "likeBroadcast"
  [115]=>
  string(21) "getBroadcastLikeCount"
  [116]=>
  string(16) "getMediaComments"
  [117]=>
  string(20) "getBroadcastComments"
  [118]=>
  string(15) "setNameAndPhone"
  [119]=>
  string(14) "getDirectShare"
  [120]=>
  string(6) "backup"
  [121]=>
  string(6) "follow"
  [122]=>
  string(8) "unfollow"
  [123]=>
  string(18) "reportExploreMedia"
  [124]=>
  string(17) "getSuggestedUsers"
  [125]=>
  string(22) "getSuggestedBroadcasts"
  [126]=>
  string(5) "block"
  [127]=>
  string(7) "unblock"
  [128]=>
  string(16) "blockFriendStory"
  [129]=>
  string(18) "unblockFriendStory"
  [130]=>
  string(17) "getUserFriendship"
  [131]=>
  string(18) "getUsersFriendship"
  [132]=>
  string(13) "getLikedMedia"
  [133]=>
  string(10) "searchTags"
  [134]=>
  string(16) "getStickerAssets"
  [135]=>
  string(7) "request"
}
```