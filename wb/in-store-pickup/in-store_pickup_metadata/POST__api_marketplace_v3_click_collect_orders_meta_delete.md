# `POST` /api/marketplace/v3/click-collect/orders/meta/delete

**Tag:** [In-Store Pickup Metadata](index.md)

**Delete Assembly Order Metadata**

Описание метода

The method removes [assembly orders metadata](./in-store-pickup#tag/In-Store-Pickup-Metadata/paths/~1api~1marketplace~1v3~1click-collect~1orders~1meta~1info/post) values.
You can only remove one type of metadata in one request: `imei`, `uin`, `gtin` or `sgtin`.


Request limit per one seller's account for all methods for getting and deleting In-Store Pickup metadata:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 150 requests | 400 ms | 20 requests |

One request with a response code of 409 is counted as 10 requests


## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `key` | string | ✓ | Metadata type to delete (`imei`, `uin`, `gtin`, `sgtin`). Only one value is passed *Example: `imei`* |
| `ordersIds` | array | ✓ | Assembly orders IDs list *Example: `[123456, 234567]`* |
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
