# `GET` /api/v3/click-collect/orders/new

**Tag:** [In-Store Pickup Assembly Orders](index.md)

**Get New Assembly Orders List**

Описание метода

The method provides a list of all new [assembly orders](./in-store-pickup#tag/In-Store-Pickup-Assembly-Orders) that the seller has at the time of the request.


Request limit per one seller's account for In-Store Pickup assembly orders methods:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 300 requests | 200 ms | 20 requests |

One request with a response code of 409 is counted as 10 requests


## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `orders` | array |  | Assembly orders list |

[Response 200: NewOrderClick](../_shared/examples/GET__api_v3_click_collect_orders_new_200_NewOrderClick.json)

- **401** Unauthorized
- **402** Payment Required
- **403** Forbidden
- **429** Too Many Requests
