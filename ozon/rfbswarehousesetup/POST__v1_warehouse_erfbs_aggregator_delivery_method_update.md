# `POST` /v1/warehouse/erfbs/aggregator/delivery-method/update

**Tag:** [rFBSWarehouseSetup](index.md)

**operationId:** `WarehouseERFBSAggregatorDeliveryMethodUpdate`

**Обновить метод доставки «Партнёры Ozon»**

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
| `courier_comment` | string |  | Комментарий для курьера. |
| `courier_phones` | array |  | Номера телефонов для связи с курьером. |
| `cut_in` | integer (enum: 15, 30, 60, 120, 180, 240, 300, 360, 420, 480) |  | Время сборки. |
| `deliver_to_pvz` | boolean |  | `true`, если доставка Ozon Express в пункт выдачи Ozon.  |
| `delivery_costs` | v1WarehouseERFBSAggregatorDeliveryMethodUpdateRequestDeliveryCosts |  | Расходы на доставку, которые вы готовы оплатить. |
| `delivery_method_id` | integer | ✓ | Идентификатор метода доставки. |
| `name` | string |  | Название метода доставки. |
| `return_settings` | v1WarehouseERFBSAggregatorDeliveryMethodUpdateRequestReturnSettings |  | Настройки возвратов от покупателей. |
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
