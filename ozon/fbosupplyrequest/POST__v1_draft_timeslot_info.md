# `POST` /v1/draft/timeslot/info

**Tag:** [FboSupplyRequest](index.md)

**operationId:** `SupplyDraftAPI_DraftTimeslotInfo`

**Доступные таймслоты**


Метод устаревает и будет отключён 16 марта 2026 года. Используйте /v2/draft/timeslot/info.


Черновик заявки на поставку доступен 30 минут.

Возвращает доступные таймслоты на конечных складах отгрузки. Для кросс-док поставок вернутся таймслоты склада отгрузки, который был передан при создании черновика.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `date_from` | string | ✓ | Дата начала нужного периода доступных таймслотов. |
| `date_to` | string | ✓ | Дата окончания нужного периода доступных таймслотов.  Максимальный период — 28 дней с текущей даты.  |
| `draft_id` | integer | ✓ | Идентификатор черновика заявки на поставку. Получите методом [/v1/draft/create/info](#operation/SupplyDraftAPI_DraftCreateInfo). |
| `warehouse_ids` | array | ✓ | Идентификаторы складов размещения. |
## Responses

### `200` Таймслоты


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `drop_off_warehouse_timeslots` | array |  | Таймслоты складов. |
| `requested_date_from` | string |  | Дата начала интересующего периода. |
| `requested_date_to` | string |  | Дата окончания интересующего периода. |

[Response 200](../_shared/examples/POST__v1_draft_timeslot_info_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
