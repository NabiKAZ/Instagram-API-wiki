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
    * [Response Objects](#response-objects)
    * [Setting a proxy](#setting-a-proxy)
    * [Pagination](#pagination)
  * **[Media functions](#media-functions)**
    * [Uploading photos](#uploading-photos)
    * [Uploading video](#uploading-video)
    * [Uploading media to Stories](#uploading-media-to-stories)
    * [Uploading an album](#uploading-an-album)
    * [Edit media](#edit-media)
    * [Liking media](#liking-media)
    * [All media functions](#all-media-functions)
  * **[Direct messaging and sharing](#direct-messaging-and-sharing)**
	* [Sharing media](#sharing-media)
	* [Sending text message or link](#sending-text-message-or-link)
	* [All Direct functions](#all-direct-functions)
  * **[Interacting with users](#interacting-with-users)**
	* [Follow and Unfollow](#follow-and-unfollow)
	* [Getting followers](#getting-followers)
	* [All functions to interact with users](#all-functions-to-interact-with-users)
  * **[More functions](#more-functions)** 



## Constructor

- `$debug`:         Boolean. Debug mode (Optional)
- `$truncatedDebug`:Boolean. Truncates Instagram's responses to 1000 chars in debug log  (Optional)
- `$storageConfig`: Configuration for the desired user settings storage backend. (Optional)

```php
$ig = new \InstagramAPI\Instagram($debug, $truncatedDebug, $storageConfig = []);
```

If you want to use a mySQL storage:

```php
$ig = new \InstagramAPI\Instagram(true, true, [
	'storage'    => 'mysql',
	'dbhost'     => 'localhost',
	'dbname'     => 'mydatabase',
	'dbusername' => 'root',
	'dbpassword' => '',
]);
```

## Login

Once you have initialized the InstagramAPI class, you must login to an account. 

```php
$ig->login($username, $password); // Will resume if a previous session exists.
```

Your sessions will be stored a `sessions/username/` folder by default, if you're using the file-based settings backend. If you set use other custom settings path, a username folder will be created under it. By default, the hierarchy is as follows:

```
Instagram-API
|-- src
|-- sessions 
|    |-- username
|    |    |-- username-cookies.dat
|    |    |-- username-settings.dat
```

- `username-cookies.dat` contains the cookies for your session.
- `username-settings.dat` contains important information about your account.

Both files are generated automatically by the API.

If you want to manage more accounts at once, you can switch accounts by calling `login()` with the new account:

```php
$ig->login($username, $password);
```

## Two Factor Login

If you have an account with two factor authentication enabled, you need to login this way:

```php
    $loginResponse = $ig->login($username, $password);

    if (!is_null($loginResponse) && $loginResponse->isTwoFactorRequired()) {
        $twoFactorIdentifier = $loginResponse->getTwoFactorInfo()->getTwoFactorIdentifier();

         // The "STDIN" lets you paste the code via terminal for testing.
         // You should replace this line with the logic you want.
         // The verification code will be sent by Instagram via SMS.
        $verificationCode = trim(fgets(STDIN));
        $ig->finishTwoFactorLogin($verificationCode, $twoFactorIdentifier);
    }
```

Example: [twoFactorLogin.php](https://github.com/mgp25/Instagram-API/blob/master/examples/twoFactorLogin.php)

## Username ID

As you can see while using the API, most of the functions require a param called `$userId`. This is a string that represents Instagram's unique, internal id for that username. For example:

`MyUsername` ---> `1959226924`

If you don't know how to obtain this id, don't worry about it, you can use `getUserIdForName()`.

```php
$userId = $ig->people->getUserIdForName('MyUsername');
```

`$userId` now contains `1959226924`

## Managing responses

When you do a request, you can obtain all the information very easily since all responses are objects, for example:

```php
$response = $ig->people->getInfoById($userId);
echo $response->getUser()->getUsername(); // this will print username of user with id $userId 
```

You can find all responses and their object-functions [here](https://github.com/mgp25/Instagram-API/tree/master/src/Response). Note that no objects have any defined functions. The functions are auto-created based on the object properties. For example a property `$username` can be read via `getUsername()`, and a property `$carousel_media` can be read via `getCarouselMedia()`. The list of auto-defined functions is `getX`, `setX`, and `isX`, where `X` is the name of an object property.

## Response Objects

Many people assume we are the ones building the objects/their values. We are _not_! It all comes from the Instagram server. `NULL` in a field means the Instagram server did not send any value for that field.

Most objects we have are re-used for lots of different responses, and most server responses do not fill every field. So just because people see something like for example a `$view_count` field on an object does not mean it _will_ be filled with anything. Most server responses only fill 30% of all available object fields!

We do not control what the server will send you! Missing `NULL` fields is totally normal!

## Setting a proxy

**Note:** Using proxies in the API works fine, so if you don't get any response it's because Instagram's server is refusing to connect with the proxy (or because the proxy doesn't work).

```php
// HTTP proxy needing authentication.
$ig->setProxy('http://user:pass@iporhost:port');

// HTTP proxy without authentication.
$ig->setProxy('http://iporhost:port');

// Encrypted HTTPS proxy needing authentication.
$ig->setProxy('https://user:pass@iporhost:port');

// Encrypted HTTPS proxy without authentication.
$ig->setProxy('https://iporhost:port');

// SOCKS5 Proxy needing authentication:
$ig->setProxy('socks5://user:pass@iporhost:port');

// SOCKS5 Proxy without authentication:
$ig->setProxy('socks5://iporhost:port');
```

The full list of proxy protocols is available in [the cURL documentation](https://curl.haxx.se/libcurl/c/CURLOPT_PROXY.html).

## Pagination

Everytime we scroll down in our devices to load more data (followers, photos, conversations...), that's called pagination.

When you get Instagram's response, it may contain a `next_max_id` key, which means there is more data you can load. In order to paginate, you will have to pass that param to the function. Here is an example:

```php
    $maxId = null;
    do {
        $response = $ig->getSelfUserFollowers($maxId);
        $followers = array_merge($followers, $response->getUsers());
        $maxId = $response->getNextMaxId();
    } while ($maxId !== null);
```

Example: [PaginationExample.php](https://github.com/mgp25/Instagram-API/blob/master/examples/paginationExample.php)


## Media functions

### Uploading photos

`$photoFile` is the path to the photo. ie: `/desktop/cat.jpg`

```php
$metadata = [
              'caption' => 'My awesome caption',
              'location' => $location, // $location must be an instance of /Model/Location class
            ];

// if you want only a caption, you can simply do this:
$metadata = ['caption' => 'My awesome caption'];

$ig->timeline->uploadPhoto($photoFilename, $metadata);
```

Example: [uploadPhoto.php](https://github.com/mgp25/Instagram-API/blob/master/examples/uploadPhoto.php)

### Uploading video

```php
$ig->timeline->uploadVideo($videoFile, $metadata);
```

Example: [uploadVideo.php](https://github.com/mgp25/Instagram-API/blob/master/examples/uploadVideo.php)

### Uploading media to Stories

You can upload both photos and videos to Stories.

```php

$metadata = [
    'hashtags' => [
        // Note that you can add more than one hashtag in this array.
        [
            'tag_name'         => 'test', // NOTE: This hashtag MUST appear in the caption (it does NOT include the '#' here).
            'x'                => 0.5, // Range: 0.0 - 1.0
            'y'                => 0.5, // Note that x = 0.5 and y = 0.5 is center of screen.
            'width'            => 0.24305555, // Percentage: 0.0 - 1.0
            'height'           => 0.07347973, // Percentage: 0.0 - 1.0
            'rotation'         => 0.0,
            'is_sticker'       => false, // Don't change this value.
            'use_custom_title' => false, // Don't change this value.
        ],
        // ...
    ],
    'caption' => '#test This is a great API!',
];

$ig->story->uploadPhoto($photoFilename, $metadata);
```

Same thing can be done with videos:

```php
$ig->story->uploadVideo($videoFile, $metadata);
```

**Note 1:** Adding a hashtag creates a link to the specified position, but the text overlay MUST be added by the user (You can use GD, PhotoShop or other image processing software for this).

**Note 2:** ONLY if you have a bussiness account, you can use links in stories. If that is the case, you can use the `link` key  in `$metadata` to add a link, i.e:
 
```php
$metadata = 
	[
		'link' => $url
	];

$ig->story->uploadPhoto($photoFilename, $metadata);
```


Example: [uploadStory.php](https://github.com/mgp25/Instagram-API/blob/master/examples/uploadStory.php)

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
        /* TAGS COMMENTED OUT UNTIL YOU READ THE BELOW:
        'usertags' => [ // Optional, lets you tag one or more users in a PHOTO.
            [
                'position' => [0.5, 0.5],
                // WARNING: THE USER ID MUST BE VALID. INSTAGRAM WILL VERIFY IT
                // AND IF IT'S WRONG THEY WILL SAY "media configure error".
                'user_id'  => '123456789', // Must be a numerical UserPK ID.
            ],
        ],
        */
    ],
    [
        'type'     => 'video',
        'file'     => '', // Path to the video file.
    ],
];

$captionText = '';

$ig->timeline->uploadAlbum(($media, ['caption' => $captionText]);
```

Example: [uploadAlbum.php](https://github.com/mgp25/Instagram-API/blob/master/examples/uploadAlbum.php)


### Edit media

If you want to add user tags, put them in the `in` array. If you want to remove a user from the media, add them to `removed` instead.

```php
$metadata = 
    [
        'usertags' => 
            [
                'removed' => [],
                'in'      => 
                    [
                        'position' => 
                            [
                                0.47097720202318, // x position
                                0.46537839732884  // y position
                            ],
                            'user_id'  => 
                                [
                                    $userId
                                ]
                    ]
            ]
    ];

$ig->media->edit($mediaId, $captionText, $metadata);
```

You can also add a `Location` or change the caption with this function. In case you want to delete the location, you can send an empty `Location` object.

### Liking media

If you want to like a media from your timeline, you can easily do:

#### (Default module) Liking from timeline feed

```php
$ig->media->like($mediaId);
```

If you are in another place performing this action, you need to set `$module` value and depending the module, it could require some extra data:

#### Liking from the explore tab

```php
$module = 'feed_contextual_post';
$extraData = ['explore_source_token' => $exploreToken];

$ig->media->like($mediaId, $module, $extraData);
```

#### Liking from an user profile

Depending on the media, modules can be:

```
media_view_profile - for carousels
photo_view_profile - for photos (the only one currently supported)
video_view_profile - for videos
```

```php
$extraData = ['username' => $username, 'user_id' => $userId];
$ig->media->like($mediaId, $module, $extraData);
```

#### Linking from hashtag search


```php
$module = 'feed_contextual_hashtag';
$extraData = ['hashtag' => $hashtag];

$ig->media->like($mediaId, $module, $extraData);
```

#### Liking from place search


```php
$module = 'feed_contextual_location';
$extraData = ['location_id' => $locationId];

$ig->media->like($mediaId, $module, $extraData);
```

#### Liking from the followings activity feed

If the user only liked one post ("xyz liked abc's post"), then the app uses module `newsfeed`.
If the user liked multiple posts ("xyz liked 5 posts"), then the app uses module `feed_contextual_newsfeed_multi_media_liked`.

No extra data is required.

**Reference:** [Issue #1602](https://github.com/mgp25/Instagram-API/issues/1602)
         

### All media functions

All media functions can be found in the following classes:

- [Media.php](https://github.com/mgp25/Instagram-API/blob/master/src/Request/Media.php)
- [Story.php](https://github.com/mgp25/Instagram-API/blob/master/src/Request/Story.php)
- [Timeline.php](https://github.com/mgp25/Instagram-API/blob/master/src/Request/Timeline.php)
- [Live.php](https://github.com/mgp25/Instagram-API/blob/master/src/Request/Live.php)

## Instagram Direct

Instagram Direct lets you exchange threaded messages with one or more people, and share posts you see in Feed as a message.

### Sharing media

```php
$ig->direct->sendPost($recipients, $mediaId);
```

To start a new thread, provide "users" as an array of numerical UserPK IDs. To use an existing thread instead, provide "thread" with the thread ID.

```php
//New thread
$recipients = 
	[
		'users' => $userIds // must be an [array] of valid UserPK IDs
	];

//Use an existing thread
 $recipients = 
	[
		'thread' => $threadId // must be a single, valid thread ID
	];
```

### Sending text message or link

```php
$ig->direct->sendText($recipients, $text);
```

If `$text` contains a link, it will be processed and sent as a link.


### All Direct functions

All Direct functions can be found in the following class:

- [Direct.php](https://github.com/mgp25/Instagram-API/blob/master/src/Request/Direct.php)


## Interacting with users

### Follow and Unfollow

```php
$ig->people->follow($userId);

$ig->people->unfollow($userId);
```

### Getting followers

```php
$ig->people->getFollowers($userId);
```

### All functions to interact with users

All functions to interact with users can be found in the following class:

- [People.php](https://github.com/mgp25/Instagram-API/blob/master/src/Request/People.php)

## More functions

All requests have now been organized into collections of related functions, which makes them much easier to find. Instead of painfully searching through hundreds of functions in the "huge main class" to find what you're looking for, you now simply have to look for the specific collection that seems to be the most likely one for your needs. And when we grouped all of these functions, we also took the opportunity to rename many of them to much cleaner, easier and more logical names! For example, if you now want to find hashtags, you would simply look in the Hashtag collection (`src/Request/Hashtag.php`), and there you would find the search() function, and your final function call would be `$ig->hashtag->search()`, which is very easy and clear to read. You can find all of the function groups [here](https://github.com/mgp25/Instagram-API/tree/master/src/Request).