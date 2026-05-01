# `POST` /api/v3/dbw/orders/delivery-date

**Tag:** [DBW Assembly Orders](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Delivery Date and Time**

Описание метода

Method provides information about the delivery date and time selected by the buyer for orders.


Request limit per one seller's account for DBW methods:

    for getting and updating contact lists
    for getting and deleting metadata
    assembly orders


| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 300 requests | 200 ms | 20 requests |

One request with a response code of 409 is counted as 10 requests


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

[Response 200](../_shared/examples/POST__api_v3_dbw_orders_delivery_date_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data for the error |

[Response 400: IncorrectRequest](../_shared/examples/POST__api_v3_dbw_orders_delivery_date_400_IncorrectRequest.json)


[Response 400: IncorrectRequestBody](../_shared/examples/POST__api_v3_dbw_orders_delivery_date_400_IncorrectRequestBody.json)

- **401** Unauthorized
- **402** Payment Required
- **403** Forbidden
- **429** Too Many Requests
