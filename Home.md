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

### **Full API documentation [HERE](https://github.com/mgp25/Instagram-API/wiki/API-Documentation)**

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

Once you have initialized the InstagramAPI class, you must login to an account. Both of these functions must be called every time. They will set the active user and then login or resume an existing session.

```php
$ig->setUser($username, $password);
$ig->login(); // Will resume if a previous session exists.
```

Your sessions will be stored a `sessions/username/` folder by default, if you're using the file-based settings backend. If you set use other custom settings path, a username folder will be created under it. By default, the hierarchy is as follows:

```
vendor
|-- mgp25
|    |-- instagram-php
|    |    |-- sessions
|    |    |    |-- 
InstagramAPI
|-- src
|-- sessions 
|    |-- username
|    |    |-- username-cookies.dat
|    |    |-- username-settings.dat
```

- `username-cookies.dat` contains the cookies for your session.
- `username-settings.dat` contains important information about your account.

Both files are generated automatically by the API.

If you want to manage more accounts at once, you can switch accounts by changing the active user and calling `login()` again:

```php
$ig->setUser($user2, $passwd2);
$ig->login();
```

## Two Factor Login

If you have an account with two factor authentication enabled, you need to login this way:

```php
    $ig->setUser($username, $password);
    $loginResponse = $ig->login();

    if (!is_null($loginResponse) && $loginResponse->getTwoFactorRequired()) {
        $twoFactorIdentifier = $loginResponse->getTwoFactorInfo()->getTwoFactorIdentifier();

         // The "STDIN" lets you paste the code via terminal for testing.
         // You should replace this line with the logic you want.
         // The verification code will be sent by Instagram via SMS.
        $verificationCode = trim(fgets(STDIN));
        $ig->twoFactorLogin($verificationCode, $twoFactorIdentifier);
    }
```

Example: [twoFactorLogin.php](https://github.com/mgp25/Instagram-API/blob/master/examples/twoFactorLogin.php)

## Username ID

As you can see while using the API, most of the functions require a param called `$userId`. This is a string that represents Instagram's unique, internal id for that username. For example:

`MyUsername` ---> `1959226924`

If you don't know how to obtain this id, don't worry about it, you can use `getUsernameId()`.

```php
$userId = $ig->getUsernameId('MyUsername');
```

`$userId` now contains `1959226924`

## Managing responses

When you do a request, you can obtain all the information very easily since all responses are objects, for example:

```php
$a = $ig->getUserInfoById($userId);
echo $a->getUsername(); // this will print username of user with id $userId 
```

You can find all responses and their object-functions [here](https://github.com/mgp25/Instagram-API/tree/master/src/Response). Note that no objects have any defined functions. The functions are auto-created based on the object properties. For example a property `$username` can be read via `getUsername()`, and a property `$carousel_media` can be read via `getCarouselMedia()`. The list of auto-defined functions is `getX`, `setX`, and `isX`, where `X` is the name of an object property.

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

$ig->uploadTimelinePhoto($photoFile, $metadata);
```

### Uploading video
`uploadTimelineVideo($videoFile, $metadata)`

```php
$ig->uploadTimelineVideo($videoFile, $metadata);
```

### Uploading media to Stories

`uploadStoryPhoto($photoFile, $metadata)`

`$photoFile` is the path to the photo. ie: `/desktop/cat.jpg`

```php
$metadata = ['caption' => 'My awesome caption'];

$ig->uploadStoryPhoto($photoFile, $metadata);
```

Same thing can be done with videos:

```php
$ig->uploadStoryVideo($videoFile, $metadata);
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


## Adding usertags to a media

If you want to add user tags, put them in the `in` array. If you want to remove a user from the media, add them to `removed` instead.

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