# `POST` /api/v3/click-collect/orders/status

**Tag:** [In-Store Pickup Assembly Orders](index.md)

**Get Assembly Order Statuses**

Описание метода

This method is deprecated. It will be removed on [May 19](https://dev.wildberries.ru/en/release-notes?id=474)

> ⚠️ **Deprecated**

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `orders` | array |  | Assembly orders IDs list |
## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `orders` | array |  | List of assembly order statuses |

[Response 200](../_shared/examples/POST__api_v3_click_collect_orders_status_200.json)

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
