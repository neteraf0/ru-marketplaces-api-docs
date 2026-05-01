# `POST` /v1/pricing-strategy/info

**Tag:** [PricingStrategyAPI](index.md)

**operationId:** `pricing_info`

**Информация о стратегии**

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

[Request example](examples/POST__v1_pricing_strategy_info_req.json)

## Responses

### `200` Информация о стратегии


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | v1GetStrategyResponseResult |  | Результат работы метода. |

[Response 200](../_shared/examples/POST__v1_pricing_strategy_info_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
