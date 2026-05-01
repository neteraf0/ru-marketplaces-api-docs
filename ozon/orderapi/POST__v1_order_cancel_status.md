# `POST` /v1/order/cancel/status

**Tag:** [OrderAPI](index.md)

**operationId:** `OrderAPI_OrderCancelStatus`

**Получить статус отмены заказа**

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `order_number` | string | ✓ | Номер заказа. |
## Responses

### `200` Статус отмены заказа


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `order_number` | string |  | Номер заказа. |
| `posting_number` | array |  | Список отправлений в заказе. |
| `state` | string |  | Статус отмены заказа. |

[Response 200](../_shared/examples/POST__v1_order_cancel_status_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
