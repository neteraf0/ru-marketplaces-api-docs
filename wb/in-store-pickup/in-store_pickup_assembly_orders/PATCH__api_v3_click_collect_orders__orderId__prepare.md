# `PATCH` /api/v3/click-collect/orders/{orderId}/prepare

**Tag:** [In-Store Pickup Assembly Orders](index.md)

**Notify That the Assembly Order Is Ready for Pickup**

Описание метода

This method is deprecated. It will be removed on [May 19](https://dev.wildberries.ru/en/release-notes?id=474)

> ⚠️ **Deprecated**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `orderId` | path | integer | ✓ | Assembly order ID |

## Responses

- **204** Confirmed
### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data enriching the error |

[Response 400: IncorrectParameter](../_shared/examples/PATCH__api_v3_click_collect_orders__orderId__confirm_400_IncorrectParameter.json)

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
