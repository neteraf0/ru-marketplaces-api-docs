# `GET` /v2/product/certificate/accordance-types/list

**Tag:** [CertificationAPI](index.md)

**operationId:** `CertificateAccordanceTypes`

**Список типов соответствия требованиям (версия 2)**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Responses

### `200` Список типов соответствия требованиям


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | v2ProductCertificateAccordanceTypesResponseResult |  | Список типов соответствия требованиям. |

[Response 200](../_shared/examples/GET__v2_product_certificate_accordance_types_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
