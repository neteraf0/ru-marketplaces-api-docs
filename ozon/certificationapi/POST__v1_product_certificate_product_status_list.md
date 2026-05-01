# `POST` /v1/product/certificate/product_status/list

**Tag:** [CertificationAPI](index.md)

**operationId:** `ProductStatusList`

**Список возможных статусов товаров**

Метод для получения списка возможных статусов товаров при их привязке к сертификату.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Responses

### `200` Список статусов товаров


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | array |  | Список статусов товаров. |

[Response 200](../_shared/examples/POST__v1_product_certificate_product_status_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
