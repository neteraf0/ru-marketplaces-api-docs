# `POST` /v1/pricing-strategy/status

**Tag:** [PricingStrategyAPI](index.md)

**operationId:** `pricing_status`

**Изменить статус стратегии**

Можно изменить статус любой стратегии кроме системной.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `enabled` | boolean |  | Статус стратегии: - `true` — включена, - `false` — отключена.  |
| `strategy_id` | string | ✓ | Идентификатор стратегии. |

[Request example](examples/POST__v1_pricing_strategy_status_req.json)

## Responses

### `200` Статус стратегии изменён


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
