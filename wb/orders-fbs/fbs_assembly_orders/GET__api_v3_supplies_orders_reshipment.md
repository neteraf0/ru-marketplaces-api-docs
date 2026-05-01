# `GET` /api/v3/supplies/orders/reshipment

**Tag:** [FBS Assembly Orders](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Get All Assembly Orders for Re-shipment**

Описание метода

Returns all assembly orders that require re-shipment


Request limit per one seller's account for FBS assembly orders, supplies and passes methods:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 300 requests | 200 ms | 20 requests |

One request with a response code of 409 is counted as 10 requests


## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `orders` | array |  | Assembly orders list |

[Response 200](../_shared/examples/GET__api_v3_supplies_orders_reshipment_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data for the error |

[Response 400: IncorrectParameter](../_shared/examples/GET__api_v3_orders_400_IncorrectParameter.json)

- **401** Unauthorized
- **402** Payment Required
- **403** Forbidden
- **429** Too Many Requests
