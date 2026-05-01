# `POST` /v1/posting/fbs/product/traceable/attribute

**Tag:** [DeliveryFBS](index.md)

**operationId:** `PostingFbsProductTraceableAttribute`

**Получить список незаполненных атрибутов для прослеживаемых товаров**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `posting_number` | string | ✓ | Номер отправления. |
## Responses

### `200` Список незаполненных атрибутов


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `products` | array |  | Список товаров в отправлении. |

[Response 200](../_shared/examples/POST__v1_posting_fbs_product_traceable_attribute_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
