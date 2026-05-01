# `POST` /v1/draft/supply/create

**Tag:** [FboSupplyRequest](index.md)

**operationId:** `SupplyDraftAPI_DraftSupplyCreate`

**Создать заявку на поставку по черновику**


Метод устаревает и будет отключён 16 марта 2026 года. Используйте /v2/draft/supply/create.


## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `draft_id` | integer | ✓ | Идентификатор черновика заявки на поставку. |
| `timeslot` | v1DayTimeSlot |  | Таймслот поставки. |
| `warehouse_id` | integer | ✓ | Идентификатор склада размещения. Можно получить с помощью метода [/v1/draft/create/info](#operation/SupplyDraftAPI_DraftCreateInfo). |
## Responses

### `200` Заявка создана


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `operation_id` | string |  | Идентификатор заявки на поставку. |

[Response 200](../_shared/examples/POST__v1_warehouse_archive_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
