# `POST` /v1/pricing-strategy/product/info

**Tag:** [PricingStrategyAPI](index.md)

**operationId:** `pricing_items-info`

**Цена товара у конкурента**

Если вы добавили товар в стратегию ценообразования, метод вернёт цену и ссылку на товар у конкурента.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `product_id` | integer | ✓ | Идентификатор товара в системе Ozon — `product_id`. |

[Request example](examples/POST__v1_pricing_strategy_product_info_req.json)

## Responses

### `200` Цена товара у конкурента


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | v1GetStrategyItemInfoResponseResult |  | Результат работы метода. |

[Response 200](../_shared/examples/POST__v1_pricing_strategy_product_info_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
