# `POST` /v1/actions/products/deactivate

**Tag:** [Promos](index.md)

**operationId:** `PromosProductsDeactivate`

**Удалить товары из акции**

Метод для удаления товаров из акции.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `action_id` | number | ✓ | Идентификатор акции. Можно получить с помощью метода [/v1/actions](#operation/Promos). |
| `product_ids` | array | ✓ | Список идентификаторов товаров в системе Ozon — `product_id`. |

[Request example](examples/POST__v1_actions_products_deactivate_req.json)

## Responses

### `200` Товары удалены из акции


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | seller_apiProductV1ResponseResultDeactivate |  | Результаты запроса. |

[Response 200](../_shared/examples/POST__v1_actions_products_deactivate_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
