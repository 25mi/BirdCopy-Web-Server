# Query Charge
	http://[ServerNetAddress]/pa_get_charge_from_tn.action

## Description
查询支付凭据(Charge)信息.

***

## Requires Type

* Get

***
## Requires authentication
- **tuser_key** — 终端用户key.
- **order_no** — 订单号.
  [order_no和ppp_chg_id]至少提供一个
- **ppp_chg_id** — Ping++ charge 对象的 id.
- **order_no** — 订单号.
***

## Parameters/optional
- **type** — 获取类型,取值如下.
	- 默认值=paid — boolean,是否已付款.
    - 'transaction_no' — 支付渠道返回的交易流水号.
    - 'time_paid' — 订单支付完成时间
    - 'time_expire' — 订单失效时间
    - 'failure_code' —订单的错误码
    - 'failure_msg' — 订单的错误消息的描述
    - 'ppp_charge' — Ping++ Charge 对象
    - 'ppp_event' — Ping++ Event 对象

- **app_id** — 查询时所在App id.
***

## Return format
服务器端响应(Content-Type:application/json;charset=utf-8):.type=all:

	{"rc":"操作结果","rm":"反馈信息","获取类型":"相应值"}
rc取值:	
	1:已成功
	0:未成功
	注:rc=0时,rm返回具体出错信息,rm参数之后的其它参数可能不会返回.
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

