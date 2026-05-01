# `POST` /v1/carriage/pass/delete

**Tag:** [Pass](index.md)

**operationId:** `carriagePassDelete`

**Удалить пропуск**

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `arrival_pass_ids` | array | ✓ | Идентификаторы пропусков. |
| `carriage_id` | integer | ✓ | Идентификатор перевозки. |
## Responses

### `200` Пропуск удалён


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
