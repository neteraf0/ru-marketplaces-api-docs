# `POST` /v1/posting/cancel/status

**Tag:** [FboPostingAPI](index.md)

**operationId:** `PostingAPI_PostingCancelStatus`

**Проверить статус отмены отправления**

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `posting_number` | string |  | Идентификатор отправления. |
## Responses

### `200` Статус отмены отправления


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `order_number` | string |  | Номер заказа. |
| `posting_number` | array |  | Идентификатор отправления. |
| `state` | string |  | Статус отмены отправления. |

[Response 200](../_shared/examples/POST__v1_order_cancel_status_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
