# `POST` /api/marketplace/v3/click-collect/orders/meta/info

**Tag:** [In-Store Pickup Metadata](index.md)

**Get Assembly Orders Metadata**

Описание метода

Returns [assembly orders](./in-store-pickup#tag/In-Store-Pickup-Assembly-Orders) metadata.

The list of metadata available for the assembly order can be got in the [list of new assembly orders](./in-store-pickup#tag/In-Store-Pickup-Assembly-Orders/paths/~1api~1v3~1click-collect~1orders~1new/get), field `requiredMeta`.


Request limit per one seller's account for all methods for getting and deleting In-Store Pickup metadata:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 150 requests | 400 ms | 20 requests |

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
| `meta` | array | ✓ | Assembly orders metadata |

[Response 200](../_shared/examples/POST__api_marketplace_v3_click_collect_orders_meta_info_200.json)

- **400** Bad Request
- **401** Unauthorized
- **403** Forbidden
- **429** Too Many Requests
