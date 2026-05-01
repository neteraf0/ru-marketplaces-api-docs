# `POST` /v1/product/certificate/delete

**Tag:** [CertificationAPI](index.md)

**operationId:** `CertificateDelete`

**Удалить сертификат**

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `certificate_id` | integer | ✓ | Идентификатор сертификата. |
## Responses

### `200` Результат удаления сертификата


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | v1ProductCertificateDeleteResponseResult |  | Результат удаления сертификата. |

[Response 200](../_shared/examples/POST__v1_product_certificate_delete_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
