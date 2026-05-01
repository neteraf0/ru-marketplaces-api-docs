# `POST` /api/v3/click-collect/orders/client/identity

**Tag:** [In-Store Pickup Assembly Orders](index.md)

**Check If the Order Belongs to the Buyer**

Описание метода

The method indicates whether the checked order belongs to the buyer based on the provided code.

Available if at least one assembly order from the order is in `prepare` status — ready for pickup.


Request limit per one seller's account:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 30 requests | 2 s | 20 requests |

One request with a response code of 409 is counted as 10 requests


## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `orderCode` | string |  | Unique buyer order ID |
| `passcode` | string |  | Confirmation code |
## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `ok` | boolean |  | Indicates whether the order belongs to the buyer:  - `true` — belongs  - `false` — the value is not applied. If the order does not belong to the buyer, you will receive a response with `409` status code  |

[Response 200](../_shared/examples/POST__api_v3_click_collect_orders_client_identity_200.json)

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
### `404` Not found


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  |  |
| `data` | object |  |  |
| `message` | string |  |  |

[Response 404: OrderNotFound](../_shared/examples/POST__api_v3_click_collect_orders_client_identity_404_OrderNotFound.json)

### `409` Incorrect verification code entered


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  |  |
| `data` | object |  |  |
| `message` | string |  |  |

[Response 409: InvalidPasscode](../_shared/examples/POST__api_v3_click_collect_orders_client_identity_409_InvalidPasscode.json)

- **429** Too Many Requests
