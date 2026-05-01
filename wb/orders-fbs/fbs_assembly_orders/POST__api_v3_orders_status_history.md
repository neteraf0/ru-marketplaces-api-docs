# `POST` /api/v3/orders/status/history

**Tag:** [FBS Assembly Orders](index.md)

**Status History for Cross-Border Orders**

Описание метода

Returns status history for Cross-Border orders


Request limit per one seller's account for FBS assembly orders, supplies and passes methods:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 300 requests | 200 ms | 20 requests |

One request with a response code of 409 is counted as 10 requests


## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `orders` | array |  | Assembly orders IDs *Example: `[123456789, 987654321]`* |
## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `orders` | array |  | Assembly orders list |

[Response 200](../_shared/examples/POST__api_v3_orders_status_history_200.json)

- **400** Bad request
- **401** Unauthorized
- **402** Payment Required
- **403** Forbidden
- **404** Not Found
- **429** Too Many Requests
