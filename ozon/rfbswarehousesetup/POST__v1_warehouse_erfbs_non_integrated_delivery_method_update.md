# `POST` /v1/warehouse/erfbs/non-integrated/delivery-method/update

**Tag:** [rFBSWarehouseSetup](index.md)

**operationId:** `WarehouseERFBSNonIntegratedDeliveryMethodUpdate`

**Обновить метод доставки «Вы или сторонняя служба»**

[Подробнее о схеме rFBS Express](https://seller-edu.ozon.ru/rfbs/scheme-of-work/rfbs-express#%D1%87%D1%82%D0%BE-%D1%82%D0%B0%D0%BA%D0%BE%D0%B5-realfbs-express)

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `courier_cutoff` | integer (enum: 5, 10, 15, 20, 25, 30, 35, 40, 45) | ✓ | Скорость отгрузки. |
| `cut_in` | integer (enum: 15, 30, 60, 120, 180, 240, 300, 360, 420, 480) | ✓ | Время сборки. |
| `delivery_method_id` | integer | ✓ | Идентификатор метода доставки. |
| `name` | string | ✓ | Название метода доставки. |
| `return_settings` | v1WarehouseERFBSNonIntegratedDeliveryMethodUpdateRequestReturnSettings | ✓ | Настройки возвратов от покупателей. |
| `warehouse_id` | integer | ✓ | Идентификатор склада. |
## Responses

### `200` Успешно


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
