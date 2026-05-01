# `POST` /v1/supply-order/status/counter

**Tag:** [FBO](index.md)

**operationId:** `SupplyOrderAPI_SupplyOrderStatusCounter`

**Количество заявок по статусам**

Возвращает количество заявок в конкретном статусе.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Responses

### `200` Статус заявки и количество заявок в этом статусе


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `items` | array |  |  |

[Response 200](../_shared/examples/POST__v1_supply_order_status_counter_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
