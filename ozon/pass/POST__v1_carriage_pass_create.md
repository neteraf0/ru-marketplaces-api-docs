# `POST` /v1/carriage/pass/create

**Tag:** [Pass](index.md)

**operationId:** `carriagePassCreate`

**Создать пропуск**

Идентификатор созданного пропуска добавится к перевозке.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `arrival_passes` | array | ✓ | Список пропусков. |
| `carriage_id` | integer | ✓ | Идентификатор перевозки. |
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
