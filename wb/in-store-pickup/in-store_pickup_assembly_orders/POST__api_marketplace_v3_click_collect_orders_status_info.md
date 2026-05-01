# `POST` /api/marketplace/v3/click-collect/orders/status/info

**Tag:** [In-Store Pickup Assembly Orders](index.md)

**Get Assembly Order Statuses**

Описание метода

The method provides the statuses of [assembly orders](./in-store-pickup#tag/In-Store-Pickup-Assembly-Orders) by their ID.

`supplierStatus` — the status of the assembly order. The trigger for its change is the action of the seller himself.

Possible values for `supplierStatus`:
| Status              | Description                | How to set the assembly order to this status                    |
|---------------------|----------------------------|-----------------------------------------------------------------|
| `new`                 | **New assembly order**         ||
| `confirm`             | **In assembly**                | [Transfer to assembly](./in-store-pickup#tag/In-Store-Pickup-Assembly-Orders/paths/~1api~1marketplace~1v3~1click-collect~1orders~1status~1confirm/post)          |
| `prepare`             | **Ready for pickup**           | [Notify that the assembly order is ready for delivery](./in-store-pickup#tag/In-Store-Pickup-Assembly-Orders/paths/~1api~1marketplace~1v3~1click-collect~1orders~1status~1prepare/post)           |
| `receive`             | **Received by buyer**       | [Notify that the order has been received by the buyer](./in-store-pickup#tag/In-Store-Pickup-Assembly-Orders/paths/~1api~1marketplace~1v3~1click-collect~1orders~1status~1receive/post)           |
| `reject`              | **Buyer refusal**           | [Notify that the buyer has declined the order](./in-store-pickup#tag/In-Store-Pickup-Assembly-Orders/paths/~1api~1marketplace~1v3~1click-collect~1orders~1status~1reject/post)            |
| `cancel`              | **Canceled by seller**         | [Cancel the order](./in-store-pickup#tag/In-Store-Pickup-Assembly-Orders/paths/~1api~1marketplace~1v3~1click-collect~1orders~1status~1cancel/post)            |
| `cancel_shelf_life`   | **Canceled due to shelf life expiration** | Automatically transitions upon event occurrence |

`wbStatus` — the status of the assembly order in the WB system.

Possible values for wbStatus:
- `waiting` - assembly order is in progress
- `sorted` - assembly order is sorted
- `sold` - the buyer got the order
- `canceled` - assembly order canceled
- `canceled_by_client` - buyer canceled the order upon receipt
- `declined_by_client` - buyer canceled the order within the first hour
Cancellation is available to the buyer within the first hour from the time of order, if the order has not been transitioned to assembly
- `defect` - order canceled due to defect
- `ready_for_pickup` - order is ready for pickup


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
| `orders` | array |  | Status data |

[Response 200](../_shared/examples/POST__api_marketplace_v3_click_collect_orders_status_info_200.json)

- **400** Bad Request
- **401** Unauthorized
- **403** Forbidden
- **429** Too Many Requests
