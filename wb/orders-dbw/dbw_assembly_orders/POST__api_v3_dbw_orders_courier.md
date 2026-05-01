# `POST` /api/v3/dbw/orders/courier

**Tag:** [DBW Assembly Orders](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Courier Info**

Описание метода

Method provides the courier's contact information and vehicle number based on the assembly order ID. For assembly orders in the statuses `confirm` and `complete`.


Request limit  per one seller's account for DBW methods:

    for getting and updating contact lists
    for getting and deleting metadata
    assembly orders


| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 300 requests | 200 ms | 20 requests |


## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `orders` | array |  | Assembly order IDs list |
## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `orders` | array |  |  |

[Response 200](../_shared/examples/POST__api_v3_dbw_orders_courier_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data for the error |

[Response 400: IncorrectParameter](../_shared/examples/GET__api_v3_dbw_orders_400_IncorrectParameter.json)


[Response 400: IncorrectRequestBody](../_shared/examples/POST__api_v3_dbw_orders_delivery_date_400_IncorrectRequestBody.json)


[Response 400: IncorrectRequest](../_shared/examples/POST__api_v3_dbw_orders_delivery_date_400_IncorrectRequestBody.json)

- **401** Unauthorized
- **402** Payment Required
- **403** Forbidden
- **429** Too Many Requests
