# `PATCH` /api/v3/dbw/orders/{orderId}/cancel

**Tag:** [DBW Assembly Orders](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Cancel the Order**

Описание метода

Moves the assembly order to `cancel` status — canceled by the seller.


Request limit per one seller's account for the DBW methods:

    for getting and updating contact lists
    for getting and deleting metadata
    for managing assembly orders


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 min | 300 requests | 200 ms | 20 requests |
| Service | 1 min | 300 requests | 200 ms | 20 requests |
| Base | 1 h | 10 requests | 6 min | 1 request |

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

[Response 400: IncorrectParameter](../_shared/examples/GET__api_v3_dbw_orders_400_IncorrectParameter.json)

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

[Response 409: StatusMismatch](../_shared/examples/PATCH__api_v3_dbw_orders__orderId__confirm_409_StatusMismatch.json)

- **429** Too Many Requests
