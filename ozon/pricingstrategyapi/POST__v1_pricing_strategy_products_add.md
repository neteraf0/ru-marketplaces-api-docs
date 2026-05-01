# `POST` /v1/pricing-strategy/products/add

**Tag:** [PricingStrategyAPI](index.md)

**operationId:** `pricing_items-add`

**Добавить товары в стратегию**

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `product_id` | array | ✓ | Список идентификаторов товаров в системе Ozon — `product_id`. Максимальное количество — 50. |
| `strategy_id` | string | ✓ | Идентификатор стратегии. |

[Request example](examples/POST__v1_pricing_strategy_products_add_req.json)

## Responses

### `200` Ошибки при добавлении товаров


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | v1AddStrategyItemsResponseResult |  | Результат работы метода. |

[Response 200](../_shared/examples/POST__v1_pricing_strategy_products_add_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
