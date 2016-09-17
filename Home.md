# **Welcome to the Instagram PHP wiki!**
![wiki](http://s1.postimg.org/gkr9ivfzj/cutmypic.png)
--
| **Instagram Legal** | **Setup Guide** | **Technical Documentation** |
| ------------- | ------------- | ------------- | 
| ![legal](https://github.com/snowplow/snowplow/wiki/images/help.png)| ![setup](https://github.com/snowplow/snowplow/wiki/images/tools.png) | ![technical](https://github.com/snowplow/snowplow/wiki/images/database.png) | ![commit](https://github.com/snowplow/snowplow/wiki/images/users.png)
|  [Instagram EULA](https://help.instagram.com/478745558852511)  | [Dependencies](https://github.com/mgp25/Instagram-API/wiki/Dependencies) | [Technical info.](https://github.com/mgp25/Instagram-API/wiki/Technical-information) 
| Instagram Legal also known as EULA. Contains all terms and conditions. | All the things you need to make Instagram PHP works | Detailed technical documentation about how Instagram works.|

**Frequently Asked Questions:** [F.A.Q.](https://github.com/mgp25/Instagram-API/wiki/FAQ)


## Constructor

- `$username`:      Instagram's username
- `$password`:      Instagram's password
- `$debug`:         Debug mode (Optional)
- `$IGDataPath`:    Custom data storage path (Optional)
- `$truncatedDebug`:Truncates Instagram's responses to 1000 chars in debug log 

```php
$i = new \InstagramAPI\Instagram($username, $password);
```

```php
$i = new \InstagramAPI\Instagram($username, $password, $debug = false, $IGDataPath = null, $truncatedDebug = false);
```

## Login

Once you have initialized InstagramAPI class, you can login:
```php
$i->login();
```

Your session will be stored in `data/username` folder. If you have set any other custom data path, a `data` folder will be created inside it.

```
InstagramAPI
|-- src
|    |-- data 
|    |    |-- username
|    |    |    |-- username-cookies.dat
|    |    |    |-- settings-username.dat
```

- `username-cookies.dat` contains your session.
- `settings-username.dat` contains essential information for the API about your account.

Both files are generated automatically by the API.

If you want to manage more accounts at once, you can switch accounts using this:

```php
$i->setUser($user2, $passwd2);
```

## Username ID

As you can see while using the API, most of the function requires a param called `$usernameId`. This is an integer that represents a unique id for the username. For example:

`MyUsername` ---> `1959226924`

If you don't know how to obtain this id, don't worry about it, i made a function for that: `getUsernameId`

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
$i = new \InstagramAPI\Instagram($username, $password);
$ip = "http://211.63.185.211";
$port = "8080";
$i->setProxy($ip,$port);
```

or
```php
$i = new \InstagramAPI\Instagram($username, $password);
$ip = "http://211.63.185.211:8080";
$i->setProxy($ip);
```

## Pagination

Everytime we scroll down in our devices to load more data(followers, photos, conversations...), that's called pagination.

When you get Instagram's response, it could contain a `next_max_id` key, that means there are more data you can load. In order to paginate, you will have to pass that param to the function. Here is an example:

```php
$a = null;
do{
   if(is_null($a))
         $a = $this->getUserTotalFollowings($usernameId);
   else 
         $a =  $this->getUserTotalFollowings($usernameId, $a->getNextMaxId());
} while(!is_null($a->getNextMaxId()));
```

Example: [PaginationExample.php](https://github.com/mgp25/Instagram-API/blob/master/examples/PaginationExample.php)

## Uploading media

### Uploading photos
`uploadPhoto($photo, $caption = null, $upload_id = null, $customPreview = null, $location = null, $filter = null)`

`$photo` is the path to the photo. ie: `/desktop/cat.jpg`

Keep `$upload_id` as `null`, that is managed automatically by the API.


```php
$i->uploadPhoto($photo, $caption);
```

### Uploading video
`uploadVideo($video, $caption = null, $customPreview = null)`

```php
$i->uploadVideo($photo, $caption);
```

### Uploading photo to Stories
`uploadPhotoStory($photo, $caption = null, $upload_id = null, $customPreview = null)`

`$photo` is the path to the photo. ie: `/desktop/cat.jpg`

Keep `$upload_id` as `null`, that is managed automatically by the API.

```php
$i->uploadPhotoStory($photo, $caption);
```


## Functions 


**Note:** Not all functions are listed here 

- [Login and switch between accounts](#login-and-switch-between-accounts)
- [Upload Photo and video](#upload-photo-and-video)
- [Direct share media to a friend](#direct-share-media-to-a-friend)
- [Edit media (change caption)](#edit-media-change-caption)
- [Remove self tag from a media](#remove-self-tag-from-a-media)
- [Get info of an uploaded media](#get-info-of-an-uploaded-media)
- [Delete photo or video](#delete-photo-or-video)
- [Post/delete a comment in a media](#postdelete-a-comment-in-a-media)
- [Get media comments](#get-media-comments)
- [Set profile picture and delete profile picture](#set-profile-picture-and-delete-profile-picture)
- [Setting private/public account](#setting-privatepublic-account)
- [Get and edit profile data](#get-and-edit-profile-data)
- [Get username info](#get-username-info)
- [Get recent activity (news inbox)](#get-recent-activity-news-inbox)
- [Get recent activity from followed users](#get-recent-activity-from-followed-users)
- [Get user tags](#get-user-tags)
- [Get media likers](#get-media-likers)
- [Get liked media](#get-liked-media)
- [Get Geo media](#get-geo-media)
- [Search users](#search-users)
- [Search users using address book](#search-users-using-address-book)
- [Get timeline](#get-timeline)
- [Get user feed](#fet-user-feed)
- [Search Location](#search-location)
- [Get self and popular feed](#get-self-and-popular-feed)
- [Get Followings / followers](#get-followings--followers)
- [Like/unlike a video or photo](#like-unlike-a-video-or-photo)
- [Backup all your uploaded photos](#backup-all-your-uploaded-photos)
- [Follow / Unfollow](#follow--unfollow)
- [Block/unblock user](#blockunblock-user)

---

### Login and switch between accounts

**Login and logout**

```php
$i->login();
```

I don't recommend logging out.
```php
$i->logout();
```

**Switch account**

```php
$i->setUser($user2, $passwd2);
```

### Upload Photo and video

```php
$i->uploadPhoto($pathToImage, $caption = null);
```

Video requires ffmpeg
```php
$i->uploadVideo($pathToVideo, $caption = null);
```

### Direct share media to a friend

`$media_id` is a id from an already uploaded media
```php
$i->direct_share($media_id, $recipients, $text = null);
```

### Edit media (change caption)

```php
$i->editMedia($mediaId, $captionText = '');
```

### Remove self tag from a media

```php
$i->removeSelftag($mediaId);
```

### Get info of an uploaded media

```php
$i->mediaInfo($mediaId);
```

### Delete photo or video

```php
$i->deleteMedia($mediaId);
```

### Post/delete a comment in a media

```php
$i->comment($mediaId, $commentText);
```

**delete**

```php
$i->deleteComment($mediaId, $commentId);
```

### Get media comments

```php
$i->getMediaComments($mediaId);
```

### Set profile picture and delete profile picture

**Set**

```php
$i->changeProfilePicture($pathToPicture);
```

**Delete**

```php
$i->removeProfilePicture();
```

### Setting private/public account

**Private**

```php
$i->setPrivateAccount();
```

**Public**

```php
$i->setPublicAccount();
```

### Get and edit profile data

**Get profile data**

```php
$i->getProfileData();
```

**Edit profile data**
```php
   * @param string $url
   *   Url - website. "" for nothing
   * @param string $phone
   *   Phone number. "" for nothing
   * @param string $first_name
   *   Name. "" for nothing
   * @param string $email
   *   Email. Required.
   * @param int $gender
   *   Gender. male = 1 , female = 0
```
```php
$i->editProfile($url, $phone, $first_name, $biography, $email, $gender)
```

### Get username info

```php
$i->getUsernameInfo($usernameId);
```

**Get self username info**

```php
$i->getSelfUsernameInfo();
```

### Get recent activity (news inbox)

```php
$i->getRecentActivity();
```

### Get recent activity from followed users

```php
$i->getFollowingRecentActivity();
```

### Get user tags

```php
$i->getUserTags($usernameId);
```

**Get user tags**

```php
$i->getSelfUserTags();
```

**Get tagged media**

```php
$i->tagFeed($tag);
```

**Search tags**

```php
$i->searchTags($query);
```

### Get media likers

```php
$i->getMediaLikers($mediaId);
```

### Get liked media

```php
$i->getLikedMedia();
```

### Get Geo media

```php
$i->getGeoMedia($usernameId);
```

**Get self geomedia**

```php
$i->getSelfGeoMedia();
```

### Search users

```php
$i->searchUsers($query);
```

**Search exact username**

```php
$i->searchUsername($usernameName);
```

### Search users using address book

`$contacts` is an array of contact, each contact has these values: 

- `phone_numbers` which is an array of the numbers the contacts has
- `first_name` Name of the contact (string)
- `email_addresses` array of the mails the contact has

```php
$i->syncFromAdressBook($contacts);
```

### Get timeline

```php
$i->getTimeline();
```

### Get user feed

```php
 $i->getUserFeed($usernameId, $maxid = null, $count = null)
```

**Get hastag feed**

```php
$i->getHashtagFeed($hashtagString, $maxid = null);
```

### Search Location

```php
$i->searchLocation($query);
```

**Get location feed**

```php
$i->getLocationFeed($locationId, $maxid = null);
```

### Get self and popular feed

**Self**

```php
$i->getSelfUserFeed();
```

**Popular**

```php
$i->getPopularFeed();
```

### Get Followings / followers

**Get user followings**

```php
$i->getUserFollowings($usernameId, $maxid = null);
```

**Get user followers**

```php
$i->getUserFollowers($usernameId, $maxid = null);
```

**Get self user followers**

```php
$i->getSelfUserFollowers();
```

**Get self users following**

```php
$i->getSelfUsersFollowing();
```

### Like/unlike a video or photo

```php
$i->like($mediaId);
```

**unlike**

```php
$i->unlike($mediaId);
```

### Backup all your uploaded photos

```php
$i->backup();
```

### Follow / Unfollow

**follow**

```php
$i->follow($userId);
```

**Unfollow**

```php
$i->unfollow($userId);
```

### Block/unblock user

```php
$i->block($userId);
```

**unblock**

```php
$i->unblock($userId);
```