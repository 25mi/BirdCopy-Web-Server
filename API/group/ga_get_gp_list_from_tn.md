# Get Group list
    http://[ServerNetAddress]/ga_get_gp_list_from_tn.action

## Description
获取群组相关列表信息.

***

## Requires Type

* Get

***
## Requires authentication
* No.

***

## Parameters/optional
- **type** — 想要获取的数据类型,默认取值all,返回群组列表,其它取值rc,返回符合条件的记录数.
    - 'all' — 为默认值,返回符合条件群组列表.
    - 'rc' —  只返回符合条件的记录数。
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

默认返回（type取all）

	{"rc":"操作结果",
	"rm":"反馈信息",
	"allRecordCount":全部记录数,
	"allPageCount":全部页数,
	"currentPage":当前页数,
	"perPageCount":每页记录数,
	"rs":[{
		"gp_id":"群组id",
		"gp_name":"群组名称",
		"gp_owner":"群组属主",
		"gp_desc":"群组描述",
		"logo":"群组logo图片的url",
		"is_audit_join":"申请加入群组是否需要审核[1:是 0:否]",
		"is_rc_gp":"是否已开通融云对应群组[1:是 0:否 null:空]",
		"is_audit_rcgp":"申请加入融云对应群组是否需要审核[1:是 0:否]",
		"owner_recom":"属主是否已推荐[1:是 0:否 null:空]",
		"sys_recom":"系统是否已推荐[1:是 0:否 null:空]",
		}]
	}
	
	rc取值:	
	1:已成功
	0:未成功,rm返回具体出错信息,rm参数之后的其它参数可能不会返回.

type=rc

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

**Return** 
	{
	"rc":"1",
	"rm":"",
	"allRecordCount":"1",
	"allPageCount":"1",
	"currentPage":"1",
	"perPageCount":20,
	"rs":[
			{"gp_index":1,
			"gp_id":"6d08cef1cd33d42bfaa1a12ae2c2f194",
			"gp_name":"看美剧学英语",
			"gp_owner":"n1",
			"gp_des":"那种看着中文字幕的美剧，然后安慰说自己在练听力的都是掩耳盗铃而已   所以有句很出名的话，学英语专业吧，一切娱乐活动，皆以学习之名！",
			"logo":"http://www.birdenglish.com:9999/public/gp/1/logo_1jpeg",
			"is_audit_join":"0",
			"is_rc_gp":"1",
			"is_audit_rcgp":"1",
			"owner_recom":"1",
			"sys_recom":"1"}]
	}

