# `POST` /api/marketplace/v3/dbw/orders/meta/details

**Tag:** [DBW Metadata](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Get Order Metadata**

Описание метода

Returns [assembly orders](./orders-dbw#tag/DBW-Assembly-Orders) metadata and their validation statuses.

The list of metadata available for the assembly order can be obtained in the [list of new assembly orders](/openapi/orders-dbw#tag/DBW-Assembly-Orders/paths/~1api~1v3~1dbw~1orders~1new/get), field `requiredMeta`.


Request limit  per one seller's account for DBW methods:

    for getting and updating contact lists
    for getting and deleting metadata
    assembly orders


| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 300 requests | 200 ms | 20 requests |


## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `ordersIds` | array |  | List of assembly order IDs *Example: `[123456, 234567]`* |
## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `requestId` | string | ✓ | Unique request ID *Example: `f1787bd2d1fdс35d6f537316514у4a05`* |
| `orders` | array |  | Assembly orders metadata and validation statuses |

[Response 200](../_shared/examples/POST__api_marketplace_v3_dbw_orders_meta_details_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `detail` | object |  | Error details |
| `origin` | string |  | WB internal service ID *Example: `dbs-public-api`* |
| `requestId` | string |  | Unique request ID *Example: `f1787bd2d1fdс35d6f537316514у4a05`* |
| `title` | string |  | Error title *Example: `IncorrectRequest`* |

[Response 400](../_shared/examples/POST__api_marketplace_v3_dbw_orders_meta_details_400.json)

- **401** Unauthorized
### `403` Access denied


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `detail` | object |  | Error details |
| `origin` | string |  | WB internal service ID *Example: `dbs-public-api`* |
| `requestId` | string |  | Unique request ID *Example: `f1787bd2d1fdс35d6f537316514у4a05`* |
| `title` | string |  | Error title *Example: `IncorrectRequest`* |

[Response 403](../_shared/examples/POST__api_marketplace_v3_dbw_orders_meta_details_403.json)

- **429** Too Many Requests
