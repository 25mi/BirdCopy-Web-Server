# 500px API

500px API provides programmatic access to 500px functionality and content.
Version 1 of the API is limited to the essentials of the website's functionality: viewing feature streams, photo information and comments, as well as user profiles.

The API is [REST API](http://en.wikipedia.org/wiki/Representational_State_Transfer "RESTful")
and uses [OAuth](http://oauth.net/ "OAuth") 1.0a for user authentication purposes.
Currently, return format for all endpoints is [JSON](http://json.org/ "JSON").

You can try our API in [console](http://bitly.com/api500px) ([http://bitly.com/api500px](http://bitly.com/api500px))

See [status.500px.com](http://status.500px.com) for API status updates, outages, and scheduled maintenance.

***

## Checklist
* [Try the API console](http://bitly.com/api500px)
* [See if the concepts used by the API are familiar to you][]
* Familiarize yourself with API functionality
* Read the 500px [API Terms of Use][]
* [Register your application][] and get OAuth consumer key and secret
* Hack away

***

## 概要

- **[Formats and Terms](https://github.com/500px/api-documentation/blob/master/basics/formats_and_terms.md)**

## Examples

- **[JavaScript](http://500px.github.com/500px-js-sdk)**
- **[iOS](https://github.com/500px/api-documentation/blob/master/examples/iOS/API%20Tutorials.md)**
- **[Ruby](https://github.com/500px/api-documentation/blob/master/examples/Ruby/)**
- **[PHP](https://github.com/500px/api-documentation/blob/master/examples/PHP/PHP.md)**

## Changes

* 2014-03-27 Deprecated photo object's image_url key.

## Application

- **[Android](https://github.com/birdcopy/Android-Birdcopy-Application)**
- **[iOS](https://github.com/birdcopy/IOS-BirdCopy-Application)**

## API

#### 群组终端上传及交互

- **[获取群组列表](https://github.com/birdcopy/BirdCopy-Web-Server/blob/master/API/group/ga_get_gp_list_from_tn.md)**
- **[获取群组相关信息](https://github.com/birdcopy/BirdCopy-Web-Server/blob/master/API/group/ga_get_gp_info_from_tn.md)**
- **[机端将终端用户申请加入群组的相关数据上传到服务器](https://github.com/birdcopy/BirdCopy-Web-Server/blob/master/API/group/ga_apply_member_from_tn.md)**
- **[手机端将终端用户申请群组聊天的相关数据上传到服务器](https://github.com/birdcopy/BirdCopy-Web-Server/blob/master/API/group/ga_apply_rcgp_from_tn.md)**
- **[获取群组成员的相关信息](https://github.com/birdcopy/BirdCopy-Web-Server/blob/master/API/group/ga_get_member_info_from_tn.md)**
- **[获取终端用户所属组列表](ga_get_member_gplist_from_tn.action)**

#### 支付相关/PING++

- **[获取支付凭据(Charge)](https://github.com/500px/api-documentation/blob/master/endpoints/upload/POST_upload.md)**
- **[查询支付凭据(Charge)信息](https://github.com/500px/api-documentation/blob/master/endpoints/upload/POST_upload.md)**


#### User Resources

- **[<code>GET</code> users](https://github.com/500px/api-documentation/blob/master/endpoints/user/GET_users.md)**
- **[<code>GET</code> users/show](https://github.com/500px/api-documentation/blob/master/endpoints/user/GET_users_show.md)**
- **[<code>GET</code> users/:id/friends](https://github.com/500px/api-documentation/blob/master/endpoints/user/GET_users_id_friends.md)**
- **[<code>GET</code> users/:id/followers](https://github.com/500px/api-documentation/blob/master/endpoints/user/GET_users_id_followers.md)**
- **[<code>GET</code> users/search](https://github.com/500px/api-documentation/blob/master/endpoints/user/GET_users_search.md)**
- **[<code>POST</code> users/:id/friends](https://github.com/500px/api-documentation/blob/master/endpoints/user/POST_users_id_friends.md)**
- **[<code>DELETE</code> users/:id/friends](https://github.com/500px/api-documentation/blob/master/endpoints/user/DELETE_users_id_friends.md)**

#### Blog Resources

- **[<code>GET</code> blogs](https://github.com/500px/api-documentation/blob/master/endpoints/blog/GET_blogs.md)**
- **[<code>GET</code> blogs/:id](https://github.com/500px/api-documentation/blob/master/endpoints/blog/GET_blogs_id.md)**
- **[<code>GET</code> blogs/:id/comments](https://github.com/500px/api-documentation/blob/master/endpoints/blog/GET_blogs_id_comments.md)**
- **[<code>POST</code> blogs/:id/comments](https://github.com/500px/api-documentation/blob/master/endpoints/blog/POST_blogs_id_comments.md)**
- **[<code>POST</code> blogs](https://github.com/500px/api-documentation/blob/master/endpoints/blog/POST_blogs.md)**
- **[<code>PUT</code> blogs/:id](https://github.com/500px/api-documentation/blob/master/endpoints/blog/PUT_blogs_id.md)**
- **[<code>DELETE</code> blogs/:id](https://github.com/500px/api-documentation/blob/master/endpoints/blog/DELETE_blogs_id.md)**

#### Collections Resources

- **[<code>GET</code> collections](https://github.com/500px/api-documentation/blob/master/endpoints/collections/GET_collections.md)**
- **[<code>GET</code> collections/:id](https://github.com/500px/api-documentation/blob/master/endpoints/collections/GET_collections_id.md)**
- **[<code>POST</code> collections](https://github.com/500px/api-documentation/blob/master/endpoints/collections/POST_collections.md)**
- **[<code>PUT</code> collections/:id](https://github.com/500px/api-documentation/blob/master/endpoints/collections/PUT_collections_id.md)**
- **[<code>DELETE</code> collections/:id](https://github.com/500px/api-documentation/blob/master/endpoints/collections/DELETE_collections_id.md)**

#### Comment Resources

- **[<code>POST</code> comments/:id/comments](https://github.com/500px/api-documentation/blob/master/endpoints/comments/POST_comments_id_comments.md)**

## Authentication

- **[<code>POST</code> oauth/request_token](https://github.com/500px/api-documentation/blob/master/authentication/POST_oauth_requesttoken.md)**
- **[<code>POST</code> oauth/authorize](https://github.com/500px/api-documentation/blob/master/authentication/POST_oauth_authorize.md)**
- **[<code>POST</code> oauth/access_token](https://github.com/500px/api-documentation/blob/master/authentication/POST_oauth_accesstoken.md)**
- **[Upload key](https://github.com/500px/api-documentation/blob/master/authentication/upload_key.md)**


## FAQ
### What do I need to know before I start using the API?
Got rust on your skills? No worries. Here are the docs you might need to get started:

- HTTPS protocol
- [REST software pattern][]
- Authentication with [OAuth][] (or the official [Beginner’s Guide][])
- Data serialization with [JSON][] (or see a [quick tutorial][])

### How do I connect to the 500px.com API?
The API is only available to authenticated clients. Clients should authenticate users using [OAuth][]. Once authenticated, you need to request a resource from one of the endpoints using HTTPS. Generally, reading any data is done through a request with GET method. If you want our server to create, update or delete a given resource, POST or PUT methods are required.

### What return formats do you support?
500px API currently returns data in [JSON](http://json.org/ "JSON") format.

### What kind of authentication is required?
Applications must identify themselves to access any resource.
If your application only needs read-only access and does not authenticate the user, **consumer_key** containing a valid Consumer Key parameter should be specified in the query string. Otherwise, [OAuth](https://github.com/500px/api-documentation/tree/master/authentication) or upload key authentication takes care of identifying the application as well as the user accessing the API.

### Is there a request rate limit?
There is a rate limit of 1,000,000 API requests per month per account. We will contact you and if required disable your application if we find that your application is exceeding this limit or interfering with our system's stability.This revised rate limit will come into effect May 1, 2014.

[REST software pattern]: http://en.wikipedia.org/wiki/Representational_State_Transfer
[OAuth]: http://oauth.net/core/1.0a/
[Beginner’s Guide]: http://hueniverse.com/oauth/
[JSON]: http://json.org
[quick tutorial]: http://www.webmonkey.com/2010/02/get_started_with_json/
[Register your application]: http://500px.com/settings/applications
[API Terms of Use]: https://github.com/500px/api-documentation/blob/master/basics/terms_of_use.md
[See if the concepts used by the API are familiar to you]: https://github.com/500px/api-documentation#what-do-i-need-to-know-before-i-start-using-the-api
