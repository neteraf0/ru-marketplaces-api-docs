# `POST` /v1/product/certificate/products/list

**Tag:** [CertificationAPI](index.md)

**operationId:** `CertificateProductsList`

**Список товаров, привязанных к сертификату**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `certificate_id` | integer | ✓ | Идентификатор сертификата. |
| `product_status_code` | string |  | Статус проверки товара при привязке к сертификату. |
| `page` | integer | ✓ | Номер страницы, с которой выводить список. Минимальное значение — 1. |
| `page_size` | integer | ✓ | Количество объектов на странице. Значение — от 1 до 1000. |

[Request example](examples/POST__v1_product_certificate_products_list_req.json)

## Responses

### `200` Список товаров


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | v1ProductCertificateProductsListResponseResult |  | Товары, привязанные к сертификату. |

[Response 200](../_shared/examples/POST__v1_product_certificate_products_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
