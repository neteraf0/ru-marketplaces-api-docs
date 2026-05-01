# `POST` /v1/pricing-strategy/strategy-ids-by-product-ids

**Tag:** [PricingStrategyAPI](index.md)

**operationId:** `pricing_ids`

**Список идентификаторов стратегий**

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

[Request example](examples/POST__v1_pricing_strategy_strategy_ids_by_product_ids_req.json)

## Responses

### `200` Список идентификаторов


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | v1GetStrategyIDsByItemIDsResponseResult |  | Результат работы метода. |

[Response 200](../_shared/examples/POST__v1_pricing_strategy_strategy_ids_by_product_ids_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
