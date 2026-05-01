# `POST` /v1/pricing-strategy/products/list

**Tag:** [PricingStrategyAPI](index.md)

**operationId:** `pricing_items-list`

**Список товаров в стратегии**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `strategy_id` | string | ✓ | Идентификатор стратегии. |

[Request example](examples/POST__v1_pricing_strategy_products_list_req.json)

## Responses

### `200` Список товаров


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | v1GetStrategyItemsResponseResult |  | Список товаров. |

[Response 200](../_shared/examples/POST__v1_pricing_strategy_products_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
