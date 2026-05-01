# `POST` /v1/warehouse/warehouses-with-invalid-products

**Tag:** [WarehouseAPI](index.md)

**operationId:** `WarehouseWithInvalidProducts`

**Получить список складов с ограниченными для доставки товарами**

Возвращает идентификаторы складов, на которых находятся товары с ограничениями. Такие товары недоступны для доставки со склада.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Responses

### `200` Список складов


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `warehouse_ids` | array |  | Список идентификаторов складов, у которых есть хотя бы 1 товар, который недоступен для доставки со склада. Чтобы получить список товаров с ограничениями, используйте метод [/v1/warehouse/invalid-products/get](#operation/WarehouseInvalidProductsGet). |

[Response 200](../_shared/examples/POST__v1_warehouse_warehouses_with_invalid_products_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
