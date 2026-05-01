# `POST` /v1/order/cancel/check

**Tag:** [OrderAPI](index.md)

**operationId:** `OrderAPI_OrderCancelCheck`

**Проверить возможность отмены заказа**

Возвращает возможность отмены заказа для покупателя.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `order_number` | string | ✓ | Номер заказа. |
## Responses

### `200` Результат проверки


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `cancellable` | boolean |  | `true`, если заказ можно отменить.  |
| `order_number` | string |  | Номер заказа. |
| `posting_groups` | array |  | Группы отправлений. |
| `postings` | array |  | Информация о возможности отмены отправлений. |

[Response 200](../_shared/examples/POST__v1_order_cancel_check_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
