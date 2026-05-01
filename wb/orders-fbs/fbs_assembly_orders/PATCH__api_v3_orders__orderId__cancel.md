# `PATCH` /api/v3/orders/{orderId}/cancel

**Tag:** [FBS Assembly Orders](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Cancel the Assembly Order**

Описание метода

Moves the assembly orders to `cancel` ("Canceled by the supplier") status.


Request limit per one seller's account:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 100 requests | 600 ms | 20 requests |

One request with a response code of 409 is counted as 10 requests


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `orderId` | path | integer | ✓ | Assembly order ID *Example: `5632423`* |

## Responses

- **204** Canceled
### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data for the error |

[Response 400: IncorrectParameter](../_shared/examples/GET__api_v3_orders_400_IncorrectParameter.json)

- **401** Unauthorized
- **402** Payment Required
- **403** Forbidden
- **404** Not Found
### `409` Error updating a status


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data for the error |

[Response 409: StatusMismatch](../_shared/examples/PATCH__api_v3_orders__orderId__cancel_409_StatusMismatch.json)


[Response 409: StatusChangeNotAllowed](../_shared/examples/PATCH__api_v3_orders__orderId__cancel_409_StatusChangeNotAllowed.json)

- **429** Too Many Requests
