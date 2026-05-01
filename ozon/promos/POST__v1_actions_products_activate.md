# `POST` /v1/actions/products/activate

**Tag:** [Promos](index.md)

**operationId:** `PromosProductsActivate`

**Добавить товар в акцию**

Метод для добавления товаров в доступную акцию.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `action_id` | number | ✓ | Идентификатор акции. Можно получить с помощью метода [/v1/actions](#operation/Promos). |
| `products` | array | ✓ | Список товаров. |

[Request example](examples/POST__v1_actions_products_activate_req.json)

## Responses

### `200` Товар добавлен в акцию


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | seller_apiProductV1ResponseResult |  | Результаты запроса. |

[Response 200](../_shared/examples/POST__v1_actions_products_activate_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
