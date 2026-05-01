# `POST` /api/v3/orders/status

**Tag:** [FBS Assembly Orders](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Get Assembly Orders Statuses**

Описание метода

Returns the statuses of assembly orders from the request.

`supplierStatus` is a status of an assembly order. Its change is always triggered only by the supplier.

Possible values of `supplierStatus`:

| Status    | Description              | How to move the assembly orders to this status |
|-----------|--------------------------|---------------------------------------------|
| `new`       | **New order**        |                                             |
| `confirm`   | **In assembly** For delivery by Wildberries `fbs` | [Add assembly orders to the supply](./orders-fbs#tag/FBS-Supplies/paths/~1api~1marketplace~1v3~1supplies~1%7BsupplyId%7D~1orders/patch)
| `complete`  | **In delivery**  For delivery by Wildberries `fbs` and by WB courier `wbgo` |  [Transfer the supply to delivery](./orders-fbs#tag/FBS-Supplies/paths/~1api~1v3~1supplies~1%7BsupplyId%7D~1deliver/patch) |
| `cancel`   | **Canceled by seller** | [Cancel the order](./orders-fbs#tag/FBS-Assembly-Orders/paths/~1api~1v3~1orders~1%7BorderId%7D~1cancel/patch) |
| `cancel_carrier`   | **Canceled by carrier** For crossborder only | Changed by the carrier |

`wbStatus` — is a status of an order on the Wildberries side.

Possible values for this field are:
- `waiting` — the supplier confirmed the order, and the Wildberries has not received it yet
- `sorted` — the Wildberries warehouse sorted the order
- `sold` — the order is sold
- `canceled` — the supplier canceled the order
- `canceled_by_client` — the buyer canceled the order upon receipt
- `declined_by_client` — the buyer canceled the order in the first hour  Cancellation is available to the buyer in the first hour from the moment of order, if the order is not transferred to confirm status.
- `defect` — cancellation of the order due to a defect
- `ready_for_pickup` — the order came at pickup point and waiting for the client
- `postponed_delivery` — courier delivery is postponed
- `accepted_by_carrier` — accepted by carrier. The order is handed over to delivery service in the seller country
- `sent_to_carrier` — dispatched to carrier. The order is on the way to delivery service's warehouse in the seller
- `canceled_by_carrier` — the order was cancelled by the carrier. For crossborder only


Request limit per one seller's account for FBS assembly orders, supplies and passes methods:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 300 requests | 200 ms | 20 requests |

One request with a response code of 409 is counted as 10 requests


## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `orders` | array | ✓ | List of assembly order IDs |
## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `orders` | array |  |  |

[Response 200](../_shared/examples/POST__api_v3_orders_status_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data for the error |

[Response 400: IncorrectParameter](../_shared/examples/GET__api_v3_orders_400_IncorrectParameter.json)


[Response 400: IncorrectRequestBody](../_shared/examples/POST__api_v3_passes_400_IncorrectRequestBody.json)


[Response 400: IncorrectRequest](../_shared/examples/POST__api_v3_orders_status_400_IncorrectRequest.json)

- **401** Unauthorized
- **402** Payment Required
- **403** Forbidden
- **429** Too Many Requests
