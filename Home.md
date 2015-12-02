# **Welcome to the Instagram PHP wiki!**
![wiki](http://s1.postimg.org/gkr9ivfzj/cutmypic.png)
--
| **Instagram Legal** | **Setup Guide** | **Technical Documentation** |
| ------------- | ------------- | ------------- | 
| ![legal](https://github.com/snowplow/snowplow/wiki/images/help.png)| ![setup](https://github.com/snowplow/snowplow/wiki/images/tools.png) | ![technical](https://github.com/snowplow/snowplow/wiki/images/database.png) | ![commit](https://github.com/snowplow/snowplow/wiki/images/users.png)
|  [Instagram EULA](https://help.instagram.com/478745558852511)  | [Dependencies](https://github.com/mgp25/Instagram-API/wiki/Dependencies) | [Technical info.](https://github.com/mgp25/Instagram-API/wiki/Technical-information) 
| Instagram Legal also known as EULA. Contains all terms and conditions. | All the things you need to make Instagram PHP works | Detailed technical documentation about how WhatsApp works.|

### Constructor

- `$username`:   Instagram's username
- `$password`:   Instagram's password
- `$debug`:      Debug mode (Optional)
- `$IGDataPath`: Custom data storage path (Optional)

```php
$insta = new Instagram($username, $password);
```

```php
$insta = new Instagram($username, $password, $debug = false, $IGDataPath = null);
```

### Functions 

**Notes:** 
`$usernameId` is not the username, it's an id (numeric)

All data returned it's an array object

---

- `login()`
- `logout()`
- `uploadPhoto($photo, $caption = null)`
- `editMedia($mediaId, $captionText = "")`
- `changeProfilePicture($photo)`
- `removeProfilePicture()`
- `setPrivateAccount()`
- `setPublicAccount()`
- `getUsernameInfo($usernameId)`
- `getSelfUsernameInfo()`
- `getRecentActivity()`
- `getv2Inbox()`
- `getUserTags($usernameId)`
- `getSelfUserTags()`
- `getGeoMedia($usernameId)`
- `getSelfGeoMedia()`
- `fbUserSearch($query)`
- `searchUsers($query)`
- `searchTags($query)`
- `getTimeline()`
- `getUserFeed($usernameId)`
- `getSelfUserFeed()`
- `getPopularFeed()`
- `getUserFollowers($usernameId)`
- `getSelfUserFollowers()`
- `getUsersFollowing()`
- `like($mediaId)`
- `unlike($mediaId)`
- `getMediaComments($mediaId)`
- `setNameAndPhone($name = "", $phone = "")`
- `getDirectShare()`
- `backup()`
- `follow($userId)`
- `unfollow($userId)`
- `block($userId)`
- `unblock($userId)`
- `getLikedMedia()`