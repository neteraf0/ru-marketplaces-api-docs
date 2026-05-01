# `POST` /v1/order/cancel

**Tag:** [OrderAPI](index.md)

**operationId:** `OrderAPI_OrderCancel`

**Отменить заказ**

Отменяет заказ со всеми отправлениями. Используйте идентификатор причины отмены `reasons.id` из метода [/v1/cancel-reason/list-by-order](#operation/CancelReasonListByOrder).

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `order_number` | string | ✓ | Номер заказа. |
| `reason_id` | integer | ✓ | Идентификатор причины отмены заказа. |
| `reason_message` | string |  | Причина отмены заказа. |
## Responses

### `200` Заказ отменён


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `message` | string |  | Статус обработки отмены. |

[Response 200](../_shared/examples/POST__v1_order_cancel_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
