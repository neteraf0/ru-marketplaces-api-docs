# `POST` /v1/pricing-strategy/list

**Tag:** [PricingStrategyAPI](index.md)

**operationId:** `pricing_list`

**Список стратегий**

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `page` | integer | ✓ | Страница списка, с которой нужно выгрузить стратегии. Минимальное значение — `1`. |
| `limit` | integer | ✓ | Максимальное количество стратегий на странице. Допустимые значения — от `1` до `50`. |

[Request example](examples/POST__v1_pricing_strategy_list_req.json)

## Responses

### `200` Список стратегий


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `strategies` | array |  | Список стратегий. |
| `total` | integer |  | Общее количество стратегий. |

[Response 200](../_shared/examples/POST__v1_pricing_strategy_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
