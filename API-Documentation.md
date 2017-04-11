## Table of contents

- [\InstagramAPI\AutoPropertyHandler](#class-instagramapiautopropertyhandler)
- [\InstagramAPI\Client](#class-instagramapiclient)
- [\InstagramAPI\ClientMiddleware](#class-instagramapiclientmiddleware)
- [\InstagramAPI\Constants](#class-instagramapiconstants)
- [\InstagramAPI\Debug](#class-instagramapidebug)
- [\InstagramAPI\ImageAutoResizer](#class-instagramapiimageautoresizer)
- [\InstagramAPI\Instagram](#class-instagramapiinstagram)
- [\InstagramAPI\InstagramID](#class-instagramapiinstagramid)
- [\InstagramAPI\Request](#class-instagramapirequest)
- [\InstagramAPI\Response](#class-instagramapiresponse)
- [\InstagramAPI\Signatures](#class-instagramapisignatures)
- [\InstagramAPI\Utils](#class-instagramapiutils)
- [\InstagramAPI\Devices\Device](#class-instagramapidevicesdevice)
- [\InstagramAPI\Devices\GoodDevices](#class-instagramapidevicesgooddevices)
- [\InstagramAPI\Devices\UserAgent](#class-instagramapidevicesuseragent)
- [\InstagramAPI\Exception\AccountDisabledException](#class-instagramapiexceptionaccountdisabledexception)
- [\InstagramAPI\Exception\CheckpointRequiredException](#class-instagramapiexceptioncheckpointrequiredexception)
- [\InstagramAPI\Exception\EmptyResponseException](#class-instagramapiexceptionemptyresponseexception)
- [\InstagramAPI\Exception\EndpointException](#class-instagramapiexceptionendpointexception)
- [\InstagramAPI\Exception\FeedbackRequiredException](#class-instagramapiexceptionfeedbackrequiredexception)
- [\InstagramAPI\Exception\ForcedPasswordResetException](#class-instagramapiexceptionforcedpasswordresetexception)
- [\InstagramAPI\Exception\IncorrectPasswordException](#class-instagramapiexceptionincorrectpasswordexception)
- [\InstagramAPI\Exception\InstagramException (interface)](#interface-instagramapiexceptioninstagramexception)
- [\InstagramAPI\Exception\InternalException](#class-instagramapiexceptioninternalexception)
- [\InstagramAPI\Exception\InvalidUserException](#class-instagramapiexceptioninvaliduserexception)
- [\InstagramAPI\Exception\LoginRequiredException](#class-instagramapiexceptionloginrequiredexception)
- [\InstagramAPI\Exception\NetworkException](#class-instagramapiexceptionnetworkexception)
- [\InstagramAPI\Exception\RequestException](#class-instagramapiexceptionrequestexception)
- [\InstagramAPI\Exception\SentryBlockException](#class-instagramapiexceptionsentryblockexception)
- [\InstagramAPI\Exception\ServerMessageThrower](#class-instagramapiexceptionservermessagethrower)
- [\InstagramAPI\Exception\SettingsException](#class-instagramapiexceptionsettingsexception)
- [\InstagramAPI\Exception\ThrottledException](#class-instagramapiexceptionthrottledexception)
- [\InstagramAPI\Exception\UploadFailedException](#class-instagramapiexceptionuploadfailedexception)
- [\InstagramAPI\Response\AccountSecurityInfoResponse](#class-instagramapiresponseaccountsecurityinforesponse)
- [\InstagramAPI\Response\ActivityNewsResponse](#class-instagramapiresponseactivitynewsresponse)
- [\InstagramAPI\Response\AddressBookResponse](#class-instagramapiresponseaddressbookresponse)
- [\InstagramAPI\Response\AutoCompleteUserListResponse](#class-instagramapiresponseautocompleteuserlistresponse)
- [\InstagramAPI\Response\BroadcastCommentsResponse](#class-instagramapiresponsebroadcastcommentsresponse)
- [\InstagramAPI\Response\BroadcastHeartbeatAndViewerCountResponse](#class-instagramapiresponsebroadcastheartbeatandviewercountresponse)
- [\InstagramAPI\Response\BroadcastInfoResponse](#class-instagramapiresponsebroadcastinforesponse)
- [\InstagramAPI\Response\BroadcastLikeCountResponse](#class-instagramapiresponsebroadcastlikecountresponse)
- [\InstagramAPI\Response\BroadcastLikeResponse](#class-instagramapiresponsebroadcastlikeresponse)
- [\InstagramAPI\Response\ChallengeResponse](#class-instagramapiresponsechallengeresponse)
- [\InstagramAPI\Response\ChangePasswordResponse](#class-instagramapiresponsechangepasswordresponse)
- [\InstagramAPI\Response\CommentBroadcastResponse](#class-instagramapiresponsecommentbroadcastresponse)
- [\InstagramAPI\Response\CommentLikeUnlikeResponse](#class-instagramapiresponsecommentlikeunlikeresponse)
- [\InstagramAPI\Response\CommentResponse](#class-instagramapiresponsecommentresponse)
- [\InstagramAPI\Response\ConfigureResponse](#class-instagramapiresponseconfigureresponse)
- [\InstagramAPI\Response\DeleteCommentResponse](#class-instagramapiresponsedeletecommentresponse)
- [\InstagramAPI\Response\DirectShareInboxResponse](#class-instagramapiresponsedirectshareinboxresponse)
- [\InstagramAPI\Response\DirectThreadResponse](#class-instagramapiresponsedirectthreadresponse)
- [\InstagramAPI\Response\DisableTwoFactorResponse](#class-instagramapiresponsedisabletwofactorresponse)
- [\InstagramAPI\Response\DiscoverChannelsResponse](#class-instagramapiresponsediscoverchannelsresponse)
- [\InstagramAPI\Response\DiscoverTopLiveResponse](#class-instagramapiresponsediscovertopliveresponse)
- [\InstagramAPI\Response\EditMediaResponse](#class-instagramapiresponseeditmediaresponse)
- [\InstagramAPI\Response\EnableTwoFactorResponse](#class-instagramapiresponseenabletwofactorresponse)
- [\InstagramAPI\Response\ExploreResponse](#class-instagramapiresponseexploreresponse)
- [\InstagramAPI\Response\ExposeResponse](#class-instagramapiresponseexposeresponse)
- [\InstagramAPI\Response\FacebookOTAResponse](#class-instagramapiresponsefacebookotaresponse)
- [\InstagramAPI\Response\FBLocationResponse](#class-instagramapiresponsefblocationresponse)
- [\InstagramAPI\Response\FBSearchResponse](#class-instagramapiresponsefbsearchresponse)
- [\InstagramAPI\Response\FollowerAndFollowingResponse](#class-instagramapiresponsefollowerandfollowingresponse)
- [\InstagramAPI\Response\FollowingRecentActivityResponse](#class-instagramapiresponsefollowingrecentactivityresponse)
- [\InstagramAPI\Response\FriendshipResponse](#class-instagramapiresponsefriendshipresponse)
- [\InstagramAPI\Response\FriendshipsShowManyResponse](#class-instagramapiresponsefriendshipsshowmanyresponse)
- [\InstagramAPI\Response\GeoMediaResponse](#class-instagramapiresponsegeomediaresponse)
- [\InstagramAPI\Response\InsightsResponse](#class-instagramapiresponseinsightsresponse)
- [\InstagramAPI\Response\LikeFeedResponse](#class-instagramapiresponselikefeedresponse)
- [\InstagramAPI\Response\LocationFeedResponse](#class-instagramapiresponselocationfeedresponse)
- [\InstagramAPI\Response\LocationResponse](#class-instagramapiresponselocationresponse)
- [\InstagramAPI\Response\LoginResponse](#class-instagramapiresponseloginresponse)
- [\InstagramAPI\Response\LogoutResponse](#class-instagramapiresponselogoutresponse)
- [\InstagramAPI\Response\MediaCommentsResponse](#class-instagramapiresponsemediacommentsresponse)
- [\InstagramAPI\Response\MediaDeleteResponse](#class-instagramapiresponsemediadeleteresponse)
- [\InstagramAPI\Response\MediaInfoResponse](#class-instagramapiresponsemediainforesponse)
- [\InstagramAPI\Response\MediaInsightsResponse](#class-instagramapiresponsemediainsightsresponse)
- [\InstagramAPI\Response\MediaLikersResponse](#class-instagramapiresponsemedialikersresponse)
- [\InstagramAPI\Response\MegaphoneLogResponse](#class-instagramapiresponsemegaphonelogresponse)
- [\InstagramAPI\Response\PendingInboxResponse](#class-instagramapiresponsependinginboxresponse)
- [\InstagramAPI\Response\PopularFeedResponse](#class-instagramapiresponsepopularfeedresponse)
- [\InstagramAPI\Response\RankedRecipientsResponse](#class-instagramapiresponserankedrecipientsresponse)
- [\InstagramAPI\Response\RecentRecipientsResponse](#class-instagramapiresponserecentrecipientsresponse)
- [\InstagramAPI\Response\ReelsMediaResponse](#class-instagramapiresponsereelsmediaresponse)
- [\InstagramAPI\Response\ReelsTrayFeedResponse](#class-instagramapiresponsereelstrayfeedresponse)
- [\InstagramAPI\Response\RelatedLocationResponse](#class-instagramapiresponserelatedlocationresponse)
- [\InstagramAPI\Response\ReportExploreMediaResponse](#class-instagramapiresponsereportexploremediaresponse)
- [\InstagramAPI\Response\RequestTwoFactorResponse](#class-instagramapiresponserequesttwofactorresponse)
- [\InstagramAPI\Response\SaveAndUnsaveMedia](#class-instagramapiresponsesaveandunsavemedia)
- [\InstagramAPI\Response\SavedFeedResponse](#class-instagramapiresponsesavedfeedresponse)
- [\InstagramAPI\Response\SearchTagResponse](#class-instagramapiresponsesearchtagresponse)
- [\InstagramAPI\Response\SearchUserResponse](#class-instagramapiresponsesearchuserresponse)
- [\InstagramAPI\Response\SendConfirmEmailResponse](#class-instagramapiresponsesendconfirmemailresponse)
- [\InstagramAPI\Response\StickerAssetsResponse](#class-instagramapiresponsestickerassetsresponse)
- [\InstagramAPI\Response\SuggestedBroadcastsResponse](#class-instagramapiresponsesuggestedbroadcastsresponse)
- [\InstagramAPI\Response\SuggestedUsersResponse](#class-instagramapiresponsesuggestedusersresponse)
- [\InstagramAPI\Response\SyncResponse](#class-instagramapiresponsesyncresponse)
- [\InstagramAPI\Response\TagFeedResponse](#class-instagramapiresponsetagfeedresponse)
- [\InstagramAPI\Response\TagInfoResponse](#class-instagramapiresponsetaginforesponse)
- [\InstagramAPI\Response\TagRelatedResponse](#class-instagramapiresponsetagrelatedresponse)
- [\InstagramAPI\Response\TimelineFeedResponse](#class-instagramapiresponsetimelinefeedresponse)
- [\InstagramAPI\Response\TopLiveStatusResponse](#class-instagramapiresponsetoplivestatusresponse)
- [\InstagramAPI\Response\UploadJobVideoResponse](#class-instagramapiresponseuploadjobvideoresponse)
- [\InstagramAPI\Response\UploadPhotoResponse](#class-instagramapiresponseuploadphotoresponse)
- [\InstagramAPI\Response\UploadVideoResponse](#class-instagramapiresponseuploadvideoresponse)
- [\InstagramAPI\Response\UserFeedResponse](#class-instagramapiresponseuserfeedresponse)
- [\InstagramAPI\Response\UserInfoResponse](#class-instagramapiresponseuserinforesponse)
- [\InstagramAPI\Response\UserStoryFeedResponse](#class-instagramapiresponseuserstoryfeedresponse)
- [\InstagramAPI\Response\UsertagsResponse](#class-instagramapiresponseusertagsresponse)
- [\InstagramAPI\Response\V2InboxResponse](#class-instagramapiresponsev2inboxresponse)
- [\InstagramAPI\Response\VisualInboxResponse](#class-instagramapiresponsevisualinboxresponse)
- [\InstagramAPI\Response\Model\_Message](#class-instagramapiresponsemodel_message)
- [\InstagramAPI\Response\Model\ActionLog](#class-instagramapiresponsemodelactionlog)
- [\InstagramAPI\Response\Model\Args](#class-instagramapiresponsemodelargs)
- [\InstagramAPI\Response\Model\Attribution](#class-instagramapiresponsemodelattribution)
- [\InstagramAPI\Response\Model\Bold](#class-instagramapiresponsemodelbold)
- [\InstagramAPI\Response\Model\Broadcast](#class-instagramapiresponsemodelbroadcast)
- [\InstagramAPI\Response\Model\BroadcastItem](#class-instagramapiresponsemodelbroadcastitem)
- [\InstagramAPI\Response\Model\BroadcastOwner](#class-instagramapiresponsemodelbroadcastowner)
- [\InstagramAPI\Response\Model\BroadcastStatusItem](#class-instagramapiresponsemodelbroadcaststatusitem)
- [\InstagramAPI\Response\Model\Caption](#class-instagramapiresponsemodelcaption)
- [\InstagramAPI\Response\Model\CarouselMedia](#class-instagramapiresponsemodelcarouselmedia)
- [\InstagramAPI\Response\Model\Channel](#class-instagramapiresponsemodelchannel)
- [\InstagramAPI\Response\Model\Comment](#class-instagramapiresponsemodelcomment)
- [\InstagramAPI\Response\Model\Counts](#class-instagramapiresponsemodelcounts)
- [\InstagramAPI\Response\Model\Experiment](#class-instagramapiresponsemodelexperiment)
- [\InstagramAPI\Response\Model\Explore](#class-instagramapiresponsemodelexplore)
- [\InstagramAPI\Response\Model\ExploreItem](#class-instagramapiresponsemodelexploreitem)
- [\InstagramAPI\Response\Model\FeedAysf](#class-instagramapiresponsemodelfeedaysf)
- [\InstagramAPI\Response\Model\FriendshipStatus](#class-instagramapiresponsemodelfriendshipstatus)
- [\InstagramAPI\Response\Model\Gating](#class-instagramapiresponsemodelgating)
- [\InstagramAPI\Response\Model\GeoMedia](#class-instagramapiresponsemodelgeomedia)
- [\InstagramAPI\Response\Model\HdProfilePicUrlInfo](#class-instagramapiresponsemodelhdprofilepicurlinfo)
- [\InstagramAPI\Response\Model\Image_Versions2](#class-instagramapiresponsemodelimage_versions2)
- [\InstagramAPI\Response\Model\In](#class-instagramapiresponsemodelin)
- [\InstagramAPI\Response\Model\Inbox](#class-instagramapiresponsemodelinbox)
- [\InstagramAPI\Response\Model\InlineFollow](#class-instagramapiresponsemodelinlinefollow)
- [\InstagramAPI\Response\Model\Insights](#class-instagramapiresponsemodelinsights)
- [\InstagramAPI\Response\Model\Item](#class-instagramapiresponsemodelitem)
- [\InstagramAPI\Response\Model\Link](#class-instagramapiresponsemodellink)
- [\InstagramAPI\Response\Model\Location](#class-instagramapiresponsemodellocation)
- [\InstagramAPI\Response\Model\LocationItem](#class-instagramapiresponsemodellocationitem)
- [\InstagramAPI\Response\Model\Media](#class-instagramapiresponsemodelmedia)
- [\InstagramAPI\Response\Model\MediaInsights](#class-instagramapiresponsemodelmediainsights)
- [\InstagramAPI\Response\Model\Param](#class-instagramapiresponsemodelparam)
- [\InstagramAPI\Response\Model\PhoneVerificationSettings](#class-instagramapiresponsemodelphoneverificationsettings)
- [\InstagramAPI\Response\Model\Position](#class-instagramapiresponsemodelposition)
- [\InstagramAPI\Response\Model\RankedRecipient](#class-instagramapiresponsemodelrankedrecipient)
- [\InstagramAPI\Response\Model\Reel](#class-instagramapiresponsemodelreel)
- [\InstagramAPI\Response\Model\Related](#class-instagramapiresponsemodelrelated)
- [\InstagramAPI\Response\Model\SavedFeedItem](#class-instagramapiresponsemodelsavedfeeditem)
- [\InstagramAPI\Response\Model\StaticStickers](#class-instagramapiresponsemodelstaticstickers)
- [\InstagramAPI\Response\Model\Stickers](#class-instagramapiresponsemodelstickers)
- [\InstagramAPI\Response\Model\Stories](#class-instagramapiresponsemodelstories)
- [\InstagramAPI\Response\Model\Story](#class-instagramapiresponsemodelstory)
- [\InstagramAPI\Response\Model\StoryLocation](#class-instagramapiresponsemodelstorylocation)
- [\InstagramAPI\Response\Model\Subscription](#class-instagramapiresponsemodelsubscription)
- [\InstagramAPI\Response\Model\SuggestedUsers](#class-instagramapiresponsemodelsuggestedusers)
- [\InstagramAPI\Response\Model\Suggestion](#class-instagramapiresponsemodelsuggestion)
- [\InstagramAPI\Response\Model\Tag](#class-instagramapiresponsemodeltag)
- [\InstagramAPI\Response\Model\Thread](#class-instagramapiresponsemodelthread)
- [\InstagramAPI\Response\Model\ThreadItem](#class-instagramapiresponsemodelthreaditem)
- [\InstagramAPI\Response\Model\ThreadItemMedia](#class-instagramapiresponsemodelthreaditemmedia)
- [\InstagramAPI\Response\Model\ThreadLastSeenAt](#class-instagramapiresponsemodelthreadlastseenat)
- [\InstagramAPI\Response\Model\TopLive](#class-instagramapiresponsemodeltoplive)
- [\InstagramAPI\Response\Model\Tray](#class-instagramapiresponsemodeltray)
- [\InstagramAPI\Response\Model\TwoFactorInfo](#class-instagramapiresponsemodeltwofactorinfo)
- [\InstagramAPI\Response\Model\User](#class-instagramapiresponsemodeluser)
- [\InstagramAPI\Response\Model\Users](#class-instagramapiresponsemodelusers)
- [\InstagramAPI\Response\Model\Usertag](#class-instagramapiresponsemodelusertag)
- [\InstagramAPI\Response\Model\VideoVersions](#class-instagramapiresponsemodelvideoversions)
- [\InstagramAPI\Settings\Factory](#class-instagramapisettingsfactory)
- [\InstagramAPI\Settings\StorageHandler](#class-instagramapisettingsstoragehandler)
- [\InstagramAPI\Settings\StorageInterface (interface)](#interface-instagramapisettingsstorageinterface)
- [\InstagramAPI\Settings\Storage\File](#class-instagramapisettingsstoragefile)
- [\InstagramAPI\Settings\Storage\Memcached](#class-instagramapisettingsstoragememcached)
- [\InstagramAPI\Settings\Storage\MySQL](#class-instagramapisettingsstoragemysql)

---
### Class: \InstagramAPI\AutoPropertyHandler

> Automatic object property handler. By deriving from this base object, it will automatically create virtual "getX()", "setX()" and "isX()" functions for all of your object's properties. This class is intended to handle Instagram's server responses, so all of your object properties must be named the same way as Instagram's standardized var format, which is "$some_value". That object property can then be magically accessed via "getSomeValue()", "setSomeValue()" and "isSomeValue()".

| Visibility | Function |
|:-----------|:---------|
| public | <strong>__call(</strong><em>string</em> <strong>$functionName</strong>, <em>array</em> <strong>$arguments</strong>)</strong> : <em>mixed</em><br /><em>__CALL is invoked when attempting to access missing functions. This handler auto-maps setters and getters for object properties.</em> |
| public static | <strong>explodeCamelCase(</strong><em>string</em> <strong>$inputString</strong>)</strong> : <em>string[]/bool Array with parts if successful, otherwise FALSE.</em><br /><em>Explodes a string on camelcase boundaries. Examples: - "getSome0XThing" => "get", "some0", "x", "thing". - "getSome0xThing" => "get", "some0x", "thing".</em> |

---
### Class: \InstagramAPI\Client

> This class handles core API network communication and file uploads. WARNING TO CONTRIBUTORS: Do NOT build ANY monolithic multi-step functions within this class! Every function here MUST be a tiny, individual unit of work, such as "request upload URL" or "upload data to a URL". NOT "request upload URL, upload data, configure its location, post it to a timeline, call your grandmother and make some tea". Because that would be unmaintainable and would lock us into unmodifiable, bloated behaviors! Such larger multi-step algorithms MUST be implemented in Instagram.php instead, and MUST simply use individual functions from this class to accomplish their larger jobs. Thank you, for not writing spaghetti code! ;-)

| Visibility | Function |
|:-----------|:---------|
| public | <strong>__construct(</strong><em>[\InstagramAPI\Instagram](#class-instagramapiinstagram)</em> <strong>$parent</strong>)</strong> : <em>void</em><br /><em>Constructor.</em> |
| public | <strong>api(</strong><em>string</em> <strong>$endpoint</strong>, <em>array/null</em> <strong>$postData=null</strong>, <em>bool</em> <strong>$needsAuth=true</strong>, <em>bool</em> <strong>$assoc=true</strong>)</strong> : <em>mixed An object or associative array.</em><br /><em>Perform an Instagram API call. POST request instead of a GET. otherwise we decode to object.</em> |
| public static | <strong>api_body_decode(</strong><em>string</em> <strong>$json</strong>, <em>bool</em> <strong>$assoc=false</strong>)</strong> : <em>object/array/null Object if assoc false, Array if assoc true, or NULL if unable to decode JSON.</em><br /><em>Decode a JSON reply from Instagram's API. WARNING: EXTREMELY IMPORTANT! NEVER, *EVER* USE THE BASIC "json_decode" ON API REPLIES! ALWAYS USE THIS METHOD INSTEAD, TO ENSURE PROPER DECODING OF BIG NUMBERS! OTHERWISE YOU'LL TRUNCATE VARIOUS INSTAGRAM API FIELDS!</em> |
| public | <strong>changeProfilePicture(</strong><em>string</em> <strong>$photoFilename</strong>)</strong> : <em>[\InstagramAPI\Response\Model\User](#class-instagramapiresponsemodeluser)</em><br /><em>Changes your account's profile picture.</em> |
| public | <strong>directShare(</strong><em>string</em> <strong>$shareType</strong>, <em>string[]/string</em> <strong>$recipients</strong>, <em>array</em> <strong>$shareData</strong>)</strong> : <em>[\InstagramAPI\Response](#class-instagramapiresponse)</em><br /><em>Perform a direct media share to specific users. of multiple recipient strings. "text" and "media_id". "message" uses "text". "photo" uses "text" and "filepath".</em> |
| public | <strong>getCookieJarAsJSON()</strong> : <em>string</em><br /><em>Gives you all cookies in the Jar encoded as a JSON string. This allows custom Settings storages to retrieve all cookies for saving.</em> |
| public | <strong>getMappedResponseObject(</strong><em>mixed</em> <strong>$baseClass</strong>, <em>mixed</em> <strong>$response</strong>, <em>bool</em> <strong>$checkOk=true</strong>, <em>mixed</em> <strong>$fullResponse=null</strong>)</strong> : <em>mixed</em><br /><em>Converts a server response to a specific kind of result object. you want to fill from the $response. response wasn't marked as OK by Instagram. "getFullResponse()" property. Set this to NULL to automatically use $response. That's almost always what you want to do!</em> |
| public | <strong>getOutputInterface()</strong> : <em>string/null</em><br /><em>Gets the current network interface override used for requests.</em> |
| public | <strong>getProxy()</strong> : <em>string/array/null</em><br /><em>Gets the current proxy used for requests.</em> |
| public | <strong>getVerifySSL()</strong> : <em>bool/string</em><br /><em>Gets the current SSL verification behavior of the Client.</em> |
| public | <strong>loadCookieJar(</strong><em>bool</em> <strong>$resetCookieJar=false</strong>)</strong> : <em>mixed</em><br /><em>Loads all cookies via the current Settings storage.</em> |
| public | <strong>requestVideoUploadURL(</strong><em>string</em> <strong>$targetFeed</strong>, <em>array</em> <strong>$internalMetadata=array()</strong>)</strong> : <em>array</em><br /><em>Asks Instagram for parameters for uploading a new video.</em> |
| public | <strong>saveCookieJar()</strong> : <em>void</em><br /><em>Tells current settings storage to store cookies if necessary. There is no need to call this function manually. It's automatically called by _guzzleRequest()!</em> |
| public | <strong>setOutputInterface(</strong><em>mixed</em> <strong>$value</strong>)</strong> : <em>void</em><br /><em>Sets the network interface override to use. Only works if Guzzle is using the cURL backend. But that's almost always the case, on most PHP installations.</em> |
| public | <strong>setProxy(</strong><em>string/array/null</em> <strong>$value</strong>)</strong> : <em>void</em><br /><em>Set the proxy to use for requests.</em> |
| public | <strong>setVerifySSL(</strong><em>bool/string</em> <strong>$state</strong>)</strong> : <em>void</em><br /><em>Controls the SSL verification behavior of the Client.</em> |
| public | <strong>updateFromCurrentSettings(</strong><em>bool</em> <strong>$resetCookieJar=false</strong>)</strong> : <em>void</em><br /><em>Resets certain Client settings via the current Settings storage. Used whenever the user switches setUser(), to configure our internal state.</em> |
| public | <strong>uploadPhotoData(</strong><em>string</em> <strong>$targetFeed</strong>, <em>string</em> <strong>$photoFilename</strong>, <em>string</em> <strong>$fileType=`'photofile'`</strong>, <em>null</em> <strong>$uploadId=null</strong>)</strong> : <em>[\InstagramAPI\Response\UploadPhotoResponse](#class-instagramapiresponseuploadphotoresponse)</em><br /><em>Uploads a photo to Instagram. In case of videofile we'll generate a thumbnail from it.</em> |
| public | <strong>uploadVideoChunks(</strong><em>string</em> <strong>$targetFeed</strong>, <em>string</em> <strong>$videoFilename</strong>, <em>array</em> <strong>$uploadParams</strong>)</strong> : <em>[\InstagramAPI\Response\UploadVideoResponse](#class-instagramapiresponseuploadvideoresponse)</em><br /><em>Performs a chunked upload of a video file. Note that video uploads often fail when their server is overloaded. So you may have to redo this call multiple times.</em> |
| public | <strong>uploadVideoData(</strong><em>string</em> <strong>$targetFeed</strong>, <em>string</em> <strong>$videoFilename</strong>, <em>array</em> <strong>$uploadParams</strong>, <em>int</em> <strong>$maxAttempts=10</strong>)</strong> : <em>[\InstagramAPI\Response\UploadVideoResponse](#class-instagramapiresponseuploadvideoresponse)</em><br /><em>Uploads a video to Instagram, with multiple retries. The retries are very important since their media server is often overloaded and aborts the upload. So you almost always want this instead of uploadVideoChunks().</em> |
| protected | <strong>_apiRequest(</strong><em>string</em> <strong>$method</strong>, <em>string</em> <strong>$endpoint</strong>, <em>array</em> <strong>$guzzleOptions=array()</strong>, <em>array</em> <strong>$libraryOptions=array()</strong>)</strong> : <em>array An array with the Guzzle "response" object, and the raw non-decoded HTTP "body" of the request, and the "object" if the "decodeToObject" library option was used.</em><br /><em>Internal wrapper around _guzzleRequest(). This takes care of many common additional tasks needed by our library, so you should try to always use this instead of the raw _guzzleRequest()! Available library options are: - 'noDebug': Can be set to TRUE to forcibly hide debugging output for this request. The user controls debugging globally, but this is an override that prevents them from seeing certain requests that you may not want to trigger debugging (such as perhaps individual steps of a file upload process). However, debugging SHOULD be allowed in MOST cases! So only use this feature if you have a very good reason. - 'debugUploadedBody': Set to TRUE to make debugging display the data that was uploaded in the body of the request. DO NOT use this if your function uploaded binary data, since printing those bytes would kill the terminal! - 'debugUploadedBytes': Set to TRUE to make debugging display the size of the uploaded body data. Should ALWAYS be TRUE when uploading binary data. - 'decodeToObject': If this option is provided, it MUST either be an instance of a new class object, or FALSE to signify that you don't want us to do any object decoding. Omitting this option entirely is the same as FALSE, but it is highly recommended to ALWAYS include this option (even if FALSE), for code clarity about what you intend to do with this function's response! but can also be a full URI starting with "http:" or "https:", which is then used as-provided. such as the debugging output and response decoding.</em> |
| protected | <strong>_buildBody(</strong><em>array</em> <strong>$bodies</strong>, <em>string</em> <strong>$boundary</strong>)</strong> : <em>string</em><br /><em>Internal helper for building a properly formatted request body.</em> |
| protected | <strong>_buildGuzzleOptions(</strong><em>array</em> <strong>$guzzleOptions</strong>)</strong> : <em>array A guzzle options array.</em><br /><em>Helper which builds in the most important Guzzle options. Takes care of adding all critical options that we need on every request. Such as cookies and the user's proxy. But don't call this function manually. It's automatically called by _guzzleRequest()!</em> |
| protected | <strong>_guzzleRequest(</strong><em>string</em> <strong>$method</strong>, <em>string</em> <strong>$uri</strong>, <em>array</em> <strong>$guzzleOptions=array()</strong>)</strong> : <em>\Psr\Http\Message\ResponseInterface</em><br /><em>Wraps Guzzle's request and adds special error handling and options. Automatically throws exceptions on certain very serious HTTP errors. And re-wraps all Guzzle errors to our own internal exceptions instead. You must ALWAYS use this (or _apiRequest()) instead of the raw Guzzle Client! However, you can never assume the server response contains what you wanted. Be sure to validate the API reply too, since Instagram's API calls themselves may fail with a JSON message explaining what went wrong. WARNING: This is a semi-lowlevel handler which only applies critical options and HTTP connection handling! Most functions will want to call _apiRequest() instead. An even higher-level handler which takes care of debugging, server response checking and response decoding!</em> |
| protected | <strong>_printDebug(</strong><em>string</em> <strong>$method</strong>, <em>string</em> <strong>$url</strong>, <em>string/null</em> <strong>$uploadedBody</strong>, <em>int/null</em> <strong>$uploadedBytes</strong>, <em>object</em> <strong>$response</strong>, <em>string</em> <strong>$responseBody</strong>)</strong> : <em>void</em><br /><em>Output debugging information. avoid displaying it. avoid displaying it.</em> |
| protected | <strong>_throwIfNotLoggedIn()</strong> : <em>void</em><br /><em>Helper which throws an error if not logged in. Remember to ALWAYS call this function at the top of any API request that requires the user to be logged in!</em> |

---
### Class: \InstagramAPI\ClientMiddleware

> Custom Guzzle middleware. This middleware sits between our class and Guzzle and gives us full access to inject or modify any aspect of our requests before speaking to Instagram's server. Thus allowing us to perfectly emulate unusual Instagram API queries.

| Visibility | Function |
|:-----------|:---------|
| public | <strong>__construct()</strong> : <em>void</em><br /><em>Constructor.</em> |
| public | <strong>__invoke(</strong><em>\callable</em> <strong>$handler</strong>)</strong> : <em>callable</em><br /><em>Middleware setup function. Called by Guzzle when it needs to add an instance of our middleware to its stack. We simply return a callable which will process all requests.</em> |
| public | <strong>addFakeCookie(</strong><em>string</em> <strong>$name</strong>, <em>string</em> <strong>$value</strong>, <em>bool</em> <strong>$singleUse=true</strong>)</strong> : <em>void</em><br /><em>Adds a fake cookie which will be injected into all requests. Remember to clear your fake cookies when you no longer need them. Usually you only need fake cookies for a few requests, and care must be taken to GUARANTEE clearout after that, via something like the following: "try{...}finally{ ...->clearFakeCookies(); }"). Otherwise you would FOREVER pollute all other requests! If you only need the cookie once, the best way to guarantee clearout is to leave the "singleUse" parameter in its enabled state.</em> |
| public | <strong>clearFakeCookies()</strong> : <em>void</em><br /><em>Removes all fake cookies so they won't be added to further requests.</em> |
| public | <strong>deleteFakeCookie(</strong><em>string</em> <strong>$name</strong>)</strong> : <em>void</em><br /><em>Delete a single fake cookie. Useful for selectively removing some fake cookies but keeping the rest.</em> |
| public | <strong>getFakeCookies()</strong> : <em>array</em><br /><em>Get all currently used fake cookies.</em> |

---
### Class: \InstagramAPI\Constants

| Visibility | Function |
|:-----------|:---------|

---
### Class: \InstagramAPI\Debug

| Visibility | Function |
|:-----------|:---------|
| public static | <strong>printHttpCode(</strong><em>mixed</em> <strong>$httpCode</strong>, <em>mixed</em> <strong>$bytes</strong>)</strong> : <em>void</em> |
| public static | <strong>printPostData(</strong><em>mixed</em> <strong>$post</strong>)</strong> : <em>void</em> |
| public static | <strong>printRequest(</strong><em>mixed</em> <strong>$method</strong>, <em>mixed</em> <strong>$endpoint</strong>)</strong> : <em>void</em> |
| public static | <strong>printResponse(</strong><em>mixed</em> <strong>$response</strong>, <em>bool</em> <strong>$truncated=false</strong>)</strong> : <em>void</em> |
| public static | <strong>printUpload(</strong><em>mixed</em> <strong>$uploadBytes</strong>)</strong> : <em>void</em> |

---
### Class: \InstagramAPI\ImageAutoResizer

> Automatic image resizer. Resizes and crops an image to match Instagram's requirements, if necessary. You can also use this to force your image into different aspects, ie square. Usage: - Create an instance of the class with your image file and requirements. - Call getFile() to get the path to an image matching the requirements. This will be the same as the input file if no processing was required. - Optionally, call deleteFile() if you want to delete the temporary file ahead of time instead of automatically when PHP does its object garbage collection. This function is safe and won't delete the original input file. Remember to thank Abyr Valg for the brilliant image processing algorithm!

| Visibility | Function |
|:-----------|:---------|
| public | <strong>__construct(</strong><em>string</em> <strong>$inputFile</strong>, <em>int/null</em> <strong>$cropFocus=null</strong>, <em>float/null</em> <strong>$minAspectRatio=null</strong>, <em>float/null</em> <strong>$maxAspectRatio=null</strong>, <em>string/null</em> <strong>$tmpPath=null</strong>)</strong> : <em>void</em><br /><em>Constructor. intelligent guess if not set. self::MIN_RATIO if not set. self::MAX_RATIO if not set. temp location if not set.</em> |
| public | <strong>__destruct()</strong> : <em>void</em><br /><em>Destructor.</em> |
| public | <strong>deleteFile()</strong> : <em>bool</em><br /><em>Removes the output file if it exists and differs from input file. This function is safe and won't delete the original input file. Is automatically called when the class instance is destroyed by PHP. But you can manually call it ahead of time if you want to force cleanup. Note that getFile() will still work afterwards, but will have to process the image again to a new temp file if the input file required processing.</em> |
| public | <strong>getFile()</strong> : <em>string The path to the image file.</em><br /><em>Gets the path to an image file matching the requirements. The automatic processing is performed the first time that this function is called. Which means that no CPU time is wasted if you never call this function at all. Due to the processing, the first call to this function may take a moment. If the input file already fits all of the specifications, we simply return the input path instead, without any need to re-process it.</em> |
| protected | <strong>_cropAndResize(</strong><em>\InstagramAPI\resource</em> <strong>$source</strong>, <em>int</em> <strong>$src_x</strong>, <em>int</em> <strong>$src_y</strong>, <em>int</em> <strong>$src_w</strong>, <em>int</em> <strong>$src_h</strong>, <em>int</em> <strong>$dst_w</strong>, <em>int</em> <strong>$dst_h</strong>)</strong> : <em>void</em> |
| protected | <strong>_makeTempFile()</strong> : <em>string</em><br /><em>Creates an empty temp file with a unique filename.</em> |
| protected | <strong>_process()</strong> : <em>void</em> |
| protected | <strong>_processResource(</strong><em>\InstagramAPI\resource</em> <strong>$resource</strong>)</strong> : <em>void</em> |
| protected | <strong>_rotateResource(</strong><em>\InstagramAPI\resource</em> <strong>$original</strong>, <em>int</em> <strong>$angle</strong>, <em>int</em> <strong>$bgColor</strong>, <em>int/null</em> <strong>$flip=null</strong>)</strong> : <em>\InstagramAPI\resource</em><br /><em>Wrapper for imagerotate function.</em> |
| protected | <strong>_shouldProcess()</strong> : <em>bool</em><br /><em>Checks whether we should process the input file.</em> |

---
### Class: \InstagramAPI\Instagram

> Instagram's Private API v2. TERMS OF USE: - This code is in no way affiliated with, authorized, maintained, sponsored or endorsed by Instagram or any of its affiliates or subsidiaries. This is an independent and unofficial API. Use at your own risk. - We do NOT support or tolerate anyone who wants to use this API to send spam or commit other online crimes. - You will NOT use this API for marketing or other abusive purposes (spam, botting, harassment, massive bulk messaging...).

| Visibility | Function |
|:-----------|:---------|
| public | <strong>__construct(</strong><em>bool</em> <strong>$debug=false</strong>, <em>bool</em> <strong>$truncatedDebug=false</strong>, <em>array</em> <strong>$storageConfig=array()</strong>)</strong> : <em>void</em><br /><em>Constructor. user settings storage backend.</em> |
| public | <strong>backup(</strong><em>string</em> <strong>$baseOutputPath=null</strong>, <em>bool</em> <strong>$printProgress=true</strong>)</strong> : <em>void</em><br /><em>Backup all of your own uploaded photos and videos. :). Uses "backups/" path in lib dir if null.</em> |
| public | <strong>block(</strong><em>string</em> <strong>$userId</strong>)</strong> : <em>[\InstagramAPI\Response\FriendshipResponse](#class-instagramapiresponsefriendshipresponse)</em><br /><em>Block a user.</em> |
| public | <strong>blockFriendStory(</strong><em>string</em> <strong>$userId</strong>)</strong> : <em>[\InstagramAPI\Response\FriendshipResponse](#class-instagramapiresponsefriendshipresponse)</em><br /><em>Block a user from viewing your story.</em> |
| public | <strong>changePassword(</strong><em>string</em> <strong>$oldPassword</strong>, <em>string</em> <strong>$newPassword</strong>)</strong> : <em>[\InstagramAPI\Response\ChangePasswordResponse](#class-instagramapiresponsechangepasswordresponse)</em><br /><em>Change your account's password.</em> |
| public | <strong>changeProfilePicture(</strong><em>string</em> <strong>$photoFilename</strong>)</strong> : <em>[\InstagramAPI\Response\Model\User](#class-instagramapiresponsemodeluser)</em><br /><em>Changes your account's profile picture.</em> |
| public | <strong>comment(</strong><em>string</em> <strong>$mediaId</strong>, <em>string</em> <strong>$commentText</strong>)</strong> : <em>[\InstagramAPI\Response\CommentResponse](#class-instagramapiresponsecommentresponse)</em><br /><em>Post a comment on a media item.</em> |
| public | <strong>commentBroadcast(</strong><em>string</em> <strong>$broadcastId</strong>, <em>string</em> <strong>$commentText</strong>)</strong> : <em>[\InstagramAPI\Response\CommentBroadcastResponse](#class-instagramapiresponsecommentbroadcastresponse)</em><br /><em>Post a comment to a live broadcast.</em> |
| public | <strong>configureSinglePhoto(</strong><em>string</em> <strong>$targetFeed</strong>, <em>array</em> <strong>$internalMetadata</strong>, <em>array</em> <strong>$externalMetadata=array()</strong>)</strong> : <em>[\InstagramAPI\Response\ConfigureResponse](#class-instagramapiresponseconfigureresponse)</em><br /><em>Configures parameters for a *SINGLE* uploaded photo file. WARNING TO CONTRIBUTORS: THIS IS ONLY FOR *TIMELINE* AND *STORY* -PHOTOS-. USE "configureTimelineAlbum()" FOR ALBUMS and "configureSingleVideo()" FOR VIDEOS. AND IF FUTURE INSTAGRAM FEATURES NEED CONFIGURATION AND ARE NON-TRIVIAL, GIVE THEM THEIR OWN FUNCTION LIKE WE DID WITH "configureTimelineAlbum()", TO AVOID ADDING BUGGY AND UNMAINTAINABLE SPIDERWEB CODE! but NOT "album", they are handled elsewhere).</em> |
| public | <strong>configureSingleVideo(</strong><em>string</em> <strong>$targetFeed</strong>, <em>array</em> <strong>$internalMetadata</strong>, <em>array</em> <strong>$externalMetadata=array()</strong>)</strong> : <em>[\InstagramAPI\Response\ConfigureResponse](#class-instagramapiresponseconfigureresponse)</em><br /><em>Configures parameters for a *SINGLE* uploaded video file. WARNING TO CONTRIBUTORS: THIS IS ONLY FOR *TIMELINE* AND *STORY* -VIDEOS-. USE "configureTimelineAlbum()" FOR ALBUMS and "configureSinglePhoto()" FOR PHOTOS. AND IF FUTURE INSTAGRAM FEATURES NEED CONFIGURATION AND ARE NON-TRIVIAL, GIVE THEM THEIR OWN FUNCTION LIKE WE DID WITH "configureTimelineAlbum()", TO AVOID ADDING BUGGY AND UNMAINTAINABLE SPIDERWEB CODE! but NOT "album", they are handled elsewhere).</em> |
| public | <strong>configureSingleVideoWithRetries(</strong><em>string</em> <strong>$targetFeed</strong>, <em>array</em> <strong>$internalMetadata</strong>, <em>array</em> <strong>$externalMetadata=array()</strong>, <em>int</em> <strong>$maxAttempts=5</strong>)</strong> : <em>[\InstagramAPI\Response\ConfigureResponse](#class-instagramapiresponseconfigureresponse)</em><br /><em>Helper function for reliably configuring videos. Exactly the same as configureSingleVideo() but performs multiple attempts. Very useful since Instagram sometimes can't configure a newly uploaded video file until a few seconds have passed. but NOT "album", they are handled elsewhere).</em> |
| public | <strong>configureTimelineAlbum(</strong><em>array</em> <strong>$media</strong>, <em>array</em> <strong>$internalMetadata</strong>, <em>array</em> <strong>$externalMetadata=array()</strong>)</strong> : <em>[\InstagramAPI\Response\ConfigureResponse](#class-instagramapiresponseconfigureresponse)</em><br /><em>Configures parameters for a whole album of uploaded media files. WARNING TO CONTRIBUTORS: THIS IS ONLY FOR *TIMELINE ALBUMS*. DO NOT MAKE IT DO ANYTHING ELSE, TO AVOID ADDING BUGGY AND UNMAINTAINABLE SPIDERWEB CODE! containing the user's per-file metadata, and internally generated per-file metadata. for the album itself (its caption, location, etc).</em> |
| public | <strong>configureTimelineAlbumWithRetries(</strong><em>array</em> <strong>$media</strong>, <em>array</em> <strong>$internalMetadata</strong>, <em>array</em> <strong>$externalMetadata=array()</strong>, <em>int</em> <strong>$maxAttempts=5</strong>)</strong> : <em>[\InstagramAPI\Response\ConfigureResponse](#class-instagramapiresponseconfigureresponse)</em><br /><em>Helper function for reliably configuring albums. Exactly the same as configureTimelineAlbum() but performs multiple attempts. Very useful since Instagram sometimes can't configure a newly uploaded video file until a few seconds have passed. containing the user's per-file metadata, and internally generated per-file metadata. for the album itself (its caption, location, etc).</em> |
| public | <strong>deleteComment(</strong><em>string</em> <strong>$mediaId</strong>, <em>string</em> <strong>$commentId</strong>)</strong> : <em>[\InstagramAPI\Response\DeleteCommentResponse](#class-instagramapiresponsedeletecommentresponse)</em><br /><em>Delete a comment.</em> |
| public | <strong>deleteComments(</strong><em>string</em> <strong>$mediaId</strong>, <em>string</em> <strong>$commentIds</strong>)</strong> : <em>[\InstagramAPI\Response\DeleteCommentResponse](#class-instagramapiresponsedeletecommentresponse)</em><br /><em>Delete multiple comments.</em> |
| public | <strong>deleteMedia(</strong><em>string</em> <strong>$mediaId</strong>)</strong> : <em>[\InstagramAPI\Response\MediaDeleteResponse](#class-instagramapiresponsemediadeleteresponse)</em><br /><em>Delete a media item.</em> |
| public | <strong>directMessage(</strong><em>string/string[]</em> <strong>$recipients</strong>, <em>string</em> <strong>$text</strong>)</strong> : <em>[\InstagramAPI\Response](#class-instagramapiresponse)</em><br /><em>Send a direct message to a user's inbox.</em> |
| public | <strong>directPhoto(</strong><em>string/string[]</em> <strong>$recipients</strong>, <em>string</em> <strong>$photoFilename</strong>, <em>string</em> <strong>$text=null</strong>)</strong> : <em>[\InstagramAPI\Response](#class-instagramapiresponse)</em><br /><em>Send a photo via direct message to a user's inbox.</em> |
| public | <strong>directShare(</strong><em>string/string[]</em> <strong>$recipients</strong>, <em>string</em> <strong>$mediaId</strong>, <em>string</em> <strong>$text=null</strong>)</strong> : <em>[\InstagramAPI\Response](#class-instagramapiresponse)</em><br /><em>Share media via direct message to a user's inbox.</em> |
| public | <strong>directThread(</strong><em>string</em> <strong>$threadId</strong>, <em>string/null</em> <strong>$cursorId=null</strong>)</strong> : <em>[\InstagramAPI\Response\DirectThreadResponse](#class-instagramapiresponsedirectthreadresponse)</em><br /><em>Get direct message thread.</em> |
| public | <strong>directThreadAction(</strong><em>string</em> <strong>$threadId</strong>, <em>string</em> <strong>$threadAction</strong>)</strong> : <em>array Direct thread action server response.</em><br /><em>Perform an action on a direct message thread.</em> |
| public | <strong>disableMediaComments(</strong><em>string</em> <strong>$mediaId</strong>)</strong> : <em>[\InstagramAPI\Response](#class-instagramapiresponse)</em><br /><em>Disable comments for a media item.</em> |
| public | <strong>disableTwoFactor()</strong> : <em>[\InstagramAPI\Response\DisableTwoFactorResponse](#class-instagramapiresponsedisabletwofactorresponse)</em><br /><em>Disable Two Factor authentication.</em> |
| public | <strong>editMedia(</strong><em>string</em> <strong>$mediaId</strong>, <em>string</em> <strong>$captionText=`''`</strong>, <em>mixed</em> <strong>$usertags=null</strong>)</strong> : <em>[\InstagramAPI\Response\EditMediaResponse](#class-instagramapiresponseeditmediaresponse)</em><br /><em>Edit media.</em> |
| public | <strong>editProfile(</strong><em>string</em> <strong>$url</strong>, <em>string</em> <strong>$phone</strong>, <em>string</em> <strong>$firstName</strong>, <em>string</em> <strong>$biography</strong>, <em>string</em> <strong>$email</strong>, <em>int</em> <strong>$gender</strong>)</strong> : <em>[\InstagramAPI\Response\UserInfoResponse](#class-instagramapiresponseuserinforesponse)</em><br /><em>Edit your profile.</em> |
| public | <strong>enableMediaComments(</strong><em>string</em> <strong>$mediaId</strong>)</strong> : <em>[\InstagramAPI\Response](#class-instagramapiresponse)</em><br /><em>Enable comments for a media item.</em> |
| public | <strong>enableTwoFactor(</strong><em>string</em> <strong>$phoneNumber</strong>, <em>string</em> <strong>$verificationCode</strong>)</strong> : <em>[\InstagramAPI\Response\AccountSecurityInfoResponse](#class-instagramapiresponseaccountsecurityinforesponse)</em><br /><em>Enable Two Factor authentication.</em> |
| public | <strong>expose()</strong> : <em>[\InstagramAPI\Response\ExposeResponse](#class-instagramapiresponseexposeresponse)</em><br /><em>Expose.</em> |
| public | <strong>follow(</strong><em>string</em> <strong>$userId</strong>)</strong> : <em>[\InstagramAPI\Response\FriendshipResponse](#class-instagramapiresponsefriendshipresponse)</em><br /><em>Follow.</em> |
| public | <strong>getAccountSecurityInfo()</strong> : <em>[\InstagramAPI\Response\AccountSecurityInfoResponse](#class-instagramapiresponseaccountsecurityinforesponse)</em><br /><em>Get account security info and backup codes. WARNING: STORE AND KEEP BACKUP CODES IN A SAFE PLACE. YOU WILL GET THE CODES IN THE RESPONSE.</em> |
| public | <strong>getAutoCompleteUserList()</strong> : <em>[\InstagramAPI\Response\AutoCompleteUserListResponse](#class-instagramapiresponseautocompleteuserlistresponse)/null Will be NULL if throttled by Instagram.</em><br /><em>Retrieve list of all friends.</em> |
| public | <strong>getBroadcastComments(</strong><em>string</em> <strong>$broadcastId</strong>, <em>string</em> <strong>$lastCommentTs</strong>)</strong> : <em>[\InstagramAPI\Response\BroadcastCommentsResponse](#class-instagramapiresponsebroadcastcommentsresponse)</em><br /><em>Get broadcast comments.</em> |
| public | <strong>getBroadcastHeartbeatAndViewerCount(</strong><em>string</em> <strong>$broadcastId</strong>)</strong> : <em>[\InstagramAPI\Response\BroadcastHeartbeatAndViewerCountResponse](#class-instagramapiresponsebroadcastheartbeatandviewercountresponse)</em><br /><em>Get a live broadcast's heartbeat and viewer count.</em> |
| public | <strong>getBroadcastInfo(</strong><em>string</em> <strong>$broadcastId</strong>)</strong> : <em>[\InstagramAPI\Response\BroadcastInfoResponse](#class-instagramapiresponsebroadcastinforesponse)</em><br /><em>Get broadcast information.</em> |
| public | <strong>getBroadcastLikeCount(</strong><em>string</em> <strong>$broadcastId</strong>, <em>string</em> <strong>$likeTs</strong>)</strong> : <em>[\InstagramAPI\Response\BroadcastLikeCountResponse](#class-instagramapiresponsebroadcastlikecountresponse)</em><br /><em>Get a live broadcast's like count.</em> |
| public | <strong>getCurrentUser()</strong> : <em>[\InstagramAPI\Response\UserInfoResponse](#class-instagramapiresponseuserinforesponse)</em><br /><em>Get details about the currently logged in account.</em> |
| public | <strong>getDirectShare()</strong> : <em>[\InstagramAPI\Response\DirectShareInboxResponse](#class-instagramapiresponsedirectshareinboxresponse)</em><br /><em>Get direct share inbox.</em> |
| public | <strong>getDiscoverChannels()</strong> : <em>[\InstagramAPI\Response\DiscoverChannelsResponse](#class-instagramapiresponsediscoverchannelsresponse)</em><br /><em>Get Home channel data.</em> |
| public | <strong>getDiscoverTopLive()</strong> : <em>[\InstagramAPI\Response\DiscoverTopLiveResponse](#class-instagramapiresponsediscovertopliveresponse)</em><br /><em>Get top live broadcasts.</em> |
| public | <strong>getExplore()</strong> : <em>[\InstagramAPI\Response\ExploreResponse](#class-instagramapiresponseexploreresponse)</em><br /><em>Get Explore tab data.</em> |
| public | <strong>getFacebookOTA()</strong> : <em>[\InstagramAPI\Response\FacebookOTAResponse](#class-instagramapiresponsefacebookotaresponse)</em><br /><em>Get Facebook OTA.</em> |
| public | <strong>getFollowingRecentActivity(</strong><em>null/string</em> <strong>$maxId=null</strong>)</strong> : <em>[\InstagramAPI\Response\FollowingRecentActivityResponse](#class-instagramapiresponsefollowingrecentactivityresponse)</em><br /><em>Get news feed with recent activity from all accounts you follow.</em> |
| public | <strong>getGeoMedia(</strong><em>string</em> <strong>$userId</strong>)</strong> : <em>[\InstagramAPI\Response\GeoMediaResponse](#class-instagramapiresponsegeomediaresponse)</em><br /><em>Get location based media feed for a user. Note that you probably want getUserFeed() instead, because the geographical feed does not contain all of the user's media.</em> |
| public | <strong>getHashtagFeed(</strong><em>string</em> <strong>$hashtagString</strong>, <em>null/string</em> <strong>$maxId=null</strong>)</strong> : <em>[\InstagramAPI\Response\TagFeedResponse](#class-instagramapiresponsetagfeedresponse)</em><br /><em>Get hashtag feed.</em> |
| public | <strong>getInsights(</strong><em>mixed</em> <strong>$day=null</strong>)</strong> : <em>[\InstagramAPI\Response\InsightsResponse](#class-instagramapiresponseinsightsresponse)</em><br /><em>Get insights.</em> |
| public | <strong>getLikedMedia(</strong><em>null/string</em> <strong>$maxId=null</strong>)</strong> : <em>[\InstagramAPI\Response\LikeFeedResponse](#class-instagramapiresponselikefeedresponse)</em><br /><em>Get feed of your liked media.</em> |
| public | <strong>getLocationFeed(</strong><em>string</em> <strong>$locationId</strong>, <em>null/string</em> <strong>$maxId=null</strong>)</strong> : <em>[\InstagramAPI\Response\LocationFeedResponse](#class-instagramapiresponselocationfeedresponse)</em><br /><em>Get location feed.</em> |
| public | <strong>getMediaComments(</strong><em>string</em> <strong>$mediaId</strong>, <em>null/string</em> <strong>$maxId=null</strong>)</strong> : <em>[\InstagramAPI\Response\MediaCommentsResponse](#class-instagramapiresponsemediacommentsresponse)</em><br /><em>Get media comments.</em> |
| public | <strong>getMediaInfo(</strong><em>string</em> <strong>$mediaId</strong>)</strong> : <em>[\InstagramAPI\Response\MediaInfoResponse](#class-instagramapiresponsemediainforesponse)</em><br /><em>Get detailed media information.</em> |
| public | <strong>getMediaInsights(</strong><em>string</em> <strong>$mediaId</strong>)</strong> : <em>[\InstagramAPI\Response\MediaInsightsResponse](#class-instagramapiresponsemediainsightsresponse)</em><br /><em>Get media insights.</em> |
| public | <strong>getMediaLikers(</strong><em>string</em> <strong>$mediaId</strong>)</strong> : <em>[\InstagramAPI\Response\MediaLikersResponse](#class-instagramapiresponsemedialikersresponse)</em><br /><em>Get list of users who liked a media item.</em> |
| public | <strong>getMegaphoneLog()</strong> : <em>[\InstagramAPI\Response\MegaphoneLogResponse](#class-instagramapiresponsemegaphonelogresponse)</em><br /><em>Get megaphone log.</em> |
| public | <strong>getOutputInterface()</strong> : <em>string/null</em><br /><em>Gets the current network interface override used for requests.</em> |
| public | <strong>getPendingFriendshipRequests()</strong> : <em>[\InstagramAPI\Response\FollowerAndFollowingResponse](#class-instagramapiresponsefollowerandfollowingresponse)</em><br /><em>Get list of pending friendship requests.</em> |
| public | <strong>getPendingInbox()</strong> : <em>[\InstagramAPI\Response\PendingInboxResponse](#class-instagramapiresponsependinginboxresponse)</em><br /><em>Get pending inbox data.</em> |
| public | <strong>getPopularFeed()</strong> : <em>[\InstagramAPI\Response\PopularFeedResponse](#class-instagramapiresponsepopularfeedresponse)</em><br /><em>Get popular feed.</em> |
| public | <strong>getProxy()</strong> : <em>string/array/null</em><br /><em>Gets the current proxy used for requests.</em> |
| public | <strong>getRankedRecipients()</strong> : <em>[\InstagramAPI\Response\RankedRecipientsResponse](#class-instagramapiresponserankedrecipientsresponse)</em><br /><em>Get ranked list of recipients.</em> |
| public | <strong>getRecentActivity()</strong> : <em>[\InstagramAPI\Response\ActivityNewsResponse](#class-instagramapiresponseactivitynewsresponse)</em><br /><em>Get recent activity.</em> |
| public | <strong>getRecentRecipients()</strong> : <em>[\InstagramAPI\Response\RecentRecipientsResponse](#class-instagramapiresponserecentrecipientsresponse)</em><br /><em>Get recent recipients.</em> |
| public | <strong>getReelsMediaFeed(</strong><em>string/string[]</em> <strong>$userList</strong>)</strong> : <em>[\InstagramAPI\Response\ReelsMediaResponse](#class-instagramapiresponsereelsmediaresponse)</em><br /><em>Get multiple users' story feeds at once.</em> |
| public | <strong>getReelsTrayFeed()</strong> : <em>[\InstagramAPI\Response\ReelsTrayFeedResponse](#class-instagramapiresponsereelstrayfeedresponse)</em><br /><em>Get the global story feed which contains everyone you follow. Note that users will eventually drop out of this list even though they still have stories. So it's always safer to call getUserStoryFeed() if a specific user's story feed matters to you.</em> |
| public | <strong>getSavedFeed()</strong> : <em>[\InstagramAPI\Response\SavedFeedResponse](#class-instagramapiresponsesavedfeedresponse)</em><br /><em>Get saved media items feed.</em> |
| public | <strong>getSelfGeoMedia()</strong> : <em>[\InstagramAPI\Response\GeoMediaResponse](#class-instagramapiresponsegeomediaresponse)</em><br /><em>Get location based media feed for your own account.</em> |
| public | <strong>getSelfUserFeed(</strong><em>null/string</em> <strong>$maxId=null</strong>, <em>null/int</em> <strong>$minTimestamp=null</strong>)</strong> : <em>[\InstagramAPI\Response\UserFeedResponse](#class-instagramapiresponseuserfeedresponse)</em><br /><em>Get your own timeline feed.</em> |
| public | <strong>getSelfUserFollowers(</strong><em>null/string</em> <strong>$maxId=null</strong>)</strong> : <em>[\InstagramAPI\Response\FollowerAndFollowingResponse](#class-instagramapiresponsefollowerandfollowingresponse)</em><br /><em>Get list of your own followers.</em> |
| public | <strong>getSelfUserInfo()</strong> : <em>[\InstagramAPI\Response\UserInfoResponse](#class-instagramapiresponseuserinforesponse)</em><br /><em>Get user details about your own account. Also try getCurrentUser() instead, for even more details.</em> |
| public | <strong>getSelfUserTags()</strong> : <em>[\InstagramAPI\Response\UsertagsResponse](#class-instagramapiresponseusertagsresponse)</em><br /><em>Get user taggings for your own account.</em> |
| public | <strong>getSelfUsersFollowing(</strong><em>null/string</em> <strong>$maxId=null</strong>)</strong> : <em>[\InstagramAPI\Response\FollowerAndFollowingResponse](#class-instagramapiresponsefollowerandfollowingresponse)</em><br /><em>Get list of who you are following.</em> |
| public | <strong>getStickerAssets(</strong><em>string</em> <strong>$stickerType=`'static_stickers'`</strong>, <em>array</em> <strong>$location=null</strong>)</strong> : <em>[\InstagramAPI\Response\StickerAssetsResponse](#class-instagramapiresponsestickerassetsresponse)</em><br /><em>Get sticker assets.</em> |
| public | <strong>getSuggestedBroadcasts()</strong> : <em>[\InstagramAPI\Response\SuggestedBroadcastsResponse](#class-instagramapiresponsesuggestedbroadcastsresponse)</em><br /><em>Get suggested broadcasts.</em> |
| public | <strong>getSuggestedUsers(</strong><em>string</em> <strong>$userId</strong>)</strong> : <em>[\InstagramAPI\Response\SuggestedUsersResponse](#class-instagramapiresponsesuggestedusersresponse)</em><br /><em>Get suggested users.</em> |
| public | <strong>getTagInfo(</strong><em>string</em> <strong>$tag</strong>)</strong> : <em>[\InstagramAPI\Response\TagInfoResponse](#class-instagramapiresponsetaginforesponse)</em><br /><em>Get detailed tag information.</em> |
| public | <strong>getTagRelated(</strong><em>string</em> <strong>$tag</strong>)</strong> : <em>[\InstagramAPI\Response\TagRelatedResponse](#class-instagramapiresponsetagrelatedresponse)</em><br /><em>Get related tags.</em> |
| public | <strong>getTimelineFeed(</strong><em>null/string</em> <strong>$maxId=null</strong>)</strong> : <em>[\InstagramAPI\Response\TimelineFeedResponse](#class-instagramapiresponsetimelinefeedresponse)</em><br /><em>Get your own timeline feed.</em> |
| public | <strong>getTopLiveStatus(</strong><em>string/string[]</em> <strong>$broadcastIds</strong>)</strong> : <em>[\InstagramAPI\Response\TopLiveStatusResponse](#class-instagramapiresponsetoplivestatusresponse)</em><br /><em>Get status for a list of broadcast ids.</em> |
| public | <strong>getUserFeed(</strong><em>string</em> <strong>$userId</strong>, <em>null/string</em> <strong>$maxId=null</strong>, <em>null/int</em> <strong>$minTimestamp=null</strong>)</strong> : <em>[\InstagramAPI\Response\UserFeedResponse](#class-instagramapiresponseuserfeedresponse)</em><br /><em>Get a user's timeline feed.</em> |
| public | <strong>getUserFollowers(</strong><em>string</em> <strong>$userId</strong>, <em>null/string</em> <strong>$maxId=null</strong>)</strong> : <em>[\InstagramAPI\Response\FollowerAndFollowingResponse](#class-instagramapiresponsefollowerandfollowingresponse)</em><br /><em>Get list of who a user is followed by.</em> |
| public | <strong>getUserFollowings(</strong><em>string</em> <strong>$userId</strong>, <em>null/string</em> <strong>$maxId=null</strong>)</strong> : <em>[\InstagramAPI\Response\FollowerAndFollowingResponse](#class-instagramapiresponsefollowerandfollowingresponse)</em><br /><em>Get list of who a user is following.</em> |
| public | <strong>getUserFriendship(</strong><em>string</em> <strong>$userId</strong>)</strong> : <em>[\InstagramAPI\Response\Model\FriendshipStatus](#class-instagramapiresponsemodelfriendshipstatus)</em><br /><em>Show a user's friendship status with you.</em> |
| public | <strong>getUserInfoById(</strong><em>string</em> <strong>$userId</strong>)</strong> : <em>[\InstagramAPI\Response\UserInfoResponse](#class-instagramapiresponseuserinforesponse)</em><br /><em>Get details about a specific user via their numerical UserPK ID.</em> |
| public | <strong>getUserInfoByName(</strong><em>string</em> <strong>$username</strong>)</strong> : <em>[\InstagramAPI\Response\UserInfoResponse](#class-instagramapiresponseuserinforesponse)</em><br /><em>Get details about a specific user via their username.</em> |
| public | <strong>getUserReelMediaFeed(</strong><em>string</em> <strong>$userId</strong>)</strong> : <em>[\InstagramAPI\Response\Model\Reel](#class-instagramapiresponsemodelreel)</em><br /><em>Get a specific user's story reel feed. This function gets the user's story Reel object directly, which always exists and contains information about the user and their last story even if that user doesn't have any active story anymore.</em> |
| public | <strong>getUserStoryFeed(</strong><em>string</em> <strong>$userId</strong>)</strong> : <em>[\InstagramAPI\Response\UserStoryFeedResponse](#class-instagramapiresponseuserstoryfeedresponse)</em><br /><em>Get a specific user's story feed with broadcast details. This function gets the story in a roundabout way, with some extra details about the "broadcast". But if there is no story available, this endpoint gives you an empty response.</em> |
| public | <strong>getUserTags(</strong><em>string</em> <strong>$userId</strong>, <em>null/string</em> <strong>$maxId=null</strong>, <em>null/int</em> <strong>$minTimestamp=null</strong>)</strong> : <em>[\InstagramAPI\Response\UsertagsResponse](#class-instagramapiresponseusertagsresponse)</em><br /><em>Get user taggings for a user.</em> |
| public | <strong>getUsernameId(</strong><em>string</em> <strong>$username</strong>)</strong> : <em>string Their numerical UserPK ID.</em><br /><em>Get the numerical UserPK ID for a specific user via their username. This is just a convenient helper function. You may prefer to use getUserInfoByName() instead, which lets you see more details.</em> |
| public | <strong>getUsersFriendship(</strong><em>string/string[]</em> <strong>$userList</strong>)</strong> : <em>[\InstagramAPI\Response\FriendshipsShowManyResponse](#class-instagramapiresponsefriendshipsshowmanyresponse)</em><br /><em>Show multiple users' friendship status with you.</em> |
| public | <strong>getV2Inbox(</strong><em>string/null</em> <strong>$cursorId=null</strong>)</strong> : <em>[\InstagramAPI\Response\V2InboxResponse](#class-instagramapiresponsev2inboxresponse)</em><br /><em>Get direct inbox messages for your account.</em> |
| public | <strong>getVerifySSL()</strong> : <em>bool/string</em><br /><em>Gets the current SSL verification behavior of the Client.</em> |
| public | <strong>getVisualInbox()</strong> : <em>[\InstagramAPI\Response\VisualInboxResponse](#class-instagramapiresponsevisualinboxresponse)</em><br /><em>Get visual inbox data.</em> |
| public | <strong>like(</strong><em>string</em> <strong>$mediaId</strong>)</strong> : <em>[\InstagramAPI\Response](#class-instagramapiresponse)</em><br /><em>Like a media item.</em> |
| public | <strong>likeBroadcast(</strong><em>string</em> <strong>$broadcastId</strong>, <em>string</em> <strong>$likeCount=1</strong>)</strong> : <em>[\InstagramAPI\Response\BroadcastLikeResponse](#class-instagramapiresponsebroadcastlikeresponse)</em><br /><em>Like a broadcast.</em> |
| public | <strong>likeComment(</strong><em>string</em> <strong>$commentId</strong>)</strong> : <em>[\InstagramAPI\Response\CommentLikeUnlikeResponse](#class-instagramapiresponsecommentlikeunlikeresponse)</em><br /><em>Like a comment.</em> |
| public | <strong>login(</strong><em>bool</em> <strong>$forceLogin=false</strong>, <em>int</em> <strong>$appRefreshInterval=1800</strong>)</strong> : <em>[\InstagramAPI\Response\LoginResponse](#class-instagramapiresponseloginresponse)</em><br /><em>Login to Instagram or automatically resume and refresh previous session. WARNING: You MUST run this function EVERY time your script runs! It handles automatic session resume and relogin and app session state refresh and other absolutely *vital* things that are important if you don't want to be banned from Instagram! that's been closed and reopened and needs to "refresh its state", by asking for extended account state details. Default: After 1800 seconds, meaning 30 minutes since the last state-refreshing login() call. This CANNOT be longer than 6 hours. Read code to see why! The shorter your delay is the BETTER. You may even want to set it to an even LOWER value than the default 30 minutes!</em> |
| public | <strong>logout()</strong> : <em>[\InstagramAPI\Response\LogoutResponse](#class-instagramapiresponselogoutresponse)</em><br /><em>Log out of Instagram. WARNING: Most people should NEVER call logout()! Our library emulates the Instagram app for Android, where you are supposed to stay logged in forever. By calling this function, you will tell Instagram that you are logging out of the APP. But you shouldn't do that! In almost 100% of all cases you want to *stay logged in* so that LOGIN() resumes your session!</em> |
| public | <strong>pushRegister(</strong><em>mixed</em> <strong>$gcmToken</strong>)</strong> : <em>mixed</em><br /><em>Register to the mqtt push server. TODO: NOT IMPLEMENTED YET!</em> |
| public | <strong>removeProfilePicture()</strong> : <em>[\InstagramAPI\Response\UserInfoResponse](#class-instagramapiresponseuserinforesponse)</em><br /><em>Remove your account's profile picture.</em> |
| public | <strong>removeSelfTag(</strong><em>string</em> <strong>$mediaId</strong>)</strong> : <em>[\InstagramAPI\Response](#class-instagramapiresponse)\MediaResponse</em><br /><em>Remove yourself from a tagged media item.</em> |
| public | <strong>reportExploreMedia(</strong><em>string</em> <strong>$exploreSourceToken</strong>, <em>string</em> <strong>$userId</strong>)</strong> : <em>[\InstagramAPI\Response\ReportExploreMediaResponse](#class-instagramapiresponsereportexploremediaresponse)</em><br /><em>Report media in the Explore-feed.</em> |
| public | <strong>request(</strong><em>string</em> <strong>$url</strong>)</strong> : <em>[\InstagramAPI\Request](#class-instagramapirequest)</em><br /><em>Create a custom API request. Used internally, but can also be used by end-users if they want to create completely custom API queries without modifying this library.</em> |
| public | <strong>requestTwoFactor(</strong><em>string</em> <strong>$phoneNumber</strong>)</strong> : <em>[\InstagramAPI\Response\RequestTwoFactorResponse](#class-instagramapiresponserequesttwofactorresponse)</em><br /><em>Sends a SMS to your phone number. The SMS have a verification code that will be used to enable two factor authentication in your account.</em> |
| public | <strong>saveMedia(</strong><em>string</em> <strong>$mediaId</strong>)</strong> : <em>[\InstagramAPI\Response\SaveAndUnsaveMedia](#class-instagramapiresponsesaveandunsavemedia)</em><br /><em>Save a media item.</em> |
| public | <strong>searchFBLocation(</strong><em>string</em> <strong>$query</strong>, <em>int</em> <strong>$count=null</strong>)</strong> : <em>[\InstagramAPI\Response\FBLocationResponse](#class-instagramapiresponsefblocationresponse)</em><br /><em>Search for Facebook locations by name.</em> |
| public | <strong>searchFBLocationByPoint(</strong><em>string</em> <strong>$lat</strong>, <em>string</em> <strong>$lng</strong>)</strong> : <em>[\InstagramAPI\Response\FBLocationResponse](#class-instagramapiresponsefblocationresponse)</em><br /><em>Search for Facebook locations by geographical location.</em> |
| public | <strong>searchFBUsers(</strong><em>string</em> <strong>$query</strong>)</strong> : <em>[\InstagramAPI\Response\FBSearchResponse](#class-instagramapiresponsefbsearchresponse)</em><br /><em>Facebook user search.</em> |
| public | <strong>searchInAddressBook(</strong><em>array</em> <strong>$contacts</strong>)</strong> : <em>[\InstagramAPI\Response\AddressBookResponse](#class-instagramapiresponseaddressbookresponse)</em><br /><em>Search for users via address book.</em> |
| public | <strong>searchLocation(</strong><em>string</em> <strong>$latitude</strong>, <em>string</em> <strong>$longitude</strong>, <em>null/string</em> <strong>$query=null</strong>)</strong> : <em>[\InstagramAPI\Response\LocationResponse](#class-instagramapiresponselocationresponse)</em><br /><em>Search for nearby Instagram locations by geographical coordinates.</em> |
| public | <strong>searchRelatedLocation(</strong><em>string</em> <strong>$locationId</strong>)</strong> : <em>[\InstagramAPI\Response\RelatedLocationResponse](#class-instagramapiresponserelatedlocationresponse)</em><br /><em>Search for related locations by location ID.</em> |
| public | <strong>searchTags(</strong><em>string</em> <strong>$query</strong>)</strong> : <em>[\InstagramAPI\Response\SearchTagResponse](#class-instagramapiresponsesearchtagresponse)</em><br /><em>Search for tags.</em> |
| public | <strong>searchUsers(</strong><em>string</em> <strong>$query</strong>)</strong> : <em>[\InstagramAPI\Response\SearchUserResponse](#class-instagramapiresponsesearchuserresponse)</em><br /><em>Search for Instagram users.</em> |
| public | <strong>sendConfirmEmail()</strong> : <em>[\InstagramAPI\Response\SendConfirmEmailResponse](#class-instagramapiresponsesendconfirmemailresponse)</em><br /><em>Send a confirmation to verify your email.</em> |
| public | <strong>setNameAndPhone(</strong><em>string</em> <strong>$name=`''`</strong>, <em>string</em> <strong>$phone=`''`</strong>)</strong> : <em>[\InstagramAPI\Response](#class-instagramapiresponse)</em><br /><em>Set your account's first name and phone (optional).</em> |
| public | <strong>setOutputInterface(</strong><em>mixed</em> <strong>$value</strong>)</strong> : <em>void</em><br /><em>Sets the network interface override to use. Only works if Guzzle is using the cURL backend. But that's almost always the case, on most PHP installations.</em> |
| public | <strong>setPrivateAccount()</strong> : <em>[\InstagramAPI\Response\UserInfoResponse](#class-instagramapiresponseuserinforesponse)</em><br /><em>Sets your account to private.</em> |
| public | <strong>setProxy(</strong><em>string/array/null</em> <strong>$value</strong>)</strong> : <em>void</em><br /><em>Set the proxy to use for requests.</em> |
| public | <strong>setPublicAccount()</strong> : <em>[\InstagramAPI\Response\UserInfoResponse](#class-instagramapiresponseuserinforesponse)</em><br /><em>Sets your account to public.</em> |
| public | <strong>setUser(</strong><em>string</em> <strong>$username</strong>, <em>string</em> <strong>$password</strong>)</strong> : <em>void</em><br /><em>Set the active account for the class instance. You can call this multiple times to switch between multiple accounts.</em> |
| public | <strong>setVerifySSL(</strong><em>bool/string</em> <strong>$state</strong>)</strong> : <em>void</em><br /><em>Controls the SSL verification behavior of the Client.</em> |
| public | <strong>syncFeatures(</strong><em>bool</em> <strong>$prelogin=false</strong>)</strong> : <em>[\InstagramAPI\Response\SyncResponse](#class-instagramapiresponsesyncresponse)</em><br /><em>Perform an Instagram "feature synchronization" call.</em> |
| public | <strong>tagUser(</strong><em>string</em> <strong>$mediaId</strong>, <em>string</em> <strong>$userId</strong>, <em>array/float</em> <strong>$position</strong>, <em>string</em> <strong>$captionText=`''`</strong>)</strong> : <em>[\InstagramAPI\Response\EditMediaResponse](#class-instagramapiresponseeditmediaresponse)</em><br /><em>Tag a user in a media item.</em> |
| public | <strong>twoFactorLogin(</strong><em>string</em> <strong>$verificationCode</strong>, <em>string</em> <strong>$twoFactorIdentifier</strong>)</strong> : <em>[\InstagramAPI\Response\LoginResponse](#class-instagramapiresponseloginresponse)</em><br /><em>Login to Instagram using two factor authentication.</em> |
| public | <strong>unblock(</strong><em>string</em> <strong>$userId</strong>)</strong> : <em>[\InstagramAPI\Response\FriendshipResponse](#class-instagramapiresponsefriendshipresponse)</em><br /><em>Unblock a user.</em> |
| public | <strong>unblockFriendStory(</strong><em>string</em> <strong>$userId</strong>)</strong> : <em>[\InstagramAPI\Response\FriendshipResponse](#class-instagramapiresponsefriendshipresponse)</em><br /><em>Unblock a user from viewing your story.</em> |
| public | <strong>unfollow(</strong><em>string</em> <strong>$userId</strong>)</strong> : <em>[\InstagramAPI\Response\FriendshipResponse](#class-instagramapiresponsefriendshipresponse)</em><br /><em>Unfollow.</em> |
| public | <strong>unlike(</strong><em>string</em> <strong>$mediaId</strong>)</strong> : <em>[\InstagramAPI\Response](#class-instagramapiresponse)</em><br /><em>Unlike a media item.</em> |
| public | <strong>unlikeComment(</strong><em>string</em> <strong>$commentId</strong>)</strong> : <em>[\InstagramAPI\Response\CommentLikeUnlikeResponse](#class-instagramapiresponsecommentlikeunlikeresponse)</em><br /><em>Unlike a comment.</em> |
| public | <strong>unsaveMedia(</strong><em>string</em> <strong>$mediaId</strong>)</strong> : <em>[\InstagramAPI\Response\SaveAndUnsaveMedia](#class-instagramapiresponsesaveandunsavemedia)</em><br /><em>Unsave a media item.</em> |
| public | <strong>untagUser(</strong><em>string</em> <strong>$mediaId</strong>, <em>string</em> <strong>$userId</strong>, <em>string</em> <strong>$captionText=`''`</strong>)</strong> : <em>[\InstagramAPI\Response\EditMediaResponse](#class-instagramapiresponseeditmediaresponse)</em><br /><em>Untag a user from a media item.</em> |
| public | <strong>uploadStoryPhoto(</strong><em>string</em> <strong>$photoFilename</strong>, <em>array</em> <strong>$externalMetadata=array()</strong>)</strong> : <em>[\InstagramAPI\Response\ConfigureResponse](#class-instagramapiresponseconfigureresponse)</em><br /><em>Uploads a photo to your Instagram story.</em> |
| public | <strong>uploadStoryVideo(</strong><em>string</em> <strong>$videoFilename</strong>, <em>array</em> <strong>$externalMetadata=array()</strong>, <em>int</em> <strong>$maxAttempts=10</strong>)</strong> : <em>[\InstagramAPI\Response\ConfigureResponse](#class-instagramapiresponseconfigureresponse)</em><br /><em>Uploads a video to your Instagram story.</em> |
| public | <strong>uploadTimelineAlbum(</strong><em>array</em> <strong>$media</strong>, <em>array</em> <strong>$externalMetadata=array()</strong>, <em>int</em> <strong>$maxAttempts=10</strong>)</strong> : <em>[\InstagramAPI\Response\ConfigureResponse](#class-instagramapiresponseconfigureresponse)</em><br /><em>Uploads an album to your Instagram timeline. An album is also known as a "carousel" and "sidecar". They can contain up to 10 photos or videos (at the moment). metadata (type, file, and optionally usertags). The "type" must be "photo" or "video". The "file" must be its disk path. And the optional "usertags" can only be used on PHOTOS, never on videos. for the album itself (its caption, location, etc).</em> |
| public | <strong>uploadTimelinePhoto(</strong><em>string</em> <strong>$photoFilename</strong>, <em>array</em> <strong>$externalMetadata=array()</strong>)</strong> : <em>[\InstagramAPI\Response\ConfigureResponse](#class-instagramapiresponseconfigureresponse)</em><br /><em>Uploads a photo to your Instagram timeline.</em> |
| public | <strong>uploadTimelineVideo(</strong><em>string</em> <strong>$videoFilename</strong>, <em>array</em> <strong>$externalMetadata=array()</strong>, <em>int</em> <strong>$maxAttempts=10</strong>)</strong> : <em>[\InstagramAPI\Response\ConfigureResponse](#class-instagramapiresponseconfigureresponse)</em><br /><em>Uploads a video to your Instagram timeline.</em> |
| protected | <strong>_getSignupChallenge()</strong> : <em>[\InstagramAPI\Response\ChallengeResponse](#class-instagramapiresponsechallengeresponse)</em><br /><em>Signup challenge is used to get _csrftoken in order to make a successful login or registration request.</em> |
| protected | <strong>_sendLoginFlow(</strong><em>bool</em> <strong>$justLoggedIn</strong>, <em>int</em> <strong>$appRefreshInterval=1800</strong>)</strong> : <em>void</em><br /><em>Sends login flow. This is required to emulate real device behavior.</em> |
| protected | <strong>_uploadSinglePhoto(</strong><em>string</em> <strong>$targetFeed</strong>, <em>string</em> <strong>$photoFilename</strong>, <em>array</em> <strong>$externalMetadata=array()</strong>)</strong> : <em>[\InstagramAPI\Response\ConfigureResponse](#class-instagramapiresponseconfigureresponse)</em><br /><em>INTERNAL. UPLOADS A *SINGLE* PHOTO. but NOT "album", they are handled elsewhere).</em> |
| protected | <strong>_uploadSingleVideo(</strong><em>string</em> <strong>$targetFeed</strong>, <em>string</em> <strong>$videoFilename</strong>, <em>array</em> <strong>$externalMetadata=array()</strong>, <em>int</em> <strong>$maxAttempts=10</strong>)</strong> : <em>[\InstagramAPI\Response\ConfigureResponse](#class-instagramapiresponseconfigureresponse)</em><br /><em>INTERNAL. UPLOADS A *SINGLE* VIDEO. but NOT "album", they are handled elsewhere).</em> |

---
### Class: \InstagramAPI\InstagramID

> Class for converting media IDs to/from Instagram's shortcode system. The shortcode is the https://instagram.com/p/SHORTCODE/ part of the URL. There are many reasons why you would want to be able to convert back and forth between shortcodes and internal ID numbers. This library helps you!

| Visibility | Function |
|:-----------|:---------|
| public static | <strong>base10to2(</strong><em>string/int</em> <strong>$base10</strong>, <em>bool</em> <strong>$padLeft=true</strong>)</strong> : <em>string The binary bits as a string.</em><br /><em>Converts a decimal number of any size into a binary string. a positive integer. And you must pass the number as a string if you want to convert a number that's larger than what fits in your CPU's integer size.</em> |
| public static | <strong>base2to10(</strong><em>string</em> <strong>$base2</strong>)</strong> : <em>string The decimal number as a string.</em><br /><em>Converts a binary number of any size into a decimal string. either "1" or "0".</em> |
| public static | <strong>buildBinaryLookupTable(</strong><em>int</em> <strong>$maxBitCount</strong>)</strong> : <em>array The lookup table, where offset has the value of bit 1, offset 1 has the value of bit 2, and so on.</em><br /><em>Builds a binary bit-value lookup table.</em> |
| public static | <strong>fromCode(</strong><em>string</em> <strong>$code</strong>)</strong> : <em>string The numeric ID.</em><br /><em>Converts an Instagram shortcode to a numeric ID.</em> |
| public static | <strong>toCode(</strong><em>string/int</em> <strong>$id</strong>)</strong> : <em>string The shortcode.</em><br /><em>Converts an Instagram ID to their shortcode system. it's larger than the size of an integer, which MOST Instagram IDs are!</em> |

---
### Class: \InstagramAPI\Request

> Bridge between Instagram Client calls, the object mapper & Response objects.

| Visibility | Function |
|:-----------|:---------|
| public | <strong>__construct(</strong><em>[\InstagramAPI\Instagram](#class-instagramapiinstagram)</em> <strong>$parent</strong>, <em>mixed</em> <strong>$url</strong>)</strong> : <em>void</em> |
| public | <strong>addParams(</strong><em>mixed</em> <strong>$key</strong>, <em>mixed</em> <strong>$value</strong>)</strong> : <em>void</em> |
| public | <strong>addPost(</strong><em>mixed</em> <strong>$key</strong>, <em>mixed</em> <strong>$value</strong>)</strong> : <em>void</em> |
| public | <strong>getResponse(</strong><em>mixed</em> <strong>$baseClass</strong>, <em>bool</em> <strong>$includeHeader=false</strong>)</strong> : <em>mixed</em> |
| public | <strong>setCheckStatus(</strong><em>bool</em> <strong>$checkStatus=true</strong>)</strong> : <em>void</em> |
| public | <strong>setNeedsAuth(</strong><em>bool</em> <strong>$needsAuth=true</strong>)</strong> : <em>void</em> |
| public | <strong>setSignedPost(</strong><em>bool</em> <strong>$signedPost=true</strong>)</strong> : <em>void</em> |

---
### Class: \InstagramAPI\Response

| Visibility | Function |
|:-----------|:---------|
| public | <strong>__construct()</strong> : <em>void</em> |
| public | <strong>getFullResponse()</strong> : <em>mixed</em> |
| public | <strong>getMessage()</strong> : <em>string/null A message string if one exists, otherwise NULL.</em><br /><em>Gets the message.</em> |
| public | <strong>getStatus()</strong> : <em>mixed</em> |
| public | <strong>isOk()</strong> : <em>bool</em> |
| public | <strong>setFullResponse(</strong><em>mixed</em> <strong>$response</strong>)</strong> : <em>void</em> |
| public | <strong>setMessage(</strong><em>mixed</em> <strong>$message</strong>)</strong> : <em>void</em> |
| public | <strong>setStatus(</strong><em>mixed</em> <strong>$status</strong>)</strong> : <em>void</em> |

*This class extends [\InstagramAPI\AutoPropertyHandler](#class-instagramapiautopropertyhandler)*

---
### Class: \InstagramAPI\Signatures

| Visibility | Function |
|:-----------|:---------|
| public static | <strong>generateDeviceId()</strong> : <em>void</em> |
| public static | <strong>generateSignature(</strong><em>mixed</em> <strong>$data</strong>)</strong> : <em>void</em> |
| public static | <strong>generateSignatureForPost(</strong><em>mixed</em> <strong>$data</strong>)</strong> : <em>void</em> |
| public static | <strong>generateUUID(</strong><em>bool</em> <strong>$keepDashes=true</strong>)</strong> : <em>void</em> |

---
### Class: \InstagramAPI\Utils

| Visibility | Function |
|:-----------|:---------|
| public static | <strong>checkFFMPEG()</strong> : <em>string/bool Name of the library if present, otherwise FALSE.</em><br /><em>Check for ffmpeg/avconv dependencies.</em> |
| public static | <strong>checkFFPROBE()</strong> : <em>string/bool Name of the library if present, otherwise FALSE.</em><br /><em>Check for ffprobe dependency.</em> |
| public static | <strong>colouredString(</strong><em>mixed</em> <strong>$string</strong>, <em>mixed</em> <strong>$colour</strong>)</strong> : <em>void</em> |
| public static | <strong>createVideoIcon(</strong><em>string</em> <strong>$videoFilename</strong>)</strong> : <em>string The JPEG binary data for the generated thumbnail.</em><br /><em>Generate a video icon/thumbnail from a video file. Automatically guarantees that the generated image follows Instagram's allowed image specifications, so that there won't be any upload issues.</em> |
| public static | <strong>formatBytes(</strong><em>mixed</em> <strong>$bytes</strong>, <em>mixed</em> <strong>$precision=2</strong>)</strong> : <em>void</em> |
| public static | <strong>generateUploadId()</strong> : <em>string</em> |
| public static | <strong>generateUserBreadcrumb(</strong><em>mixed</em> <strong>$size</strong>)</strong> : <em>string</em><br /><em>Generates user breadcrumb for use when posting a comment.</em> |
| public static | <strong>getFilterCode(</strong><em>mixed</em> <strong>$filter</strong>)</strong> : <em>mixed</em> |
| public static | <strong>getVideoFileDetails(</strong><em>string</em> <strong>$videoFilename</strong>)</strong> : <em>array Video codec name, float duration, int width and height.</em><br /><em>Get detailed information about a video file. This also validates that a file is actually a video, since FFmpeg will fail to read details from badly broken / non-video files.</em> |
| public static | <strong>throwIfIllegalMediaResolution(</strong><em>string</em> <strong>$targetFeed</strong>, <em>string</em> <strong>$fileType</strong>, <em>string</em> <strong>$mediaFilename</strong>, <em>int/float</em> <strong>$width</strong>, <em>int/float</em> <strong>$height</strong>)</strong> : <em>void</em><br /><em>Verifies that a piece of media follows Instagram's size/aspect rules. Currently all photos and videos everywhere have the exact same rules. We bring in the up-to-date rules from the ImageAutoResizer class.</em> |
| public static | <strong>throwIfIllegalVideoDetails(</strong><em>string</em> <strong>$targetFeed</strong>, <em>string</em> <strong>$videoFilename</strong>, <em>array</em> <strong>$videoDetails</strong>)</strong> : <em>void</em><br /><em>Verifies that a video's details follow Instagram's requirements.</em> |

---
### Class: \InstagramAPI\Devices\Device

> Android hardware device representation.

| Visibility | Function |
|:-----------|:---------|
| public | <strong>__construct(</strong><em>string</em> <strong>$appVersion</strong>, <em>string</em> <strong>$userLocale</strong>, <em>string/null</em> <strong>$deviceString=null</strong>, <em>bool</em> <strong>$autoFallback=true</strong>)</strong> : <em>void</em><br /><em>Constructor. to construct from. If NULL or not a good device, we'll use a random good device.</em> |
| public | <strong>getAndroidRelease()</strong> : <em>mixed</em> |
| public | <strong>getAndroidVersion()</strong> : <em>mixed</em> |
| public | <strong>getBrand()</strong> : <em>mixed</em> |
| public | <strong>getCPU()</strong> : <em>mixed</em> |
| public | <strong>getDPI()</strong> : <em>mixed</em> |
| public | <strong>getDevice()</strong> : <em>mixed</em> |
| public | <strong>getDeviceString()</strong> : <em>mixed</em> |
| public | <strong>getManufacturer()</strong> : <em>mixed</em> |
| public | <strong>getModel()</strong> : <em>mixed</em> |
| public | <strong>getResolution()</strong> : <em>mixed</em> |
| public | <strong>getUserAgent()</strong> : <em>mixed</em> |
| protected | <strong>_initFromDeviceString(</strong><em>string</em> <strong>$deviceString</strong>)</strong> : <em>void</em><br /><em>Parses a device string into its component parts and sets internal fields. Does no validation to make sure the string is one of the good devices.</em> |

---
### Class: \InstagramAPI\Devices\GoodDevices

> Internal list of verified Android devices.

| Visibility | Function |
|:-----------|:---------|
| public static | <strong>getAllGoodDevices()</strong> : <em>string[]</em><br /><em>Retrieve all good devices.</em> |
| public static | <strong>getRandomGoodDevice()</strong> : <em>string</em><br /><em>Retrieve the device string for a random good device.</em> |
| public static | <strong>isGoodDevice(</strong><em>string</em> <strong>$deviceString</strong>)</strong> : <em>bool</em><br /><em>Checks whether a device string is one of the good devices.</em> |

---
### Class: \InstagramAPI\Devices\UserAgent

> Android device User-Agent builder.

| Visibility | Function |
|:-----------|:---------|
| public static | <strong>buildUserAgent(</strong><em>string</em> <strong>$appVersion</strong>, <em>string</em> <strong>$userLocale</strong>, <em>[\InstagramAPI\Devices\Device](#class-instagramapidevicesdevice)</em> <strong>$device</strong>)</strong> : <em>string</em><br /><em>Generates a User Agent string from a Device.</em> |

---
### Class: \InstagramAPI\Exception\AccountDisabledException

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Exception\RequestException](#class-instagramapiexceptionrequestexception)*

*This class implements [\InstagramAPI\Exception\InstagramException](#interface-instagramapiexceptioninstagramexception), \Throwable*

---
### Class: \InstagramAPI\Exception\CheckpointRequiredException

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Exception\RequestException](#class-instagramapiexceptionrequestexception)*

*This class implements [\InstagramAPI\Exception\InstagramException](#interface-instagramapiexceptioninstagramexception), \Throwable*

---
### Class: \InstagramAPI\Exception\EmptyResponseException

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Exception\RequestException](#class-instagramapiexceptionrequestexception)*

*This class implements [\InstagramAPI\Exception\InstagramException](#interface-instagramapiexceptioninstagramexception), \Throwable*

---
### Class: \InstagramAPI\Exception\EndpointException

> All general API function call "server response" failures use this exception. The server-side Instagram API functions are called "endpoints", and they all perform very different tasks and have hundreds of different function-specific error messages (which may change at any time). Instead of us trying to handle all of them (which would be slow and stupid), we throw them to the user as an EndpointException, so that it's up to the users to handle any specific error strings they want to catch in their own projects. Encapsulates ALL function-call specific problems such as "User not found" and so on. To see what happened, simply getMessage() on this exception.

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Exception\RequestException](#class-instagramapiexceptionrequestexception)*

*This class implements [\InstagramAPI\Exception\InstagramException](#interface-instagramapiexceptioninstagramexception), \Throwable*

---
### Class: \InstagramAPI\Exception\FeedbackRequiredException

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Exception\RequestException](#class-instagramapiexceptionrequestexception)*

*This class implements [\InstagramAPI\Exception\InstagramException](#interface-instagramapiexceptioninstagramexception), \Throwable*

---
### Class: \InstagramAPI\Exception\ForcedPasswordResetException

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Exception\RequestException](#class-instagramapiexceptionrequestexception)*

*This class implements [\InstagramAPI\Exception\InstagramException](#interface-instagramapiexceptioninstagramexception), \Throwable*

---
### Class: \InstagramAPI\Exception\IncorrectPasswordException

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Exception\RequestException](#class-instagramapiexceptionrequestexception)*

*This class implements [\InstagramAPI\Exception\InstagramException](#interface-instagramapiexceptioninstagramexception), \Throwable*

---
### Interface: \InstagramAPI\Exception\InstagramException

> The core exception interface that ALL other library exceptions derive from. If you catch this exception, you KNOW it came from our Instagram-API library.

| Visibility | Function |
|:-----------|:---------|

---
### Class: \InstagramAPI\Exception\InternalException

> All internally generated non-server exceptions must derive from this class.

| Visibility | Function |
|:-----------|:---------|

*This class extends \RuntimeException*

*This class implements \Throwable, [\InstagramAPI\Exception\InstagramException](#interface-instagramapiexceptioninstagramexception)*

---
### Class: \InstagramAPI\Exception\InvalidUserException

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Exception\RequestException](#class-instagramapiexceptionrequestexception)*

*This class implements [\InstagramAPI\Exception\InstagramException](#interface-instagramapiexceptioninstagramexception), \Throwable*

---
### Class: \InstagramAPI\Exception\LoginRequiredException

> Used when the server requires us to login again, and also used as a locally triggered exception when we know for sure that we aren't logged in.

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Exception\RequestException](#class-instagramapiexceptionrequestexception)*

*This class implements [\InstagramAPI\Exception\InstagramException](#interface-instagramapiexceptioninstagramexception), \Throwable*

---
### Class: \InstagramAPI\Exception\NetworkException

> This exception re-wraps ALL networking/socket exceptions. Currently (and probably forever) we're using the great Guzzle library for all network communication. So this exception is used for re-wrapping their exceptions into something derived from our own base InstagramException instead, to make life much easier for our users (that way they only have to catch our base exception in their projects, and won't have to also catch Guzzle's various exceptions). It also ensures that users get a proper stack-trace showing which area of OUR code threw the exception, instead of some useless line of GUZZLE'S code. The message we use is the same as the message of the Guzzle exception, but nicely formatted to begin with "Network: " and to always end in punctuation that forms complete English sentences, so that the exception message is ready for display in user-facing applications. And if you (the programmer) want extra details that were included in Guzzle's exception, you can simply use "getGuzzleException()" on this NetworkException to get the original Guzzle exception instead, which has more networking information, such as the failed HTTP request that was attempted.

| Visibility | Function |
|:-----------|:---------|
| public | <strong>__construct(</strong><em>[\Exception](http://php.net/manual/en/class.exception.php)</em> <strong>$guzzleException</strong>)</strong> : <em>void</em><br /><em>Constructor.</em> |
| public | <strong>getGuzzleException()</strong> : <em>[\Exception](http://php.net/manual/en/class.exception.php) The original Guzzle exception.</em><br /><em>Gets the original Guzzle exception, which contains much more details.</em> |

*This class extends [\InstagramAPI\Exception\RequestException](#class-instagramapiexceptionrequestexception)*

*This class implements [\InstagramAPI\Exception\InstagramException](#interface-instagramapiexceptioninstagramexception), \Throwable*

---
### Class: \InstagramAPI\Exception\RequestException

> All server-response API related exceptions must derive from this class.

| Visibility | Function |
|:-----------|:---------|

*This class extends \RuntimeException*

*This class implements \Throwable, [\InstagramAPI\Exception\InstagramException](#interface-instagramapiexceptioninstagramexception)*

---
### Class: \InstagramAPI\Exception\SentryBlockException

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Exception\RequestException](#class-instagramapiexceptionrequestexception)*

*This class implements [\InstagramAPI\Exception\InstagramException](#interface-instagramapiexceptioninstagramexception), \Throwable*

---
### Class: \InstagramAPI\Exception\ServerMessageThrower

> Parses Instagram's API error messages and throws an appropriate exception.

| Visibility | Function |
|:-----------|:---------|
| public static | <strong>autoThrow(</strong><em>string/null</em> <strong>$prefixString</strong>, <em>string</em> <strong>$serverMessage</strong>)</strong> : <em>void</em><br /><em>Parses a server message and throws the appropriate exception. Uses the generic EndpointException if no other exceptions match. the final exception. Should be something helpful such as the name of the class or function which threw. Can be NULL.</em> |
| public static | <strong>prettifyMessage(</strong><em>string</em> <strong>$message</strong>)</strong> : <em>string The cleaned-up message.</em><br /><em>Nicely reformats externally generated exception messages. This is used for guaranteeing consistent message formatting with full English sentences, ready for display to the user.</em> |

---
### Class: \InstagramAPI\Exception\SettingsException

> Used for all problems with the Settings storage.

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Exception\InternalException](#class-instagramapiexceptioninternalexception)*

*This class implements [\InstagramAPI\Exception\InstagramException](#interface-instagramapiexceptioninstagramexception), \Throwable*

---
### Class: \InstagramAPI\Exception\ThrottledException

> Means that you have become throttled by Instagram's API server because of too many requests. You must slow yourself down!

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Exception\RequestException](#class-instagramapiexceptionrequestexception)*

*This class implements [\InstagramAPI\Exception\InstagramException](#interface-instagramapiexceptioninstagramexception), \Throwable*

---
### Class: \InstagramAPI\Exception\UploadFailedException

> Used when we know for a fact that our uploads failed. However, this is not the only type of exception used for failed uploads/API communication. There can also be lower-level Guzzle HTTP exceptions.

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Exception\RequestException](#class-instagramapiexceptionrequestexception)*

*This class implements [\InstagramAPI\Exception\InstagramException](#interface-instagramapiexceptioninstagramexception), \Throwable*

---
### Class: \InstagramAPI\Response\AccountSecurityInfoResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\ActivityNewsResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\AddressBookResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\AutoCompleteUserListResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\BroadcastCommentsResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\BroadcastHeartbeatAndViewerCountResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\BroadcastInfoResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\BroadcastLikeCountResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\BroadcastLikeResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\ChallengeResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\ChangePasswordResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\CommentBroadcastResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\CommentLikeUnlikeResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\CommentResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\ConfigureResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\DeleteCommentResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\DirectShareInboxResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\DirectThreadResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\DisableTwoFactorResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\DiscoverChannelsResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\DiscoverTopLiveResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\EditMediaResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\EnableTwoFactorResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\ExploreResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\ExposeResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\FacebookOTAResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\FBLocationResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\FBSearchResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\FollowerAndFollowingResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\FollowingRecentActivityResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\FriendshipResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\FriendshipsShowManyResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\GeoMediaResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\InsightsResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\LikeFeedResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\LocationFeedResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\LocationResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\LoginResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\LogoutResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\MediaCommentsResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\MediaDeleteResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\MediaInfoResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\MediaInsightsResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\MediaLikersResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\MegaphoneLogResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\PendingInboxResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\PopularFeedResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\RankedRecipientsResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\RecentRecipientsResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\ReelsMediaResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\ReelsTrayFeedResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\RelatedLocationResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\ReportExploreMediaResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\RequestTwoFactorResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\SaveAndUnsaveMedia

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\SavedFeedResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\SearchTagResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\SearchUserResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\SendConfirmEmailResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\StickerAssetsResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\SuggestedBroadcastsResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\SuggestedUsersResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\SyncResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\TagFeedResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\TagInfoResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\TagRelatedResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\TimelineFeedResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\TopLiveStatusResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\UploadJobVideoResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\UploadPhotoResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\UploadVideoResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\UserFeedResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\UserInfoResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\UserStoryFeedResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\UsertagsResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\V2InboxResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\VisualInboxResponse

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\_Message

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\ActionLog

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\Args

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\Attribution

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\Bold

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\Broadcast

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\BroadcastItem

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\BroadcastOwner

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\BroadcastStatusItem

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\Caption

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\CarouselMedia

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\Channel

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\Comment

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\Counts

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\Experiment

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\Explore

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\ExploreItem

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\FeedAysf

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\FriendshipStatus

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\Gating

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\GeoMedia

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\HdProfilePicUrlInfo

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\Image_Versions2

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\In

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\Inbox

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\InlineFollow

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\Insights

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\Item

| Visibility | Function |
|:-----------|:---------|
| public | <strong>getItemUrl()</strong> : <em>mixed</em> |
| public | <strong>setMediaOrAd(</strong><em>mixed</em> <strong>$params</strong>)</strong> : <em>void</em> |

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\Link

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\Location

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\LocationItem

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\Media

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\MediaInsights

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\Param

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\PhoneVerificationSettings

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\Position

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\RankedRecipient

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\Reel

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\Related

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\SavedFeedItem

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\StaticStickers

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\Stickers

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\Stories

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\Story

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\StoryLocation

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\Subscription

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\SuggestedUsers

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\Suggestion

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\Tag

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\Thread

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\ThreadItem

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\ThreadItemMedia

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\ThreadLastSeenAt

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\TopLive

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\Tray

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\TwoFactorInfo

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\User

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\Users

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\Usertag

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Response\Model\VideoVersions

| Visibility | Function |
|:-----------|:---------|

*This class extends [\InstagramAPI\Response](#class-instagramapiresponse)*

---
### Class: \InstagramAPI\Settings\Factory

> Effortlessly instantiates a StorageHandler with the desired Storage backend. Takes care of resolving user configuration values from multiple sources, then creates the correct Storage backend and hooks it up to a StorageHandler.

| Visibility | Function |
|:-----------|:---------|
| public static | <strong>createHandler(</strong><em>array</em> <strong>$storageConfig</strong>)</strong> : <em>[\InstagramAPI\Settings\StorageHandler](#class-instagramapisettingsstoragehandler)</em><br /><em>Create a StorageHandler instance. user settings storage backend.</em> |
| public static | <strong>getCmdOptions(</strong><em>array</em> <strong>$longOpts</strong>)</strong> : <em>array</em><br /><em>Get option values via command-line parameters.</em> |
| public static | <strong>getUserConfig(</strong><em>string</em> <strong>$settingName</strong>, <em>array</em> <strong>$storageConfig</strong>, <em>array</em> <strong>$cmdOptions</strong>)</strong> : <em>string/null The value if found, otherwise NULL.</em><br /><em>Looks for the highest-priority result for a Storage config value.</em> |

---
### Class: \InstagramAPI\Settings\StorageHandler

> Advanced, modular settings storage engine. Connects to a StorageInterface and transfers data to/from the application, with intelligent caching and data translation.

| Visibility | Function |
|:-----------|:---------|
| public | <strong>__construct(</strong><em>mixed</em> <strong>$storageInstance</strong>, <em>array</em> <strong>$locationConfig=array()</strong>)</strong> : <em>void</em><br /><em>Constructor. the storage backend location.</em> |
| public | <strong>__destruct()</strong> : <em>void</em><br /><em>Destructor.</em> |
| public | <strong>deleteUser(</strong><em>string</em> <strong>$username</strong>)</strong> : <em>void</em><br /><em>Delete all internal data for a given username.</em> |
| public | <strong>get(</strong><em>string</em> <strong>$key</strong>)</strong> : <em>string/null The value as a string IF the setting exists AND is a NON-EMPTY string. Otherwise NULL.</em><br /><em>Retrieve the value of a setting from the current user's memory cache. Can only be executed after setActiveUser().</em> |
| public | <strong>getCookies()</strong> : <em>array Cookies with their "format" ("cookiefile", "cookiestring") and a "data" field pointing to the file (if "cookiefile") or containing the raw cookie data (if "cookiestring"). The cookiestring will be an empty string if no cookies exist.</em><br /><em>Get all cookies for the currently active user. Can only be executed after setActiveUser().</em> |
| public | <strong>hasCookies()</strong> : <em>bool TRUE if cookies exist, otherwise FALSE.</em><br /><em>Whether the storage backend has cookies for the currently active user. Can only be executed after setActiveUser().</em> |
| public | <strong>hasUser(</strong><em>string</em> <strong>$username</strong>)</strong> : <em>bool TRUE if user exists, otherwise FALSE.</em><br /><em>Whether the storage backend contains a specific user.</em> |
| public | <strong>isMaybeLoggedIn()</strong> : <em>bool TRUE if possibly logged in, otherwise FALSE.</em><br /><em>Does a preliminary guess about whether the current user is logged in. Can only be executed after setActiveUser(). And the session it looks for may be expired, so there's no guarantee that we are still logged in.</em> |
| public | <strong>moveUser(</strong><em>string</em> <strong>$oldUsername</strong>, <em>string</em> <strong>$newUsername</strong>)</strong> : <em>void</em><br /><em>Move the internal data for a username to a new username. This function is important because of the fact that all per-user settings in all Storage implementations are retrieved and stored via its Instagram username, since their NAME is literally the ONLY thing we know about a user before we have loaded their settings or logged in! So if you later rename that Instagram account, it means that your old device settings WON'T follow along automatically, since the new login username is seen as a brand new user that isn't in the settings storage. This function conveniently tells your chosen Storage backend to move a user's settings to a new name, so that they WILL be found again when you later look for settings for your new name. Bonus guide for easily confused people: YOU must manually rename your user on Instagram.com before you call this function. We don't do that.</em> |
| public | <strong>set(</strong><em>string</em> <strong>$key</strong>, <em>string/mixed</em> <strong>$value</strong>)</strong> : <em>void</em><br /><em>Store a setting's value for the current user. Can only be executed after setActiveUser(). To clear the value of a setting, simply pass in an empty string as value.</em> |
| public | <strong>setActiveUser(</strong><em>string</em> <strong>$username</strong>)</strong> : <em>void</em><br /><em>Load all settings for a user from the storage and mark as current user.</em> |
| public | <strong>setCookies(</strong><em>string</em> <strong>$rawData</strong>)</strong> : <em>void</em><br /><em>Save all cookies for the currently active user. Can only be executed after setActiveUser(). Note that this function is called frequently! But it is ONLY called if a non-"cookiefile" answer was returned by the getCookies() call.</em> |
| protected | <strong>_throwIfEmptyValue(</strong><em>mixed</em> <strong>$value</strong>)</strong> : <em>void</em><br /><em>Internal: Ensures that a parameter is a non-empty string.</em> |
| protected | <strong>_throwIfNoActiveUser()</strong> : <em>void</em><br /><em>Internal: Ensures that there is an active storage user.</em> |
| protected | <strong>_throwIfNotString(</strong><em>mixed</em> <strong>$value</strong>)</strong> : <em>void</em><br /><em>Internal: Ensures that a parameter is a string.</em> |

---
### Interface: \InstagramAPI\Settings\StorageInterface

> Data Storage Interface. These methods must be implemented by all storage backends. All of their input and output validation is already done by the owning Settings class, so that backends can focus on dealing with basic, fully verified data (instead of writing and maintaining a bunch of boilerplate code to verify parameters). All functions in this file are listed in roughly the sequence they're called during normal operation. You can completely trust that they are called in a sane order and that you do not need to validate the call order. -- HOW TO STORE DATA: -- The ONLY datatype we use for settings is STRINGS. You absolutely MUST store ALL data as strings. Do NOT attempt any "fancy" formats such as "database INT columns", because we will OFTEN be storing empty strings in all fields. Your storage backends MUST use STRING storage and MUST allow EMPTY strings. Data length varies, but it's a VERY bad idea for you to cap the length. We may need to store very long data someday. For example, the cookie data that we already store is usually around 2000 characters long. Furthermore, do NOT make ANY assumptions about what settings-"keys/columns" we will be storing. There is a list in StorageHandler::PERSISTENT_KEYS, but it will DEFINITELY change several times in the future. If you hardcode those columns, you will be in trouble in the future. Therefore, the absolute BEST encoding method is to use a SINGLE file/database column for the settings and to JSON-encode everything. And to use a SINGLE file/database column for the cookies and simply store our raw cookie string as-provided. -- MAJOR WARNING: -- Backend developers are NOT allowed to violate ANY aspect of this interface specification. ANY exceptions thrown MUST be of the EXACT types listed, and ALL return values MUST be of the EXACT types listed. This means that YOU will have to handle ALL exceptions thrown by your particular backend solution, and re-wrapping them as the required exceptions if necessary. Otherwise you WILL BREAK all user applications that use your terrible Storage implementation. Just look at our existing Storage implementations to see correct code.

| Visibility | Function |
|:-----------|:---------|
| public | <strong>closeLocation()</strong> : <em>void</em><br /><em>Disconnect from a storage location and perform necessary shutdown steps. This function is called ONCE, when we no longer need to access the currently open storage. But we may still open another storage afterwards, so do NOT treat this as a "class destructor"! Implementing this is optional, but the function must exist.</em> |
| public | <strong>closeUser()</strong> : <em>void</em><br /><em>Close the settings storage for the currently active user. Is called every time we're switching away from a user, BEFORE the new user's loadUserSettings() call. Should be used for doing things like closing previous per-user file handles in the backend, and unsetting the cached user information that was set in the openUser() call. After this call, there will not be any other user-related calls until the next openUser() call.</em> |
| public | <strong>deleteUser(</strong><em>string</em> <strong>$username</strong>)</strong> : <em>void</em><br /><em>Delete all internal data for a given username. Is NEVER called for the currently loaded user, so Storage backend writers can safely assume that you'll never be asked to delete the loaded user. This function MUST treat a non-existent or already deleted user as "success". ONLY throw an exception if ACTUAL deletion fails.</em> |
| public | <strong>hasUser(</strong><em>string</em> <strong>$username</strong>)</strong> : <em>bool TRUE if user exists, otherwise FALSE.</em><br /><em>Whether the storage backend contains a specific user. Having a user is defined as HAVING the USERSETTINGS-portion of the data. The usercookies may be stored separately (such as in a cookiefile) and are NOT essential since they can be re-generated. So the data storage implementation MUST ONLY check for the existence of the USERSETTINGS.</em> |
| public | <strong>hasUserCookies()</strong> : <em>bool TRUE if cookies exist, otherwise FALSE.</em><br /><em>Whether the storage backend has cookies for the currently active user.</em> |
| public | <strong>loadUserCookies()</strong> : <em>string/null Either a "cookiefile:[path]" string to use a file- based cookie jar, otherwise a previously-stored raw cookie data string, or an empty string/NULL if no data exists in the storage yet.</em><br /><em>Load all cookies for the currently active user. If a "cookiefile:[path]" string is returned, the Settings class will use a file-based cookie jar which IT will write to that location. In that case, the Storage class MUST AVOID writing to it, to avoid corruption! Otherwise, simply return the raw cookie data that we previously gave to the storage during a previous session, or an EMPTY STRING (or NULL) if no cookie data exists in the storage yet.</em> |
| public | <strong>loadUserSettings()</strong> : <em>array An array with all current key-value pairs for the user, or an empty array if no settings exist.</em><br /><em>Load all settings for the currently active user.</em> |
| public | <strong>moveUser(</strong><em>string</em> <strong>$oldUsername</strong>, <em>string</em> <strong>$newUsername</strong>)</strong> : <em>void</em><br /><em>Move the internal data for a username to a new username. Is NEVER called for the currently loaded user, so Storage backend writers can safely assume that you'll never be asked to rename the loaded user. Before performing the move, this function MUST validate that the OLD user EXISTS and that the NEW user DOESN'T EXIST, and MUST throw an exception if either of those checks fail. This is to ensure that users don't lose data by accidentally overwriting something.</em> |
| public | <strong>openLocation(</strong><em>array</em> <strong>$locationConfig</strong>)</strong> : <em>void</em><br /><em>Connect to a storage location and perform necessary startup preparations. This function is guaranteed to be called before anything else here. Must do whatever needs to be done BEFORE any per-user data can be loaded from/saved to the storage backend. For example, setting variables, connecting to a database, creating tables, or loading from disk. You can treat this as your "constructor", but you may ALSO want a separate constructor for any work that you DON'T want to repeat every time that you're told to open a different storage location. However, you MUST put ALL per-storage startup code in THIS function, since a normal constructor is only called a single time, as you're aware.</em> |
| public | <strong>openUser(</strong><em>string</em> <strong>$username</strong>)</strong> : <em>void</em><br /><em>Open the data storage for a specific user. If the user does not exist, THIS call MUST create their user storage, or at least do any necessary preparations so that the other functions can read/write to the user's storage (and behave as specified). Is called every time we're switching to a user, and happens before we call any user-specific data retrieval functions. This function must cache the user reference and perform necessary backend operations, such as opening file/database handles and finding the row ID for the given user, so that all further queries know what user to use. All further calls relating to that user will assume that your storage class has cached the user reference we gave you in this call.</em> |
| public | <strong>saveUserCookies(</strong><em>string</em> <strong>$rawData</strong>)</strong> : <em>void</em><br /><em>Save all cookies for the currently active user. Note that this function is called frequently! But it is ONLY called if a non-"cookiefile:" answer was returned by the loadUserCookies() call. If your Storage backend class uses a cookiefile, make this a no-op.</em> |
| public | <strong>saveUserSettings(</strong><em>array</em> <strong>$userSettings</strong>, <em>string</em> <strong>$triggerKey</strong>)</strong> : <em>void</em><br /><em>Save the settings for the currently active user. Is called every time any setting changes. The trigger-key can be used for selectively saving only the modified setting. But most backends should simply JSON-encode the whole $userSettings array and store that string.</em> |

---
### Class: \InstagramAPI\Settings\Storage\File

> Persistent storage backend which keeps settings in a reliable binary file.

| Visibility | Function |
|:-----------|:---------|
| public | <strong>closeLocation()</strong> : <em>void</em><br /><em>Disconnect from a storage location and perform necessary shutdown steps.</em> |
| public | <strong>closeUser()</strong> : <em>void</em><br /><em>Close the settings storage for the currently active user.</em> |
| public | <strong>deleteUser(</strong><em>mixed</em> <strong>$username</strong>)</strong> : <em>void</em><br /><em>Delete all internal data for a given username.</em> |
| public | <strong>hasUser(</strong><em>mixed</em> <strong>$username</strong>)</strong> : <em>bool</em><br /><em>Whether the storage backend contains a specific user.</em> |
| public | <strong>hasUserCookies()</strong> : <em>bool</em><br /><em>Whether the storage backend has cookies for the currently active user.</em> |
| public | <strong>loadUserCookies()</strong> : <em>mixed</em><br /><em>Load all cookies for the currently active user.</em> |
| public | <strong>loadUserSettings()</strong> : <em>mixed</em><br /><em>Load all settings for the currently active user.</em> |
| public | <strong>moveUser(</strong><em>mixed</em> <strong>$oldUsername</strong>, <em>mixed</em> <strong>$newUsername</strong>)</strong> : <em>void</em><br /><em>Move the internal data for a username to a new username.</em> |
| public | <strong>openLocation(</strong><em>array</em> <strong>$locationConfig</strong>)</strong> : <em>void</em><br /><em>Connect to a storage location and perform necessary startup preparations.</em> |
| public | <strong>openUser(</strong><em>mixed</em> <strong>$username</strong>)</strong> : <em>void</em><br /><em>Open the data storage for a specific user.</em> |
| public | <strong>saveUserCookies(</strong><em>mixed</em> <strong>$rawData</strong>)</strong> : <em>void</em><br /><em>Save all cookies for the currently active user.</em> |
| public | <strong>saveUserSettings(</strong><em>array</em> <strong>$userSettings</strong>, <em>mixed</em> <strong>$triggerKey</strong>)</strong> : <em>void</em><br /><em>Save the settings for the currently active user.</em> |

*This class implements [\InstagramAPI\Settings\StorageInterface](#interface-instagramapisettingsstorageinterface)*

---
### Class: \InstagramAPI\Settings\Storage\Memcached

> Semi-persistent storage backend which uses a Memcached server daemon.

| Visibility | Function |
|:-----------|:---------|
| public | <strong>closeLocation()</strong> : <em>void</em><br /><em>Disconnect from a storage location and perform necessary shutdown steps.</em> |
| public | <strong>closeUser()</strong> : <em>void</em><br /><em>Close the settings storage for the currently active user.</em> |
| public | <strong>deleteUser(</strong><em>mixed</em> <strong>$username</strong>)</strong> : <em>void</em><br /><em>Delete all internal data for a given username.</em> |
| public | <strong>hasUser(</strong><em>mixed</em> <strong>$username</strong>)</strong> : <em>bool</em><br /><em>Whether the storage backend contains a specific user.</em> |
| public | <strong>hasUserCookies()</strong> : <em>bool</em><br /><em>Whether the storage backend has cookies for the currently active user.</em> |
| public | <strong>loadUserCookies()</strong> : <em>mixed</em><br /><em>Load all cookies for the currently active user.</em> |
| public | <strong>loadUserSettings()</strong> : <em>mixed</em><br /><em>Load all settings for the currently active user.</em> |
| public | <strong>moveUser(</strong><em>mixed</em> <strong>$oldUsername</strong>, <em>mixed</em> <strong>$newUsername</strong>)</strong> : <em>void</em><br /><em>Move the internal data for a username to a new username.</em> |
| public | <strong>openLocation(</strong><em>array</em> <strong>$locationConfig</strong>)</strong> : <em>void</em><br /><em>Connect to a storage location and perform necessary startup preparations.</em> |
| public | <strong>openUser(</strong><em>mixed</em> <strong>$username</strong>)</strong> : <em>void</em><br /><em>Open the data storage for a specific user.</em> |
| public | <strong>saveUserCookies(</strong><em>mixed</em> <strong>$rawData</strong>)</strong> : <em>void</em><br /><em>Save all cookies for the currently active user.</em> |
| public | <strong>saveUserSettings(</strong><em>array</em> <strong>$userSettings</strong>, <em>mixed</em> <strong>$triggerKey</strong>)</strong> : <em>void</em><br /><em>Save the settings for the currently active user.</em> |

*This class implements [\InstagramAPI\Settings\StorageInterface](#interface-instagramapisettingsstorageinterface)*

---
### Class: \InstagramAPI\Settings\Storage\MySQL

> Persistent storage backend which uses a MySQL server.

| Visibility | Function |
|:-----------|:---------|
| public | <strong>closeLocation()</strong> : <em>void</em><br /><em>Disconnect from a storage location and perform necessary shutdown steps.</em> |
| public | <strong>closeUser()</strong> : <em>void</em><br /><em>Close the settings storage for the currently active user.</em> |
| public | <strong>deleteUser(</strong><em>mixed</em> <strong>$username</strong>)</strong> : <em>void</em><br /><em>Delete all internal data for a given username.</em> |
| public | <strong>hasUser(</strong><em>mixed</em> <strong>$username</strong>)</strong> : <em>bool</em><br /><em>Whether the storage backend contains a specific user.</em> |
| public | <strong>hasUserCookies()</strong> : <em>bool</em><br /><em>Whether the storage backend has cookies for the currently active user.</em> |
| public | <strong>loadUserCookies()</strong> : <em>mixed</em><br /><em>Load all cookies for the currently active user.</em> |
| public | <strong>loadUserSettings()</strong> : <em>mixed</em><br /><em>Load all settings for the currently active user.</em> |
| public | <strong>moveUser(</strong><em>mixed</em> <strong>$oldUsername</strong>, <em>mixed</em> <strong>$newUsername</strong>)</strong> : <em>void</em><br /><em>Move the internal data for a username to a new username.</em> |
| public | <strong>openLocation(</strong><em>array</em> <strong>$locationConfig</strong>)</strong> : <em>void</em><br /><em>Connect to a storage location and perform necessary startup preparations.</em> |
| public | <strong>openUser(</strong><em>mixed</em> <strong>$username</strong>)</strong> : <em>void</em><br /><em>Open the data storage for a specific user.</em> |
| public | <strong>saveUserCookies(</strong><em>mixed</em> <strong>$rawData</strong>)</strong> : <em>void</em><br /><em>Save all cookies for the currently active user.</em> |
| public | <strong>saveUserSettings(</strong><em>array</em> <strong>$userSettings</strong>, <em>mixed</em> <strong>$triggerKey</strong>)</strong> : <em>void</em><br /><em>Save the settings for the currently active user.</em> |

*This class implements [\InstagramAPI\Settings\StorageInterface](#interface-instagramapisettingsstorageinterface)*

