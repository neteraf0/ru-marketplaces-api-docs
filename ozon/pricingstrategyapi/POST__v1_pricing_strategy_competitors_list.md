# `POST` /v1/pricing-strategy/competitors/list

**Tag:** [PricingStrategyAPI](index.md)

**operationId:** `pricing_competitors`

**Список конкурентов**

Метод для получения списка конкурентов — продавцов с похожими товарами в других интернет-магазинах и маркетплейсах.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `page` | integer | ✓ | Страница списка, с которой нужно выгрузить конкурентов. Минимальное значение — `1`. |
| `limit` | integer | ✓ | Максимальное количество конкурентов на странице. Допустимы значения от `1` до `50`. |

[Request example](examples/POST__v1_pricing_strategy_competitors_list_req.json)

## Responses

### `200` Список конкурентов


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `competitor` | array |  | Список конкурентов. |
| `total` | integer |  | Общее количество конкурентов. |

[Response 200](../_shared/examples/POST__v1_pricing_strategy_competitors_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
