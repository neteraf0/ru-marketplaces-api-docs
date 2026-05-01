# `POST` /v1/supply-order/pass/status

**Tag:** [FBO](index.md)

**operationId:** `SupplyOrderAPI_SupplyOrderPassStatus`

**Статус ввода данных о водителе и автомобиле**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `operation_id` | string | ✓ | Идентификатор операции. |
## Responses

### `200` Статус


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `errors` | array |  | Причина ошибки: - `UNSPECIFIED` — статус не указан; - `INVALID_ORDER_STATE` — неверный статус заявки; - `VEHICLE_NOT_REQUIRED` — указывать данные автомобиля необязательно; - `ORDER_NOT_BELONG_CONTRACTOR` — заявка создана другим юридическом лицом, работать с ней не получится; - `ORDER_NOT_BELONG_COMPANY` — заявка не принадлежит вашему кабинету, работать с ней не получится.  |
| `result` | v1SupplyOrderPassStatusResponseStatus |  | Статус ввода данных о водителе и автомобиле: - `Unknown` — статус неизвестен; - `Success` — данные указаны; - `InProgress` — данные обрабатываются; - `Failed` — не удалось обработать данные.  |

[Response 200](../_shared/examples/POST__v1_supply_order_pass_status_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
