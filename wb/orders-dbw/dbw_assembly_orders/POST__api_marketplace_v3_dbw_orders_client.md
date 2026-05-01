# `POST` /api/marketplace/v3/dbw/orders/client

**Tag:** [DBW Assembly Orders](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Buyer Information**

Описание метода

The method returns buyers information by order IDs.


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
| `orders` | array |  | Buyers information |

[Response 200](../_shared/examples/POST__api_marketplace_v3_dbw_orders_client_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data for the error |

[Response 400: IncorrectRequest](../_shared/examples/POST__api_v3_dbw_orders_delivery_date_400_IncorrectRequest.json)


[Response 400: IncorrectRequestBody](../_shared/examples/POST__api_v3_dbw_orders_delivery_date_400_IncorrectRequestBody.json)

- **401** Unauthorized
- **403** Forbidden
- **429** Too Many Requests
