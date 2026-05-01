# `POST` /v1/warehouse/ozon/list

**Tag:** [BetaMethod](index.md)

**operationId:** `WarehouseOZONList`

**Получить список складов Ozon**

Возвращает список складов Ozon, которые работают по схемам FBO и FBO Fresh, и возвратных складов.

Вы можете оставить обратную связь о работе метода в [комментариях](https://dev.ozon.ru/community/1889-Novyi-metod-dlia-polucheniia-FBO-skladov/) в сообществе разработчиков Ozon for dev.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `warehouse_types` | array |  | Тип склада Ozon: - `FULL_FILLMENT` — фулфилмент; - `FULL_FILLMENT_RETURNS` — склад возвратов; - `FULL_FILLMENT_DEFECT` — склад брака; - `EXPRESS_DARK_STORE` — фреш; - `CROSS_DOCK` — кросс-док; - `SORTING_CENTER` — сортировочный центр; - `PHARMACY` — склад аптеки; - `DISTRIBUTION_CENTER` — распределительный центр; - `ORDERS_RECEIVING_POINT` — пункты приёма заказов; - `OUTSOURCE_FF` — аутсорс-склады; - `B2B` — B2B-склад; - `EXTERNAL_FF` — склады партнёров.  |
## Responses

### `200` Список складов Ozon


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `warehouses` | array |  | Список складов. |

[Response 200](../_shared/examples/POST__v1_warehouse_ozon_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
