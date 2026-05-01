# `POST` /v1/cancel-reason/list

**Tag:** [CancelReasonAPI](index.md)

**operationId:** `CancelReasonList`

**Причины отмены отправлений**

Возвращает возможные причины отмены отправлений и заказов.

## Responses

### `200` Причины отмены отправлений


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
