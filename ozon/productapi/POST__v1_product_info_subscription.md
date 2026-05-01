# `POST` /v1/product/info/subscription

**Tag:** [ProductAPI](index.md)

**operationId:** `ProductAPI_GetProductInfoSubscription`

**Количество подписавшихся на товар пользователей**

Метод для получения количества пользователей, которые нажали **Узнать о поступлении** на странице товара.

Вы можете передать несколько товаров в запросе.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `skus` | array | ✓ | Список SKU, идентификаторов товара в системе Ozon. |

[Request example](examples/POST__v1_product_info_subscription_req.json)

## Responses

### `200` Количество подписавшихся пользователей


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | array |  | Результат работы метода. |

[Response 200](../_shared/examples/POST__v1_product_info_subscription_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
