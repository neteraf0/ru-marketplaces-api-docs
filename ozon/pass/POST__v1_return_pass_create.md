# `POST` /v1/return/pass/create

**Tag:** [Pass](index.md)

**operationId:** `returnPassCreate`

**Создать пропуск для возврата**

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `arrival_passes` | array | ✓ | Список пропусков. |
## Responses

### `200` Пропуск создан


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `arrival_pass_ids` | array |  | Идентификаторы пропусков. |

[Response 200](../_shared/examples/POST__v1_carriage_pass_create_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
