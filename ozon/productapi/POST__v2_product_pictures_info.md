# `POST` /v2/product/pictures/info

**Tag:** [ProductAPI](index.md)

**operationId:** `ProductAPI_ProductInfoPicturesV2`

**Получить изображения товаров**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `product_id` |  | ✓ | Список идентификаторов товаров в системе Ozon — `product_id`. |

[Request example](examples/POST__v2_product_pictures_info_req.json)

## Responses

### `200` Изображения товаров


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `items` | array |  | Изображения товаров. |

[Response 200](../_shared/examples/POST__v2_product_pictures_info_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
