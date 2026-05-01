# `POST` /v1/fbp/order/direct/timeslot/edit

**Tag:** [OrderDirectFBP](index.md)

**operationId:** `FbpAPI_FbpEditTimeslot`

**Отредактировать таймслот в заявке на поставку**

Вы можете оставить обратную связь по этому методу в комментариях к [обсуждению](https://dev.ozon.ru/community/1700-FBP-metody/) в сообществе разработчиков Ozon for dev.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `row_version` | integer | ✓ | Идентификатор актуальной версии черновика. |
| `supply_id` | string | ✓ | Идентификатор заявки на поставку. |
| `timeslot_start` | string | ✓ | Начало таймслота. |
## Responses

### `200` Таймслот отредактирован


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `error_reasons` | array |  | Причина ошибки: - `RESERVE_FAILURE_TYPE_UNSPECIFIED` — не определена; - `REQUEST_VALIDATION` — в запросе указана дата резервирования в прошлом; - `INVALID_RESERVE` — исходный резерв не найден, неактивен или уже содержит заявки, а его пытаются перезаписать; - `LOGISTICS_REASON` — ошибка на стороне логистики; - `SCHEDULE_REASON` — ошибка на стороне расписаний.  |
| `row_version` | integer |  | Идентификатор актуальной версии черновика. |

[Response 200](../_shared/examples/POST__v1_fbp_draft_direct_timeslot_edit_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
