# `POST` /v1/product/certificate/unbind

**Tag:** [CertificationAPI](index.md)

**operationId:** `CertificateUnbind`

**Отвязать товар от сертификата**

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
| `product_id` | array | ✓ | Список идентификаторов товара, которые нужно отвязать от сертификата. |

[Request example](examples/POST__v1_product_certificate_unbind_req.json)

## Responses

### `200` Товар отвязан от сертификата


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | array |  | Результат работы метода. |

[Response 200](../_shared/examples/POST__v1_product_certificate_unbind_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
