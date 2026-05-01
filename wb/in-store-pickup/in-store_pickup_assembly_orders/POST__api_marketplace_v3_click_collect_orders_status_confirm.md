# `POST` /api/marketplace/v3/click-collect/orders/status/confirm

**Tag:** [In-Store Pickup Assembly Orders](index.md)

**Transfer to Assembly**

Описание метода

The method transfers [assembly orders](./in-store-pickup#tag/In-Store-Pickup-Assembly-Orders) from the `new` [status](./in-store-pickup#tag/In-Store-Pickup-Assembly-Orders/paths/~1api~1marketplace~1v3~1click-collect~1orders~1status~1info/post) to the `confirm` — on  assembly — status.


Request limit per one seller's account for In-Store Pickup assembly orders methods:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 s | 1 request | 1 s | 10 requests |

One request with a response code of 409 is counted as 10 requests


## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `ordersIds` | array |  | List of assembly order IDs *Example: `[123456, 234567]`* |
## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `requestId` |  | ✓ | Unique request ID *Example: `f1787bd2d1fdс35d6f537316514у4a05`* |
| `results` | array | ✓ |  |

[Response 200](../_shared/examples/POST__api_marketplace_v3_click_collect_orders_status_confirm_200.json)

- **400** Bad Request
- **401** Unauthorized
- **403** Forbidden
- **429** Too Many Requests
