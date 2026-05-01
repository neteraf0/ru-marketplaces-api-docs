# `POST` /v1/posting/cancel

**Tag:** [FboPostingAPI](index.md)

**operationId:** `PostingAPI_PostingCancel`

**Отменить отправление из заказа**

Отменяет отправление из заказа. Используйте идентификатор причины отмены `reasons.id` из метода [/v1/cancel-reason/list-by-posting](#operation/CancelReasonAPI_CancelReasonListByPosting).

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `posting_number` | string | ✓ | Номер отправления. |
| `reason_id` | integer | ✓ | Идентификатор причины отмены. |
| `reason_message` | string |  | Дополнительная информация по отмене. |
## Responses

### `200` Сообщение со статусом отмены


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `message` | string |  | Текст сообщения. |

[Response 200](../_shared/examples/POST__v1_order_cancel_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
