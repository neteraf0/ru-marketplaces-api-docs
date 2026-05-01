# `POST` /v1/product/certificate/status/list

**Tag:** [CertificationAPI](index.md)

**operationId:** `CertificateStatusList`

**Возможные статусы сертификатов**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Responses

### `200` Возможные статусы сертификатов


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | array |  | Список возможных статусов сертификатов. |

[Response 200](../_shared/examples/POST__v1_product_certificate_status_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
