# `POST` /api/v3/click-collect/orders/client

**Tag:** [In-Store Pickup Assembly Orders](index.md)

**Buyer Information**

Описание метода

The method provides information about the buyer based on the assembly order ID.

Available only for assembly orders with the following statuses:
  - `confirm` — in assembly
  - `prepare` — ready for pickup

Restrictions:
- Information can only be obtained for assembly orders that are in the assembly process — status `confirm` and ready for pickup — status `prepare`.


Request limit per one seller's account for In-Store Pickup assembly orders methods:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 300 requests | 200 ms | 20 requests |

One request with a response code of 409 is counted as 10 requests


## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `orders` | array |  | Assembly orders IDs list |
## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `orders` | array |  |  |

[Response 200](../_shared/examples/POST__api_v3_click_collect_orders_client_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data enriching the error |

[Response 400: IncorrectRequestBody](../_shared/examples/POST__api_v3_click_collect_orders_client_400_IncorrectRequestBody.json)

- **401** Unauthorized
- **402** Payment Required
- **403** Forbidden
- **429** Too Many Requests
