# `POST` /v1/cancel-reason/list-by-posting

**Tag:** [CancelReasonAPI](index.md)

**operationId:** `CancelReasonAPI_CancelReasonListByPosting`

**Причины отмены отправления**

Возвращает возможные причины отмены для отправления.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `posting_number` | string | ✓ | Номер отправления. |
## Responses

### `200` Причины отмены отправления


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
