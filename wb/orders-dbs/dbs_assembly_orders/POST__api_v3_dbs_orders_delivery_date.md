# `POST` /api/v3/dbs/orders/delivery-date

**Tag:** [DBS Assembly Orders](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Delivery Date and Time**

Описание метода

Method provides information about the delivery date and time selected by the buyer for orders.


Request limit per one seller's account for DBS assembly orders methods:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 300 requests | 200 ms | 20 requests |


## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `orders` | array |  | List of orders IDs |
## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `orders` | array |  |  |

[Response 200](../_shared/examples/POST__api_v3_dbs_orders_delivery_date_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data for the error |

[Response 400: IncorrectRequest](../_shared/examples/POST__api_v3_dbs_orders_delivery_date_400_IncorrectRequest.json)


[Response 400: IncorrectRequestBody](../_shared/examples/POST__api_v3_dbs_groups_info_400_IncorrectRequestBody.json)

- **401** Unauthorized
- **402** Payment Required
- **403** Forbidden
- **429** Too Many Requests
