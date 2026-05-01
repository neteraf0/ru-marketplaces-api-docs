# `POST` /v1/pricing-strategy/products/delete

**Tag:** [PricingStrategyAPI](index.md)

**operationId:** `pricing_items-delete`

**Удалить товары из стратегии**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `product_id` | array | ✓ | Список идентификаторов товаров в системе Ozon — `product_id`. Максимальное количество — 50. |

[Request example](examples/POST__v1_pricing_strategy_products_delete_req.json)

## Responses

### `200` Ошибки при удалении товаров


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | v1DeleteStrategyItemsResponseResult |  | Результат работы метода. |

[Response 200](../_shared/examples/POST__v1_pricing_strategy_products_delete_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
