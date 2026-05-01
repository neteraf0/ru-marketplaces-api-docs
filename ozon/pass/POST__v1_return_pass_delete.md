# `POST` /v1/return/pass/delete

**Tag:** [Pass](index.md)

**operationId:** `returnPassDelete`

**Удалить пропуск для возврата**

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `arrival_pass_ids` | array | ✓ | Идентификаторы пропусков. |
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
