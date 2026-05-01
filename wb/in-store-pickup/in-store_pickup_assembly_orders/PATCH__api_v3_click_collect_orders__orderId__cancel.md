# `PATCH` /api/v3/click-collect/orders/{orderId}/cancel

**Tag:** [In-Store Pickup Assembly Orders](index.md)

**Cancel the Assembly Order**

Описание метода

This method is deprecated. It will be removed on [May 19](https://dev.wildberries.ru/en/release-notes?id=474)


Request limit per one seller's account for In-Store Pickup assembly orders methods:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 min | 100 requests | 600 ms | 20 requests |
| Service | 1 min | 100 requests | 600 ms | 20 requests |
| Base | 1 h | 10 requests | 6 min | 1 request |

One request with a response code of 409 is counted as 10 requests


> ⚠️ **Deprecated**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `orderId` | path | integer | ✓ | Assembly order ID |

## Responses

- **204** Canceled
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
- **404** Not Found
### `409` Status update error


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data enriching the error |

[Response 409: StatusMismatch](../_shared/examples/PATCH__api_v3_click_collect_orders__orderId__confirm_409_StatusMismatch.json)

- **429** Too Many Requests
