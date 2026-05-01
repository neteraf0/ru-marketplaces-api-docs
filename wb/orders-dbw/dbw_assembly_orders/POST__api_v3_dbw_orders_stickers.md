# `POST` /api/v3/dbw/orders/stickers

**Tag:** [DBW Assembly Orders](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Get Orders Stickers**

Описание метода

Returns a list of stickers for the [assembly orders](/openapi/orders-dbw#tag/DBW-Assembly-Orders/paths/~1api~1v3~1dbw~1orders~1new/get) in the [statuses](./orders-dbw#tag/DBW-Assembly-Orders/paths/~1api~1v3~1dbw~1orders~1status/post):
  - `confirm` — on assembly
  - `complete` — on delivery

You can get a maximum of 100 stickers per request.
Available sticker formats:
  - SVG
  - ZPLV (vertical)
  - ZPLH (horizontal)
  - PNG

Available dimensions:
  - 580x400 px, with `width=58&height=40` in request
  - 400x300 px, with `width=40&height=30` in request


Request limit per one seller's account for DBW methods:

    for getting and updating contact lists
    for getting and deleting metadata
    assembly orders


| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 300 requests | 200 ms | 20 requests |

One request with a response code of 409 is counted as 10 requests


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `type` | query | string (enum: svg, zplv, zplh, png) | ✓ | Sticker format |
| `width` | query | integer (enum: 58, 40) | ✓ | Sticker width |
| `height` | query | integer (enum: 40, 30) | ✓ | Sticker height |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `orders` | array |  | Assembly order IDs list |
## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `stickers` | array |  |  |

[Response 200](../_shared/examples/POST__api_v3_dbw_orders_stickers_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data for the error |

[Response 400: IncorrectRequestBody](../_shared/examples/POST__api_v3_dbw_orders_delivery_date_400_IncorrectRequestBody.json)


[Response 400: IncorrectRequest](../_shared/examples/POST__api_v3_dbw_orders_delivery_date_400_IncorrectRequestBody.json)


[Response 400: IncorrectParameter](../_shared/examples/GET__api_v3_dbw_orders_400_IncorrectParameter.json)

- **401** Unauthorized
- **402** Payment Required
- **403** Forbidden
- **429** Too Many Requests
