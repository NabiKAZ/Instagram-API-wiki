#Frequently Asked Question

- [My photos/videos are removed just after upload](#my-photosvideos-are-removed-just-after-upload)
- [Uploading videos doesnt work](#uploading-videos-doesnt-work)
- [How to extract Instagram Signature Key](#how-to-extract-instagram-signature-key)
- [Instagram has changed my password](#instagram-has-changed-my-password)
- [Instagram registration doesn't work](#instagram-registration-doesnt-work)
- [How to get all the users im following?](#how-to-get-all-the-users-im-following)
- [Are you going to add video view increment?](#are-you-going-to-add-video-view-increment)
- [How can i capture requests?](#how-can-i-capture-requests)

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
