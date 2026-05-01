# `POST` /v2/draft/timeslot/info

**Tag:** [FboSupplyRequest](index.md)

**operationId:** `DraftTimeslotInfo`

**Получить список доступных таймслотов**


Не используйте в запросе draft_id из метода /v1/draft/create/info, иначе вернётся ошибка.


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `date_from` | string | ✓ | Дата начала периода доступных таймслотов. |
| `date_to` | string | ✓ | Дата окончания периода доступных таймслотов.  Максимальный период — 28 дней с текущей даты.  |
| `draft_id` | integer | ✓ | Идентификатор черновика из метода [/v2/draft/create/info](#operation/DraftCreateInfo). |
| `supply_type` | string (enum: CROSSDOCK, DIRECT, MULTI_CLUSTER) | ✓ | Тип поставки: - `CROSSDOCK` — кросс-докинг; - `DIRECT` — прямая; - `MULTI_CLUSTER` — для нескольких кластеров.  |
| `selected_cluster_warehouses` | array | ✓ | Информация о кластере и складах в нём. Можно передать один кластер для кросс-докинговой и прямой поставки или список всех кластеров для поставки в несколько кластеров. |
## Responses

### `200` Список таймслотов


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `error_reason` | v2DraftTimeslotInfoResponseErrorReasonEnum |  | Причина ошибки: - `UNSPECIFIED` — не определена; - `INVALID_CLUSTERS_COUNT` — переданы не все кластеры из расчёта; - `REQUESTED_PERIOD_MORE_THAN_MAX` — превышен период; - `INVALID_REQUESTED_CLUSTER_IDS` — переданы кластеры, которых нет в расчёте. - `UNDEFINED` — неизвестная ошибка.  |
| `result` | DraftTimeslotInfoResponseResult |  | Информация о таймслотах. |

[Response 200](../_shared/examples/POST__v2_draft_timeslot_info_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
