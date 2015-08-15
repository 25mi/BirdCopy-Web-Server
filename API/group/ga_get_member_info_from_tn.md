# Get Group Member
	http://[ServerNetAddress]/ga_get_member_info_from_tn.action

## Description
获取群组成员的相关信息.
***

## Requires Type

* Get
***
## Requires authentication
* No.

***

## Parameters/Required
- **tuser_key** — 终端用户key;
- **gp_id** — 要加入或已加入的群组id.

## Parameters/optional
- **type** — 获取类型.
	- 'all' -默认值,全部信息.
	- 'ay_join_status' -获取此成员加入申请状态.
	- 'rp_join_desc' -获取此成员未通过加入申请描述.
	- 'ay_rcgp_status' -获取此成员聊天申请状态.
	- 'rp_rcgp_desc' -获取此成员未通过聊天申请描述.
	
- **app_id** — 查询时所在App id,为空时默认为系统App id.

***

## Return format
服务器端响应(Content-Type:application/json;charset=utf-8):

	{"rc":"操作结果","rm":"反馈信息","type":"相应值"}
	rc取值:	
	1:已成功
	0:未成功,rm返回具体出错信息,rm参数之后的其它参数可能不会返回
	
	注:当type=all时,返回结果同??的结果一致;
	注:ay_join_status及ay_rcgp_status取值同上;

***

## Errors
None

***

## Example
**Request**

    https://api.500px.com/v1/photos?feature=popular

**Return** __shortened for example purpose__
json
{
  "feature": "popular",
  "filters": {
      "category": false,
      "exclude": false
  },
  "current_page": 1,
  "total_pages": 250,
  "total_items": 5000,
  "photos": [
    {
      "id": 4910421,
      "name": "Orange or lemon",
      "description": "",
      "times_viewed": 709,
      "rating": 97.4,
      "created_at": "2012-02-09T02:27:16-05:00",
      "category": 0,
      "privacy": false,
      "width": 472,
      "height": 709,
      "votes_count": 88,
      "favorites_count": 26,
      "comments_count": 58,
      "nsfw": false,
      "image_url": "http://pcdn.500px.net/4910421/c4a10b46e857e33ed2df35749858a7e45690dae7/2.jpg",
      "user": {
        "id": 386047,
        "username": "Lluisdeharo",
        "firstname": "Lluis ",
        "lastname": "de Haro Sanchez",
        "city": "Sabadell",
        "country": "Catalunya",
        "fullname": "Lluis de Haro Sanchez",
        "userpic_url": "http://acdn.500px.net/386047/f76ed05530afec6d1d0bd985b98a91ce0ce49049/1.jpg?0",
        "upgrade_status": 0
      }
    },
    {
      "id": 4905955,
      "name": "R E S I G N E D",
      "description": "From the past of Tagus River, we have History and memories, some of them abandoned and disclaimed in their margins ...",
      "times_viewed": 842,
      "rating": 97.4,
      "created_at": "2012-02-08T19:00:13-05:00",
      "category": 0,
      "privacy": false,
      "width": 750,
      "height": 500,
      "votes_count": 69,
      "favorites_count": 34,
      "comments_count": 29,
      "nsfw": false,
      "image_url": "http://pcdn.500px.net/4905955/7e1a6be3d8319b3b7357c6390289b20c16a26111/2.jpg",
      "user": {
        "id": 350662,
        "username": "cresendephotography",
        "firstname": "Carlos",
        "lastname": "Resende",
        "city": "Forte da Casa",
        "country": "Portugal",
        "fullname": "Carlos Resende",
        "userpic_url": "http://acdn.500px.net/350662.jpg",
        "upgrade_status": 0
      }
    }
  ]
}

