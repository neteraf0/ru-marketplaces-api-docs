# `GET` /api/v3/dbw/orders/new

**Tag:** [DBW Assembly Orders](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Get New Orders**

Описание метода

Returns a list of all new [orders](./orders-dbw#tag/DBW-Assembly-Orders).


Request limit  per one seller's account for DBW methods:

    for getting and updating contact lists
    for getting and deleting metadata
    assembly orders


| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 300 requests | 200 ms | 20 requests |


## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `orders` | array |  | New assembly orders list |

[Response 200](../_shared/examples/GET__api_v3_dbw_orders_new_200.json)

- **401** Unauthorized
- **402** Payment Required
- **403** Forbidden
- **429** Too Many Requests
