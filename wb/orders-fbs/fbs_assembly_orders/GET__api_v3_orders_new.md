# `GET` /api/v3/orders/new

**Tag:** [FBS Assembly Orders](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Get New Assembly Orders**

Описание метода

Returns a list of all new [assembly orders](./orders-fbs#tag/FBS-Assembly-Orders/paths/~1api~1v3~1orders/get).


  Metadata specified in the requiredMeta and optionalMeta fields in assembly orders only affects the ability to transfer a supply to delivery. If your product requires mandatory marking with identification means, you must specify all needed metadata whether it was received in requiredMeta or optionalMeta field (see 4.6 of the Offer).

  We recommend adding all metadata received in the requiredMeta and optionalMeta fields to the assembly orders


Request limit per one seller's account for FBS assembly orders, supplies and passes methods:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 300 requests | 200 ms | 20 requests |


## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `orders` | array |  | New assembly orders list |

[Response 200](../_shared/examples/GET__api_v3_orders_new_200.json)

- **401** Unauthorized
- **402** Payment Required
- **403** Forbidden
- **429** Too Many Requests
