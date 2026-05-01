# `POST` /v1/cancel-reason/list-by-order

**Tag:** [CancelReasonAPI](index.md)

**operationId:** `CancelReasonListByOrder`

**Причины отмены заказа**

Возвращает возможные причины отмены для заказа.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `order_number` | string | ✓ | Номер заказа. |
## Responses

### `200` Причины отмены заказа


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `reasons` | array |  | Информация о причинах отмены. |

[Response 200](../_shared/examples/POST__v1_cancel_reason_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
