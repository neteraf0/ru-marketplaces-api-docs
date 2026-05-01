# `POST` /v1/product/certificate/info

**Tag:** [CertificationAPI](index.md)

**operationId:** `CertificateInfo`

**Информация о сертификате**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `certificate_number` | string | ✓ | Идентификатор сертификата. |

[Request example](examples/POST__v1_product_certificate_info_req.json)

## Responses

### `200` Информация о сертификате


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | v1Certificate |  | Информация о сертификате. |

[Response 200](../_shared/examples/POST__v1_product_certificate_info_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
