# `GET` /v1/supplier/available_warehouses

**Tag:** [FBO](index.md)

**operationId:** `SupplierAPI_SupplierAvailableWarehouses`

**Загруженность складов Ozon**

Метод возвращает список активных складов Ozon с информацией об их средней загруженности на ближайшее время.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Responses

### `200` Информация о загруженности складов


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` |  |  | Результат работы метода. |

[Response 200](../_shared/examples/GET__v1_supplier_available_warehouses_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
