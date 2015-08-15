# Appley Member
	http://[ServerNetAddress]/ga_apply_member_from_tn.action

## Description
手机端将终端用户申请加入群组的相关数据上传到服务器.
***

## Requires Type

* Get
***
## Requires authentication
* No.

***

## Parameters/Required
- **tuser_key** — 终端用户key;[注:tuser_key不存在时会自动注册;].
- **gp_id** — 要加入的群组id.

## Parameters/optional
- **is_ay_rcgp** — 是否申请聊天功能(融云群组聊天),默认值1(是),其它值0(否);.
    - ‘1’  — 申请聊天功能.
    - '0'  — 不申请聊天功能.
- **app_id** — 申请时所在App id,为空时默认为系统App id.
***

## Return format
服务器端响应(Content-Type:application/json;charset=utf-8):

	{"rc":"操作结果","rm":"反馈信息","info_type":"信息类型","tuser_key":"tuser_key"
		,"ay_join_time":"加入申请时间","ay_join_status":"加入申请状态","rp_join_desc":"未通过加入申请描述"
		,"ay_rcgp_time":"聊天申请时间","ay_rcgp_status":"聊天申请状态","rp_rcgp_desc":"未通过聊天申请描述"
	}
	rc取值:	
	1:已成功
	0:未成功,rm返回具体出错信息,rm参数之后的其它参数可能不会返回.

	注:info_type取值如下:
		now:及时反馈;
		ay_join:申请加入群组的审批反馈;(可能是V的反馈)
		ay_rcgp:申请群组聊天的审批反馈;(可能是VI的反馈)
		mod_member:服务器端改变成员状态提示;(可能是VII的提示)
		del_member:服务器端删除成员信息提示;(可能是VIII的提示)

	注:ay_join_status及ay_rcgp_status取值如下:
		0:正在审批;
		1:审批通过;
		4:审批未通过;
	注:如果系统依赖融云推送审批结果,系统审批后会发送RC:TxtMsg类型系统消息一次,内容同上,也可自行获取审批结果.
	
	服务器端如果改变成员相应状态,如果系统依赖融云推送审批结果,系统会发送RC:TxtMsg类型系统消息一次,内容同V的结果一致.
	 
	服务器端如果从组删除成员,如果系统依赖融云推送审批结果,系统会发送RC:TxtMsg类型系统消息一次,内容同V的结果一致,但info_type之后的内容不会返回.
***

## Errors
None

***

## Example
**Request**

    https://api.500px.com/v1/photos?feature=popular

**Return shortened for example purpose**

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

