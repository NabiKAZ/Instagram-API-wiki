# Frequently Asked Questions

- [What does error code XXX mean?](#what-does-error-code-xxx-mean)
- [Your version of Instagram is out of date](#your-version-of-instagram-is-out-of-date)
- [What does sentry_block error mean?](#what-does-sentry_block-error-mean)
- [My photos/videos are removed just after upload](#my-photosvideos-are-removed-just-after-upload)
- [Uploading videos doesnt work](#uploading-videos-doesnt-work)
- [How to extract Instagram Signature Key](#how-to-extract-instagram-signature-key)
- [Instagram has changed my password](#instagram-has-changed-my-password)
- [Instagram registration doesn't work](#instagram-registration-doesnt-work)
- [How to get all the users im following?](#how-to-get-all-the-users-im-following)
- [Are you going to add video view increment?](#are-you-going-to-add-video-view-increment)
- [How can i capture requests?](#how-can-i-capture-requests)
- [Checkpoint required](#checkpoint-required)
- [Im getting Error 500](#im-getting-error-500)
- [My photo doesnt appear when searching hashtags](#my-photo-doesnt-appear-when-searching-hashtags)
- [New line in comment doesnt work](#new-line-in-comment-doesnt-work)
- [Issue getting media likers](#issue-getting-media-likers)
- [Issue getting followers](#issue-getting-followers)

### What does error code XXX mean?


- **400**: Bad request. Please check the parameters specified.
- **403**: The method requires authentication (web client) or the request has been denied by Instagram.
- **404**: The entity requested is not found (web client) or the endpoint does not exist.
- **429**: Too many requests. You’re making too many calls.

Instagram may also return other 4XX or 5XX codes.

### Your version of Instagram is out of date.

API is using an outdated version or outdated headers. If you get this message with **this API**, open a new issue.

### What does sentry_block error mean?

This is Instagram's response when your account has been banned from the API for detected spam/bot behavior. The website and app will still work, but you will not be able to use that account via this API anymore.

Specifically, "sentry block" means that Instagram has blocked your account's ability to use this PHP API library (and all other reverse-engineered libraries like it), because of either A) spamming or otherwise abusing (such as mass-following) or B) repeatedly and heavily misusing APIs, in a way humans would never call them.

Normal people using this library don't get sentry blocked. Which means that you've had to do something bad to get blocked by Instagram. There is no way to get unblocked.

Stop using the API in whatever way that triggered this response.

### My photos/videos are removed just after upload

In that case, Instagram has flagged your account/IP as spam, try from a different location and remove the cookies inside `data` folder, and do not do spam.

### Uploading videos doesnt work

It works. Make sure the media is compatible (format, size, dimmensions...) and you have `ffmpeg` installed. More info: https://github.com/mgp25/Instagram-API/wiki/Dependencies

### How to extract Instagram Signature Key

It's explained here: https://github.com/mgp25/Instagram-API/wiki/Technical-information

### Instagram has changed my password

When you login from different locations, to avoid someone gets into your account, Instagram does that, its a security measure.

### Instagram registration doesn't work

It works perfectly. If your IP is flagged you won't be able to create any account. If you receive this as response, you were flagged as spam:

```json
 {"status": "fail", "feedback_title": "Signup Error", 
"feedback_message": "Sorry! There\u2019s a problem signing you up right now. 
Please try again later. We restrict certain content and actions to protect our community. 
Tell us if you think we made a mistake.", 
"spam": true, "feedback_action": "report_problem", "feedback_url": 
"repute/report_problem/instagram_signup/", 
"feedback_ignore_label": "OK", "message": "feedback_required", 
"feedback_appeal_label": "Report problem"}
```

### How to get all the users im following?

Check this [example](https://github.com/mgp25/Instagram-API/blob/master/examples/PaginationExample.php), it will show you how to get all followers/followings using pagination.

### Are you going to add video view increment?

**No.**

### How can i capture requests?

You can use any proxy you want. Remember to disable cert pinning. If you have any doubt, search in google.

### checkpoint required

If you get `checkpoint_required` use this script: https://github.com/mgp25/Instagram-API/blob/master/examples/checkpoint.php

Or login to your account using your mobile device, that should fix it.

### Im getting Error 500

This is a server internal error, due to some bad configuration, this is **NOT** an API issue, so don't open any issue related to this. If you use a proxy and you get this error, the proxy could be the problem.

### My photo doesn't appear when searching hashtags

This is a known issue and will be fixed eventually, so don't open issues about this.

### New line in comment doesnt work

See [issue 1118](https://github.com/mgp25/Instagram-API/issues/1118)

### Issue getting media likers

When the media has a lot of likes, only some of the likers will be retrived, the response has a limited likers and **this is a normal behavior, app does the same**

### Issue getting followers

When you try to paginate to get all followers or following of a user, the response could be limited showing only some of the followers / followings, and **this is a normal behavior, app does the same**