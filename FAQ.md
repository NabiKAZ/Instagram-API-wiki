# Frequently Asked Questions

- Understanding Responses from Instagram
  - [What do the 4XX HTTP error codes mean?](#what-do-the-4xx-http-error-codes-mean)
  - [What does the 500 HTTP error code mean?](#what-does-the-500-http-error-code-mean)
  - [What does "Your version of Instagram is out of date." mean?](#what-does-your-version-of-instagram-is-out-of-date-mean)
  - [What does "sentry_block" error mean?](#what-does-sentry_block-error-mean)
  - [What does "checkpoint_required" error mean?](#what-does-checkpoint_required-error-mean)

- Unusual Instagram Behaviour
  - [My photos/videos are removed just after upload](#my-photosvideos-are-removed-just-after-upload)
  - [Instagram has changed my password](#instagram-has-changed-my-password)
  - [Uploading videos doesn't work](#uploading-videos-doesnt-work)
  - [I can only see some 'likers'](#i-can-only-see-some-likers)
  - [I can only see some 'followers'](#i-can-only-see-some-followers)


- How To Guides
  - [How do I extract an Instagram Signature Key?](#how-do-i-extract-an-instagram-signature-key)
  - [How do I paginate in API endpoints?](#how-do-i-paginate-in-api-endpoints)
  - [How do I capture requests?](#how-do-i-capture-requests)


- Other Issues

  - [My photo doesn't appear when searching hashtags](#my-photo-doesnt-appear-when-searching-hashtags)
  - [A new-line character in a comment doesn't work](#a-new-line-character-in-a-comment-doesnt-work)
  - [Is it possible to run the Realtime and Push clients in a single script?](#is-it-possible-to-run-the-realtime-and-push-clients-in-a-single-script) 
  - [Will you make the library asynchronous/concurrent?](#will-you-make-the-library-asynchronousconcurrent)
  - [Are you going to add video view increment?](#are-you-going-to-add-video-view-increment)



## Understanding Responses from Instagram

### What do the 4XX HTTP error codes mean?


- **400**: Bad request. Please check the parameters specified.
- **403**: The method requires authentication (web client) or the request has been denied by Instagram.
- **404**: The entity requested is not found (web client) or the endpoint does not exist.
- **429**: Too many requests. You’re making too many calls, too fast.

Instagram may also return other 4XX codes.

### What does the 500 HTTP error code mean?

#### If the "Error 500" is in an Instagram API response:

This is an internal Instagram server error, and is usually temporary. But it is permanent if _you_ are responsible for the error by sending bad data to Instagram.

Note: This is **NOT** an API issue. Please so don't open any issue related to this.

Some causes that have been reported by our users:

  * Uploaded photos must be an acceptable size and shape; they are not resized by the server.
  * EXIF data may cause an uploaded photo to be rejected.
  * Incorrectly configured HTTP proxies may trigger this error.

#### If the "Error 500" happens in a web browser when you host a script that uses this library:

This is a problem with _your_ specific web server configuration.

You are opening the scripts via a web server/web browser, and your web server has disabled error-display, so instead of showing what is wrong with the code/your settings, you get a blank/generic Error 500 HTML page.

We do not recommend running any scripts via a web browser. This library is made for command line usage in a terminal (by running the script like a command line program, as `php yourscript.php`).

However, it is possible to fix your bad web server configuration, by enabling error reporting on the server via either php.ini, or via adding a command like this (if your PHP config allows the `ini_set()` command) to the top of your script (above all other commands):

```php
<?php

ini_set("display_errors", 1);
```

But we still do not recommend running this library via a web browser! Because browsers will terminate the PHP process as soon as the user closes their connection to the page, which means that your script can terminate at any moment. And furthermore, we must waste time logging in to Instagram every time the user refreshes the page, since each page load starts a new script. And there's also risks about concurrent access to a single user account. So we really, _really_ do not recommend running this library via a browser! It's a _very_ bad idea!

Instead, you should run your script as a permanent process, and make it dump data to a database which your regular website reads from. That's the proper architecture system if you want to use this library online!

### What does "Your version of Instagram is out of date." mean?

This error message indicates the API is using an outdated version or outdated headers.

If you get this message with **this API**, please open a new issue.

### What does "sentry_block" error mean?

This is Instagram's response when your account has been banned from the API for detected spam/bot behavior.

The website and app will still work, but you will not be able to use that account via this API anymore. There is no way to get unblocked.

Specifically, "sentry block" means that Instagram has blocked your account's ability to use this PHP API library (and all other reverse-engineered libraries like it), because of either:

  1. Spamming or otherwise abusing (such as mass-following)
  1. Or repeatedly and heavily misusing APIs, in a way humans would never call them.

People using this library like a normal person don't get sentry blocked. Which means that you've had to do something bad to get blocked by Instagram. There is no way to get unblocked.

Stop using the API in whatever way that triggered this response.

### What does "checkpoint_required" error mean?

If you get `checkpoint_required`, it means that Instagram wants you to prove that you are human and that you are the owner of the account. It can easily get triggered if you put your script on a server which is in a country that you don't normally log in from, for example. Simply login to your account via the official website or your mobile device - that should fix it. If you still get the error again, it means Instagram dislikes your server's IP and that you must login to your account via Instagram's website and your server's IP to prove to them that your server's IP is a human.

## Unusual Instagram Behaviour

### My photos/videos are removed just after upload

In this case, Instagram has flagged your account/IP as spam. Try from a different location and remove the cookies inside the `sessions/` folder, and do not spam.

### Instagram has changed my password

When you login from different locations, to avoid someone stealing your account, Instagram may change your password. It's a security measure.

### Uploading videos doesn't work

* Ensure the media is compatible (format, size, dimensions, etc.)
* Ensure you have `ffmpeg` and `ffprobe` installed. See [Dependencies](https://github.com/mgp25/Instagram-API/wiki/Dependencies) for more info.

### I can only see some 'likers'

When the media has a lot of likes, only some of the likers will be retrieved. The response has a limited number of likers.

This is a normal behavior; the Instagram app performs in the same way.

### I can only see some 'followers'

When you try to paginate to get all followers or following of a user, the response could be limited
to show only some of the followers / followings.

This is a normal behavior; the Instagram app performs in the same way.

## How To Guides

### How do I extract an Instagram Signature Key?

It's explained on the [Technical Information](https://github.com/mgp25/Instagram-API/wiki/Technical-information) wiki page.

### How do I paginate in API endpoints?

This [example](https://github.com/mgp25/Instagram-API/blob/master/examples/paginationExample.php) shows how to handle endpoints that use pagination.

### How do I capture requests?

You can use any proxy you want. Remember to disable certificate pinning.

Please don't ask for further assistance here.


## Other Issues

### My photo doesn't appear when searching hashtags

This is a known issue with the API. It's due to Instagram's anti-spam protection. They obviously don't want bad API users to spam a bunch of fake photos on popular hashtags, so they don't allow API uploads to be listed in hashtag feeds.

Please don't open further issues about this.

### A new-line character in a comment doesn't work

See [issue 1118](https://github.com/mgp25/Instagram-API/issues/1118)

### Is it possible to run the Realtime and Push clients in a single script?

Yes. You can run both in the same script. Just attach both to the same EventLoop.

However, note that the real Instagram app only runs Realtime client when in foreground, whereas its Push client is persistent. You may want to emulate that behavior.

There's also another hidden feature: You can create multiple `InstagramAPI\Instagram()` class instances in a single script, and create individual `Realtime`/`Push` clients for each of them, and then attach them all to the same EventLoop to handle multiple accounts in a single script ([see discussion](https://github.com/mgp25/Instagram-API/issues/1582#issuecomment-331618428)). But we leave that up to very advanced programmers and will not provide any assistance with such usage.

### Will you make the library asynchronous/concurrent?

Never. It is an extremely terrible idea, [for a billion different reasons](https://github.com/mgp25/Instagram-API/issues/1584#issuecomment-332202257).

### Are you going to add video view increment?

No.