# `POST` /v1/seller-actions/products/add

**Tag:** [SellerActions](index.md)

**operationId:** `SellerActionsProductsAdd`

**Добавить товары в акцию**

Вы можете оставить обратную связь о работе метода в [комментариях](https://dev.ozon.ru/community/1872-Novye-metody-dlia-raboty-s-aktsiiami-sellera) в сообществе разработчиков Ozon for dev.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `action_id` | integer | ✓ | Идентификатор акции. Получите значение параметра методом [/v1/seller-actions/list](#operation/SellerActionsList). |
| `products` | array | ✓ | Информация о товарах. |
## Responses

- **200** Товары добавлены
### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
