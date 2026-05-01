# `POST` /api/marketplace/v3/dbs/orders/status/confirm

**Tag:** [DBS Assembly Orders](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Transfer to Assembly**

Описание метода

The method transfers [assembly orders](./orders-dbs#tag/DBS-Assembly-Orders) with the `new` [status](./orders-dbs#tag/DBS-Assembly-Orders/paths/~1api~1marketplace~1v3~1dbs~1orders~1status~1info/post) to the `confirm` status — order on assembly.


Request limit per one seller's account:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 s | 1 request | 1 s | 10 requests |


## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `ordersIds` | array |  | List of assembly order IDs *Example: `[123456, 234567]`* |
## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `requestId` | string |  | Unique request ID *Example: `f1787bd2d1fdс35d6f537316514у4a05`* |
| `results` | array |  |  |

[Response 200](../_shared/examples/POST__api_marketplace_v3_dbs_orders_status_cancel_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `detail` | object |  | Error details |
| `origin` | string |  | WB internal service ID *Example: `dbs-public-api`* |
| `requestId` | string |  | Unique request ID *Example: `f1787bd2d1fdс35d6f537316514у4a05`* |
| `title` | string |  | Error title *Example: `IncorrectRequest`* |

[Response 400](../_shared/examples/POST__api_marketplace_v3_dbs_orders_b2b_info_400.json)

- **401** Unauthorized
### `403` Access denied


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `detail` | object |  | Error details |
| `origin` | string |  | WB internal service ID *Example: `dbs-public-api`* |
| `requestId` | string |  | Unique request ID *Example: `f1787bd2d1fdс35d6f537316514у4a05`* |
| `title` | string |  | Error title *Example: `IncorrectRequest`* |

[Response 403](../_shared/examples/POST__api_marketplace_v3_dbs_orders_b2b_info_403.json)

- **429** Too Many Requests
