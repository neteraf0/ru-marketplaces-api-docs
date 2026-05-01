# `POST` /v1/pricing-strategy/update

**Tag:** [PricingStrategyAPI](index.md)

**operationId:** `pricing_update`

**Обновить стратегию**

Можно обновить все стратегии кроме системной.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `competitors` | array | ✓ | Список конкурентов. |
| `strategy_id` | string | ✓ | Идентификатор стратегии. |
| `strategy_name` | string | ✓ | Название стратегии. |

[Request example](examples/POST__v1_pricing_strategy_update_req.json)

## Responses

### `200` Стратегия обновлена


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 200](../_shared/examples/POST__v1_pricing_strategy_update_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
