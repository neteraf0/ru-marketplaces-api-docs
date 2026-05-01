# `POST` /v1/supply-order/timeslot/get

**Tag:** [FBO](index.md)

**operationId:** `SupplyOrderAPI_GetSupplyOrderTimeslots`

**Интервалы поставки**

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
## Responses

### `200` Список интервалов поставки


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `timeslots` | array |  | Интервалы поставки. |
| `timezone` |  |  | Часовой пояс. |

[Response 200](../_shared/examples/POST__v1_supply_order_timeslot_get_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
