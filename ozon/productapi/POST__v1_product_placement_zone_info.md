# `POST` /v1/product/placement-zone/info

**Tag:** [ProductAPI](index.md)

**operationId:** `ProductAPI_GetProductPlacementZoneInfo`

**Получить зоны размещения товаров по SKU перед поставкой**

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `skus` | array | ✓ | Список идентификаторов товаров в системе Ozon — SKU. |
## Responses

### `200` Информация о зонах размещения


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `products_placement` | array |  | Список товаров с их зонами размещения. |

[Response 200](../_shared/examples/POST__v1_product_placement_zone_info_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
