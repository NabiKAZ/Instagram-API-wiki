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

### **Full API documentation [HERE](https://github.com/mgp25/Instagram-API/wiki/API-Documentation#interface-instagramapiexceptioninstagramexception)**

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