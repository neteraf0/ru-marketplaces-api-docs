# `POST` /v1/actions/candidates

**Tag:** [Promos](index.md)

**operationId:** `PromosCandidates`

**Список доступных для акции товаров**

Метод для получения списка товаров, которые могут участвовать в акции, по её идентификатору.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `action_id` | number | ✓ | Идентификатор акции. Можно получить с помощью метода [/v1/actions](#operation/Promos). |
| `limit` | number |  | Количество ответов на странице. По умолчанию — 100. |
| `last_id` | number |  | Идентификатор последнего значения на странице. При первом запросе оставьте это поле пустым. |

[Request example](examples/POST__v1_actions_candidates_req.json)

## Responses

### `200` Список товаров


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | seller_apiGetSellerProductV1ResponseResult |  | Результаты запроса. |

[Response 200](../_shared/examples/POST__v1_actions_candidates_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
