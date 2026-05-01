# `POST` /api/v3/orders/stickers/cross-border

**Tag:** [FBS Assembly Orders](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Get Stickers for Cross-Border Assembly Orders**

Описание метода

Returns a list of stickers for Cross-Border assembly orders in PDF.

For each assembly order, the response contains the sticker generation status:
  - `awaitingTrackNumber` — the sticker is not ready. Waiting for a carrier's track number.
  - `ready` — the sticker is ready


  Stickers may be generated with a delay. Repeat the request until you receive the ready status.


Method limitations:
- You cannot request more than 100 stickers at a time (no more than 100 assembly order IDs in a request).
- The method returns stickers only for assembly orders that are on assembly or in delivery [status](/openapi/orders-fbs#tag/FBS-Assembly-Orders/paths/~1api~1v3~1orders~1status/post): `confirm`, `complete`.


Request limit per one seller's account for FBS assembly orders, supplies and passes methods:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 300 requests | 200 ms | 20 requests |

One request with a response code of 409 is counted as 10 requests


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

[Response 200](../_shared/examples/POST__api_v3_orders_stickers_cross_border_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data for the error |

[Response 400: IncorrectRequestBody](../_shared/examples/POST__api_v3_passes_400_IncorrectRequestBody.json)


[Response 400: IncorrectRequest](../_shared/examples/POST__api_v3_orders_status_400_IncorrectRequest.json)

- **401** Unauthorized
- **402** Payment Required
- **403** Forbidden
- **429** Too Many Requests
