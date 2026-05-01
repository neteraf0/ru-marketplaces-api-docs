# `POST` /v1/fbp/draft/direct/timeslot/get

**Tag:** [DraftDirectFBP](index.md)

**operationId:** `FbpDraftDirectGetTimeslot`

**Получить список таймслотов для прямой поставки**

Вы можете оставить обратную связь о работе метода в [комментариях](https://dev.ozon.ru/community/1700-FBP-metody/) в сообществе разработчиков Ozon for dev.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `bundle_id` | string | ✓ | Идентификатор провалидированного списка товаров. |
| `interval_end` | string | ✓ | Дата окончания нужного периода доступных таймслотов. |
| `interval_start` | string | ✓ | Дата начала нужного периода доступных таймслотов. |
| `warehouse_id` | integer | ✓ | Идентификатор склада продавца. |
## Responses

### `200` Список таймслотов


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `reasons` | array |  | Причины отсутствия таймслотов: - `EMPTY_TIMESLOTS_REASON_UNSPECIFIED` — не определено; - `LOGISTICS_UNKNOWN` — неизвестная ошибка на стороне логистики; - `NO_ROUTE` — нет маршрута; - `NO_ROUTE_SCHEDULES` — нет расписания на маршруте; - `NO_LOGISTICS_CAPACITY` — недостаточно доступных слотов на маршруте; - `SCHEDULE_UNKNOWN` — неизвестная ошибка на стороне расписаний; - `NOT_ENOUGH_CAPACITY` — недостаточно доступных слотов на складе; - `NOT_ENOUGH_TRUCKS` — недостаточно машиномест; - `LIMITS_NOT_AVAILABLE` — не настроены лимиты на складе; - `CROSS_DOCK_RESERVE_MISSING` — не забронирован кросс-докинговый резерв на складе; - `SCHEDULE_RESERVE_MISSING` — отсутствует необходимый резерв по расписанию.  |
| `timeslots` | array |  | Список доступных таймслотов. |
| `warehouse_timezone_name` | string |  | Часовой пояс склада продавца. |

[Response 200](../_shared/examples/POST__v1_fbp_draft_direct_timeslot_get_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
