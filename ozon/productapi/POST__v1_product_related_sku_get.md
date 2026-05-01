# `POST` /v1/product/related-sku/get

**Tag:** [ProductAPI](index.md)

**operationId:** `ProductAPI_ProductGetRelatedSKU`

**Получить связанные SKU**

Метод для получения единого SKU по старым идентификаторам SKU FBS и SKU FBO.
В ответе будут все SKU, связанные с переданными.

Метод может обработать любые SKU, даже скрытые или удалённые.

Передавайте до 200 SKU в одном запросе.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `sku` |  | ✓ | Список SKU. |

[Request example](examples/POST__v1_product_related_sku_get_req.json)

## Responses

### `200` Информация об SKU


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `items` |  |  | Информация о связанных SKU. |
| `errors` |  |  | Ошибки. |

[Response 200](../_shared/examples/POST__v1_product_related_sku_get_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
