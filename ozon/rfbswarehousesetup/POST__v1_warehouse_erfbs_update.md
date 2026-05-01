# `POST` /v1/warehouse/erfbs/update

**Tag:** [rFBSWarehouseSetup](index.md)

**operationId:** `WarehouseERFBSUpdate`

**Обновить склад**

[Подробнее о схеме realFBS Express](https://seller-edu.ozon.ru/rfbs/scheme-of-work/rfbs-express#%D1%87%D1%82%D0%BE-%D1%82%D0%B0%D0%BA%D0%BE%D0%B5-realfbs-express)

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `min_order_value` | integer |  | Минимальная стоимость заказа. |
| `name` | string |  | Название склада. |
| `phone` | string |  | Номер телефона склада. |
| `timetable_warehouse` | v1WarehouseERFBSUpdateRequestTimetableWarehouse |  | Расписание работы склада. |
| `warehouse_id` | integer | ✓ | Идентификатор склада. |
## Responses

### `200` Склад обновлён


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `operation_id` | string |  | Идентификатор операции. Получите статус операции методом [/v1/warehouse/operation/status](#operation/GetWarehouseFBSOperationStatus). |

[Response 200](../_shared/examples/POST__v1_warehouse_archive_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
