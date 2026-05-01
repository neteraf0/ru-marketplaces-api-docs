# `POST` /v1/warehouse/erfbs/non-integrated/create

**Tag:** [rFBSWarehouseSetup](index.md)

**operationId:** `WarehouseERFBSNonIntegratedCreate`

**Создать склад с методом доставки «Вы или сторонняя служба»**

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
| `address_coordinates` | v1WarehouseERFBSNonIntegratedCreateRequestAddressCoordinates | ✓ | Координаты адреса склада. |
| `delivery_method` | v1WarehouseERFBSNonIntegratedCreateRequestDeliveryMethod | ✓ | Информация о методе доставки «Вы или сторонняя служба». |
| `min_order_value` | integer |  | Минимальная стоимость заказа в рублях. |
| `name` | string | ✓ | Название склада. |
| `phone` | string | ✓ | Номер телефона склада. |
| `timetable_warehouse` | v1WarehouseERFBSNonIntegratedCreateRequestTimetableWarehouse | ✓ | Расписание работы склада. |
## Responses

### `200` Склад создан


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
