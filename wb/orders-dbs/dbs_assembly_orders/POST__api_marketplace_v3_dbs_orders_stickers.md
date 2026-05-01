# `POST` /api/marketplace/v3/dbs/orders/stickers

**Tag:** [DBS Assembly Orders](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Get Stickers for Assembly Orders with Delivery to Pickup Point**

Описание метода

Method is available by token types: Personal, Service

The method returns stickers for the assembly orders with delivery to pickup points in the [statuses](./orders-dbs#tag/DBS-Assembly-Orders/paths/~1api~1marketplace~1v3~1dbs~1orders~1status~1info/post):
  - `confirm` — on assembly
  - `deliver` — in delivery

You can get stickers only with 580x400 px size in PDF format.


Request limit per one seller's account for DBS assembly orders methods:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 300 requests | 200 ms | 20 requests |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `type` | query | string (enum: pdf) | ✓ | Sticker format |
| `width` | query | integer (enum: 58) | ✓ | Sticker width |
| `height` | query | integer (enum: 40) | ✓ | Sticker height |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `orders` | array | ✓ | Assembly orders ID list |
## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `stickers` | array |  | Stickers |

[Response 200](../_shared/examples/POST__api_marketplace_v3_dbs_orders_stickers_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data for the error |

[Response 400: IncorrectParameter](../_shared/examples/GET__api_v3_dbs_orders_400_IncorrectParameter.json)


[Response 400: StatusMismatch](../_shared/examples/POST__api_marketplace_v3_dbs_orders_stickers_400_StatusMismatch.json)

- **401** Unauthorized
- **403** Forbidden
- **429** Too Many Requests
