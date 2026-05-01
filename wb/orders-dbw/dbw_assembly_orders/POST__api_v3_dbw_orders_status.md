# `POST` /api/v3/dbw/orders/status

**Tag:** [DBW Assembly Orders](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Get Orders Statuses**

Описание метода

Returns the statuses of orders based on the provided list of assembly order IDs

`supplierStatus` is a status of an order. The trigger for its change is the action of the seller himself.
Possible values for this field are:
| Status   | Description               | How to move an order to this status   |
| -------  | ---------                 | --------------------------------------|
| `new`      | **New order** | |
| `confirm`  | **Order on assembly**      |  [Transfer to assembly](./orders-dbw#tag/DBW-Assembly-Orders/paths/~1api~1v3~1dbw~1orders~1%7BorderId%7D~1confirm/patch)
| `complete`  | **Order on delivery**    | [Transfer to delivery](./orders-dbw#tag/DBW-Assembly-Orders/paths/~1api~1v3~1dbw~1orders~1%7BorderId%7D~1assemble/patch)
| `receive`  | **Received by the buyer**       | Changed by the courier
| `reject`   | **Declined upon receipt**           |  Changed by the courier
| `cancel`   | **Canceled by the seller**   |  [Cancel the order](./orders-dbw#tag/DBW-Assembly-Orders/paths/~1api~1v3~1dbw~1orders~1%7BorderId%7D~1cancel/patch)
| `cancel_missed_call` | **Cancellation due to unreachable buyer** | The status changes automatically |

`wbStatus` is a status of an order on the Wildberries side.
Possible values for this field are:
- `waiting` — order in work
- `sold` — the buyer got the order
- `canceled` — order canceled
- `canceled_by_client` — the buyer canceled the order
- `declined_by_client` — the buyer canceled the order in the first hour  Cancellation is available to the buyer in the first hour from the moment of order, if the order is not transferred to confirm status.
- `defect` — order canceled due to a defect
- `canceled_by_missed_call` — cancellation due to unreachable buyer
- `postponed_delivery` — courier delivery is postponed


Request limit per one seller's account for DBW methods:

    for getting and updating contact lists
    for getting and deleting metadata
    assembly orders


| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 300 requests | 200 ms | 20 requests |

One request with a response code of 409 is counted as 10 requests


## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `orders` | array | ✓ | Orders IDs list |
## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `orders` | array |  |  |

[Response 200](../_shared/examples/POST__api_v3_dbw_orders_status_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data for the error |

[Response 400: IncorrectParameter](../_shared/examples/GET__api_v3_dbw_orders_400_IncorrectParameter.json)


[Response 400: IncorrectRequestBody](../_shared/examples/POST__api_v3_dbw_orders_delivery_date_400_IncorrectRequestBody.json)


[Response 400: IncorrectRequest](../_shared/examples/POST__api_v3_dbw_orders_delivery_date_400_IncorrectRequestBody.json)

- **401** Unauthorized
- **402** Payment Required
- **403** Forbidden
- **429** Too Many Requests
