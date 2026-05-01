# `POST` /v1/supply-order/pass/create

**Tag:** [FBO](index.md)

**operationId:** `SupplyOrderAPI_SupplyOrderPassCreate`

**Указать данные о водителе и автомобиле**

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
| `vehicle` | v1VehicleInfo | ✓ | Информация о водителе и автомобиле. |
## Responses

### `200` Данные указаны


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `error_reasons` | array |  | Причина ошибки:   - `UNSPECIFIED` — статус заявки не указан;   - `INVALID_ORDER_STATE` — неверный статус заявки;   - `VEHICLE_NOT_REQUIRED` — указывать данные автомобиля необязательно;   - `ORDER_NOT_BELONG_CONTRACTOR` — заявка создана другим юридическом лицом, работать с ней не получится;   - `ORDER_NOT_BELONG_COMPANY` — заявка не принадлежит вашему кабинету, работать с ней не получится.  |
| `operation_id` | string |  | Идентификатор операции. |

[Response 200](../_shared/examples/POST__v1_supply_order_pass_create_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
