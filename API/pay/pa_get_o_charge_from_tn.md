# Query Charge
	http://[ServerNetAddress]/pa_get_o_charge_from_tn.action

## Description
壹收款专用-获取支付凭据(Charge).
***

## Requires Type

* post

***
## Requires authentication
- **tuser_key** — 终端用户key.
- **app_id** — 支付时所在App id.
- 数据格式:
		
		{
			"amount":订单总金额(int),
			"order_no":订单号(String),
			"channel":支付渠道(String),
			"extras":自定义参数(JsonObject)
		}

***

## Parameters/optional
    - 'subject' — 商品的标题，该参数最长为 32 个 Unicode 字符，银联限制在 32 个字节.
    - 'body' — 商品的描述信息，该参数最长为 128 个 Unicode 字符，yeepay_wap 对于该参数长度限制为 100 个 Unicode 字符
***

## Return format
服务器端响应(Content-Type:application/json;charset=utf-8):.type=all:

	{Ping++ Charge 对象(见Ping++相关文档)}
	注:中途出错时,返回格式{"rc":"0","rm":"出错信息"}.
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

