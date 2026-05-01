# `POST` /api/marketplace/v3/dbs/orders/status/info

**Tag:** [DBS Assembly Orders](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Get Assembly Order Statuses**

Описание метода

Returns the statuses of [assembly orders](./orders-dbs#tag/DBS-Assembly-Orders) based on the list of assembly order IDs.

`supplierStatus` is a status of an order. The trigger for its change is the action of the seller himself.
Possible values for this field are:
| Status   | Description               | How to move an order to this status   |
| -------  | ---------                 | --------------------------------------|
| `new`      | **New order** | |
| `confirm`  | **Order on assembly**      |  [Transfer to assembly](./orders-dbs?locale=ru#tag/DBS-Assembly-Orders/paths/~1api~1marketplace~1v3~1dbs~1orders~1status~1confirm/post)
| `deliver`  | **Order on delivery**    | [Transfer to delivery](./orders-dbs#tag/DBS-Assembly-Orders/paths/~1api~1marketplace~1v3~1dbs~1orders~1status~1deliver/post)
| `receive`  | **Received by the buyer**       | [Notify that the order has been accepted by the buyer](./orders-dbs#tag/DBS-Assembly-Orders/paths/~1api~1marketplace~1v3~1dbs~1orders~1status~1receive/post)
| `reject`   | **Declined upon receipt**           |  [Notify that the buyer has declined the order](./orders-dbs#tag/DBS-Assembly-Orders/paths/~1api~1marketplace~1v3~1dbs~1orders~1status~1reject/post)
| `cancel`   | **Canceled by the supplier**   |  [Cancel the order](./orders-dbs#tag/DBS-Assembly-Orders/paths/~1api~1marketplace~1v3~1dbs~1orders~1status~1cancel/post)
| `cancel_missed_call` | **Cancellation due to unreachable buyer** | The status changes automatically |

`wbStatus` is a status of an order on the Wildberries side.
Possible values for this field are:
- `waiting` — assembly order in work
- `sold` — the buyer got the order
- `canceled` — assembly order canceled
- `canceled_by_client` — the buyer canceled the order
- `declined_by_client` — the buyer canceled the order in the first hour  Cancellation is available to the buyer in the first hour from the moment of order, if the order is not transferred to confirm status.
- `defect` — order canceled due to a defect
- `ready_for_pickup` — the order arrived the pickup point
- `canceled_by_missed_call`— cancellation due to unreachable buyer. For delivery by supplier


Request limit per one seller's account for DBS assembly orders methods:

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
| `orders` | array |  | Status data |

[Response 200](../_shared/examples/POST__api_marketplace_v3_dbs_orders_status_info_200.json)

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

### `404` Not found


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `detail` | object |  | Error details |
| `origin` | string |  | WB internal service ID *Example: `dbs-public-api`* |
| `requestId` | string |  | Unique request ID *Example: `f1787bd2d1fdс35d6f537316514у4a05`* |
| `title` | string |  | Error title *Example: `IncorrectRequest`* |

[Response 404](../_shared/examples/POST__api_marketplace_v3_dbs_orders_b2b_info_400.json)

- **429** Too Many Requests
