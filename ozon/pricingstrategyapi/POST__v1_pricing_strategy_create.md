# `POST` /v1/pricing-strategy/create

**Tag:** [PricingStrategyAPI](index.md)

**operationId:** `pricing_create`

**Создать стратегию**

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `competitors` | array | ✓ | Список конкурентов. |
| `strategy_name` | string | ✓ | Название стратегии. |

[Request example](examples/POST__v1_pricing_strategy_create_req.json)

## Responses

### `200` Стратегия создана


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | v1CreatePricingStrategyResponseResult |  | Результат работы метода. |

[Response 200](../_shared/examples/POST__v1_pricing_strategy_create_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
