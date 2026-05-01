# `POST` /v1/carriage/pass/update

**Tag:** [Pass](index.md)

**operationId:** `carriagePassUpdate`

**Обновить пропуск**

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `arrival_passes` | array | ✓ | Список пропусков. |
| `carriage_id` | integer | ✓ | Идентификатор перевозки. |
## Responses

### `200` Пропуск обновлён


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 200](../_shared/examples/POST__v1_pricing_strategy_update_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
