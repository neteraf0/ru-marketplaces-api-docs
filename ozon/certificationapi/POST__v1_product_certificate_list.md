# `POST` /v1/product/certificate/list

**Tag:** [CertificationAPI](index.md)

**operationId:** `CertificateList`

**Список сертификатов**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `offer_id` | string |  | Идентификатор товара в системе продавца — артикул, привязанный к сертификату. Передайте параметр, если нужны сертификаты, к которым привязаны определённые товары. |
| `status` | string |  | Статус сертификата. Передайте параметр, если нужны сертификаты с определённым статусом. |
| `type` | string |  | Тип сертификата. Передайте параметр, если нужны сертификаты с определённым типом. |
| `page` | integer | ✓ | Страница, с которой следует выводить список. Минимальное значение — 1. |
| `page_size` | integer | ✓ | Количество объектов на странице. Значение — от 1 до 1000. |

[Request example](examples/POST__v1_product_certificate_list_req.json)

## Responses

### `200` Список сертификатов


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | v1ProductCertificateListResponseResult |  | Список сертификатов. |

[Response 200](../_shared/examples/POST__v1_product_certificate_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
