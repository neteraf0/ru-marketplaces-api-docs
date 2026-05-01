# `POST` /api/v3/orders/stickers

**Tag:** [FBS Assembly Orders](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Get Assembly Orders Stickers**

Описание метода

Returns a list of stickers according to the requested assembly orders.
You can request a sticker in `svg`, `zplv` (vertical), `zplh` (horizontal) and `png` formats.

**Method limitations**:
- You cannot request more than 100 stickers at a time (no more than 100 assembly orders IDs in a request).
- The method returns stickers only for assembly orders in the `confirm` — in assembly and `complete` — in delivery [statuses](./orders-fbs#tag/FBS-Assembly-Orders/paths/~1api~1v3~1orders~1status/post).
- Available dimensions:
  - 580x400 px, with parameters `width` = 58, `height` = 40
  - 400x300 px, with parameters `width` = 40, `height` = 30


Request limit per one seller's account for FBS assembly orders, supplies and passes methods:

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
| `orders` | array |  | List of assembly order IDs |
## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `stickers` | array |  |  |

[Response 200](../_shared/examples/POST__api_v3_orders_stickers_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data for the error |

[Response 400: IncorrectRequestBody](../_shared/examples/POST__api_v3_passes_400_IncorrectRequestBody.json)


[Response 400: IncorrectRequest](../_shared/examples/POST__api_v3_orders_status_400_IncorrectRequest.json)


[Response 400: IncorrectParameter](../_shared/examples/GET__api_v3_orders_400_IncorrectParameter.json)

- **401** Unauthorized
- **402** Payment Required
- **403** Forbidden
- **429** Too Many Requests
