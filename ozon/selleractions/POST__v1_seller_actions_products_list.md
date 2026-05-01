# `POST` /v1/seller-actions/products/list

**Tag:** [SellerActions](index.md)

**operationId:** `SellerActionsProductsList`

**Получить список участвующих в акции товаров**

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
| `cursor` | integer |  | Указатель для выборки следующих данных. |
| `limit` | integer | ✓ | Максимальное количество элементов в ответе. |
## Responses

### `200` Список товаров


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `cursor` | integer |  | Указатель для выборки следующих данных. |
| `has_next` | boolean |  | Признак, что в ответе вернулась только часть значений: - `true` — сделайте повторный запрос с новым параметром `cursor` для получения остальных значений; - `false` — ответ содержит все значения.  |
| `products` | array |  | Информация о товарах. |

[Response 200](../_shared/examples/POST__v1_seller_actions_products_candidates_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
