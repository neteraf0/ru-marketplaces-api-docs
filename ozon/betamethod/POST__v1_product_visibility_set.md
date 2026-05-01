# `POST` /v1/product/visibility/set

**Tag:** [BetaMethod](index.md)

**operationId:** `ProductVisibilitySet`

**Настроить видимость товара на витрине Ozon и Ozon Селект**

Вы можете оставить обратную связь о работе метода в [комментариях](https://dev.ozon.ru/community/1951-Novyi-metod-upravleniia-vidimostiu-na-vitrinakh/) в сообществе разработчиков Ozon for dev.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `item_placement` | array | ✓ | Информация о видимости товара. |
## Responses

### `200` Видимость товара настроена


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `items` | array |  | Информация о видимости товаров. |
| `items_errors` | array |  | Товары с ошибками. |

[Response 200](../_shared/examples/POST__v1_product_visibility_set_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
