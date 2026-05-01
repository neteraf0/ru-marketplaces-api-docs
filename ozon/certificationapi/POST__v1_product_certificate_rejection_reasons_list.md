# `POST` /v1/product/certificate/rejection_reasons/list

**Tag:** [CertificationAPI](index.md)

**operationId:** `RejectionReasonsList`

**Возможные причины отклонения сертификата**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Responses

### `200` Причины отклонения сертификата


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | array |  | Причины отклонения сертификата. |

[Response 200](../_shared/examples/POST__v1_product_certificate_rejection_reasons_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
