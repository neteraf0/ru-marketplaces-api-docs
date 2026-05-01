# `POST` /v1/supply-order/bundle

**Tag:** [FBO](index.md)

**operationId:** `SupplyOrderBundle`

**Состав поставки или заявки на поставку**

Используйте метод, чтобы получить товарный состав поставки или черновика заявки на поставку.
Одним вызовом метода можно получить состав одной поставки или черновика заявки.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `bundle_ids` | array | ✓ | Идентификаторы товарного состава поставки. Можно получить в методе [/v3/supply-order/get](#operation/SupplyOrderGet). |
| `is_asc` | boolean |  | `true`, чтобы сортировать по возрастанию.  |
| `item_tags_calculation` | GetSupplyOrderBundleRequestItemTagsCalculation |  | Список складов для расчёта товарных тегов. |
| `last_id` | string |  | Идентификатор последнего значения SKU на странице. |
| `limit` | integer | ✓ | Количество товаров на странице. |
| `query` | string |  | Поисковый запрос, например: по названию, артикулу или SKU.  |
| `sort_field` | v1ItemSortField |  | Сортировка по параметрам: - `SKU` — SKU; - `NAME` — названию товара; - `QUANTITY` — количеству; - `TOTAL_VOLUME_IN_LITRES` — объёму в литрах.  |

[Request example](examples/POST__v1_supply_order_bundle_req.json)

## Responses

### `200` Состав поставки


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `items` | array |  | Список товаров в заявке на поставку. |
| `total_count` | integer |  | Количество товаров в заявке. |
| `has_next` | boolean |  | Признак, что в ответе вернули не все товары: - `true` — сделайте повторный запрос с другим значением `last_id`, чтобы получить остальные значения; - `false` — ответ содержит все значения характеристики.  |
| `last_id` | string |  | Идентификатор последнего значения на странице. |

[Response 200](../_shared/examples/POST__v1_supply_order_bundle_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
