# `POST` /api/marketplace/v3/click-collect/orders/meta/sgtin

**Tag:** [In-Store Pickup Metadata](index.md)

**Add Labeling codes Chestny ZNAK to the Assembly Orders (Chestny ZNAK)**

Описание метода

The method sets labeling code [Chestny ZNAK](https://chestnyznak.ru/en) to the [assembly orders metadata](./in-store-pickup#tag/In-Store-Pickup-Metadata/paths/~1api~1marketplace~1v3~1click-collect~1orders~1meta~1info/post).
You can set the labeling codes Chestny ZNAK only for orders in the `confirm` status and if the field `sgtin` is returned in the response of the [Get order metadata](./in-store-pickup#tag/In-Store-Pickup-Metadata/paths/~1api~1marketplace~1v3~1click-collect~1orders~1meta~1info/post) method.
You can get the uploaded labeling codes in the [assembly orders metadata](./in-store-pickup#tag/In-Store-Pickup-Metadata/paths/~1api~1marketplace~1v3~1click-collect~1orders~1meta~1info/post).

For more information about labeling codes Chestny ZNAK please check: https://chestnyznak.ru/en/.


Request limit per one seller's account for all methods for adding In-Store Pickup metadata:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 20 requests | 3 s | 500 requests |

One request with a response code of 409 is counted as 10 requests


## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `orders` | array | ✓ |  |
## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `requestId` |  | ✓ | Unique request ID *Example: `f1787bd2d1fdс35d6f537316514у4a05`* |
| `results` | array | ✓ |  |

[Response 200](../_shared/examples/POST__api_marketplace_v3_click_collect_orders_status_confirm_200.json)

- **400** Bad Request
- **401** Unauthorized
- **403** Forbidden
- **429** Too Many Requests
