# Get Group list
    http://[ServerNetAddress]/ga_get_gp_list_from_tn.action

## Description
获取群组相关列表信息.

***

## Requires Type

* Get

***

## Parameters/optional
- **type** — 想要获取的数据内容,默认取值all,返回群组列表,其它取值rc,返回符合条件的全部记录数.
- **perPageCount** — 每页记录数,大于0的正整数，默认15.
- **page** — 第几页,大于0的正整数，默认1.
- **owner_recom** — 属主推荐,1:已推荐 0:未推荐.
- **sys_recom** — 系统推荐,1:已推荐 0:未推荐
- **gp_id**— 群组id.
- **gp_owner** — 群组属主.
- **sys_time_start** — 录入起始时间,标准格式:yyyy-mm-dd hh:mi:ss
- **sys_time_stop** — 录入终止时间,标准格式:yyyy-mm-dd hh:mi:ss
- **upd_time_start** — 最近更新起始时间,标准格式:yyyy-mm-dd hh:mi:ss
- **upd_time_stop** — 最近更新终止时间,标准格式:yyyy-mm-dd hh:mi:ss
- **sortindex** — 排序.(返回群组列表的排序）,多重排序可组合,中间以,分隔;
    - 为空时 — 表示按 最近更新时间 降序.
    - 'sys_time desc' — 为默认值,表示按 录入时间 降序;(升序去掉 desc).
    - 'upd_time desc' — 表示按 更新时间 降序;(升序去掉 desc)
    - 'gp_name' — 表示按 群组名称 升序;(降序加 desc)

- **tuser_key** — 终端用户key.
- **app_id** — 查询时所在App id.


***

## Return format
服务器端响应(Content-Type:application/json;charset=utf-8):.type=all:

.type=all:
	{"rc":"操作结果","rm":"反馈信息","allRecordCount":全部记录数,"allPageCount":全部页数,"currentPage":当前页数,"perPageCount":每页记录数,
		[{
		"gp_id":"群组id","gp_name":"群组名称","gp_owner":"群组属主","gp_desc":"群组描述","logo":"群组logo图片的url",
		"is_audit_join":"申请加入群组是否需要审核[1:是 0:否]",
		"is_rc_gp":"是否已开通融云对应群组[1:是 0:否 null:空]",
		"is_audit_rcgp":"申请加入融云对应群组是否需要审核[1:是 0:否]",
		"owner_recom":"属主是否已推荐[1:是 0:否 null:空]",
		"sys_recom":"系统是否已推荐[1:是 0:否 null:空]",
		},{puser2:...}...]
	}
	rc取值:	
	1:已成功
	0:未成功,rm返回具体出错信息,rm参数之后的其它参数可能不会返回.


       .type=rc:
	{"rc":"操作结果","rm":"反馈信息","allRecordCount":全部记录数}
	rc取值:	
	1:已成功
	0:未成功,rm返回具体出错信息,rm参数之后的其它参数可能不会返回.
***

## Errors
None

***

## Example
**Request**

    https://api.500px.com/v1/photos?feature=popular

**Return** __shortened for example purpose__
``` json
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

