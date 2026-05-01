# `POST` /v1/draft/supply/create/status

**Tag:** [FboSupplyRequest](index.md)

**operationId:** `SupplyDraftAPI_DraftSupplyCreateStatus`

**Информация о создании заявки на поставку**


Метод устаревает и будет отключён 16 марта 2026 года. Используйте /v2/draft/supply/create/status.


## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `operation_id` | string | ✓ | Идентификатор заявки на поставку. |
## Responses

### `200` Информация о создании заявки на поставку


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `error_messages` | array |  | Ошибки создания заявок. |
| `result` | DraftSupplyCreateStatusResponseResult |  | Идентификаторы заявок на поставку. |
| `status` | v1DraftSupplyCreateStatus |  | Статус создания заявки на поставку:   - `DraftSupplyCreateStatusUnknown` — неизвестный,   - `DraftSupplyCreateStatusSuccess` — создана,   - `DraftSupplyCreateStatusFailed` — не создана,   - `DraftSupplyCreateStatusInProgress` — создаётся.  |

[Response 200](../_shared/examples/POST__v1_draft_supply_create_status_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
