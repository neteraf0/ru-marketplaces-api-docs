# `PATCH` /api/marketplace/v3/supplies/{supplyId}/orders

**Tag:** [FBS Supplies](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Add Assembly Orders to the Supply**

Описание метода

The method adds up to 100 [assembly orders](/openapi/orders-fbs#tag/FBS-Assembly-Orders/paths/~1api~1v3~1orders/get) to the supply and moves it to the `confirm` [status](/openapi/orders-fbs#tag/FBS-Assembly-Orders/paths/~1api~1v3~1orders~1status/post).

It can also move the assembly orders:
  - between active supplies
  - from a closed to an active supply, if the assembly order requires [reshipment](/openapi/orders-fbs#tag/FBS-Assembly-Orders/paths/~1api~1v3~1supplies~1orders~1reshipment/get).


  You can add assembly orders of any dimensional type to an empty supply. After adding the first assembly order, the supply acquires the dimensional type of this assembly order from the cargoType field.

  After that, you can only add assembly orders of the same dimensional type as the supply.


Assembly orders received at different warehouses cannot be added to the delivery.


  You can add assembly orders of any type to an empty supply: crossborder or non-crossborder. After adding the first assembly order, the supply acquires the type of this assembly order from the crossBorderType field.

  After that, you can add to the supply only the assembly orders of the same type as the supply.


Request limit per one seller's account for FBS assembly orders, supplies and passes methods:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 300 requests | 200 ms | 20 requests |

One request with a response code of 409 is counted as 10 requests


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `supplyId` | path | string | ✓ | Supply ID *Example: `WB-GI-1234567`* |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `orders` | array |  | Assembly order IDs *Example: `[5632423, 3453452, 7654533, 4529544]`* |
## Responses

- **204** The assembly orders assigned to the supply
### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data for the error |

[Response 400: IncorrectParameter](../_shared/examples/GET__api_v3_orders_400_IncorrectParameter.json)

- **401** Unauthorized
- **403** Forbidden
- **404** Not Found
### `409` Error adding the assembly order to the supply


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data for the error |

[Response 409: FailedToAddSupplyOrder](../_shared/examples/PATCH__api_marketplace_v3_supplies__supplyId__orders_409_FailedToAddSupplyOrder.json)

- **429** Too Many Requests
