# `POST` /v1/warehouse/fbs/return-mile/check

**Tag:** [FBSWarehouseSetup](index.md)

**operationId:** `WarehouseFbsReturnMileCheck`

**Проверить необходимость установки возвратной мили на склад**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `country_code` | string | ✓ | Код страны в формате ISO 2. |
| `first_mile_type` | v1WarehouseFbsReturnMileCheckRequestFirstMileTypeEnum | ✓ | Тип первой мили: - `PICK_UP` — отгрузка заказов курьеру; - `DROP_OFF` — отгрузка заказов в пункт приёма.  |
| `is_kgt` | boolean | ✓ | Признак крупногабаритного товара. |
| `warehouse_id` | integer |  | Идентификатор склада. |
## Responses

### `200` Успешно


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `should_set_return_mile` | boolean |  | Признак, что необходимо установить возвратную милю. |
| `unavailability_reasons` | array |  | Причины, по которым нельзя установить возвратную милю. |

[Response 200](../_shared/examples/POST__v1_warehouse_fbs_return_mile_check_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
