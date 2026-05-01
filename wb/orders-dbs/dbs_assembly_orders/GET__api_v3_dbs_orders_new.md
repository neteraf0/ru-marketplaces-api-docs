# `GET` /api/v3/dbs/orders/new

**Tag:** [DBS Assembly Orders](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Get New Orders List**

Описание метода

Returns a list of all new orders for the seller at the moment


Request limit per one seller's account for DBS assembly orders methods:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 300 requests | 200 ms | 20 requests |


## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `orders` | array |  | New assembly orders list |

[Response 200](../_shared/examples/GET__api_v3_dbs_orders_new_200.json)

- **401** Unauthorized
- **402** Payment Required
- **403** Forbidden
- **429** Too Many Requests
