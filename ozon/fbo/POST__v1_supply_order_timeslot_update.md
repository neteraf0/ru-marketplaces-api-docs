# `POST` /v1/supply-order/timeslot/update

**Tag:** [FBO](index.md)

**operationId:** `SupplyOrderAPI_UpdateSupplyOrderTimeslot`

**Обновить интервал поставки**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `supply_order_id` | integer | ✓ | Идентификатор заявки на поставку. |
| `timeslot` | v1SupplyOrderTimeslot | ✓ | Время интервала поставки. |
## Responses

### `200` Интервал обновлён


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `errors` | array |  | Возможные ошибки:    - `UNSPECIFIED` — статус не указан;   - `INVALID_ORDER_STATE` — неверный статус заказа;   - `INCOMPATIBLE_ORDER_FLOW` — неверный статус интервала поставки;   - `SET_TIMESLOT_DEADLINE_EXCEED` — заявка на поставку просрочена;   - `OUT_OF_ALLOWED_RANGE` — вы ввели некорректное значение интервала поставки;   - `ORDER_NOT_BELONG_CONTRACTOR` — заявка создана другим юридическим лицом, работать с ней не получится;   - `ORDER_NOT_BELONG_COMPANY` — заявка не принадлежит вашему кабинету, работать с ней не получится;   - `UPDATE_TIMESLOT_ERROR_PICKUP_ORDER_LIMIT_EXCEEDED` — превышен суточный лимит на создание заявок на поставку курьером.  |
| `operation_id` | string |  | Идентификатор операции. |

[Response 200](../_shared/examples/POST__v1_supply_order_timeslot_update_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
