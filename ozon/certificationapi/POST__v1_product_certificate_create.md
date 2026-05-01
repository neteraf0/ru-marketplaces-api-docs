# `POST` /v1/product/certificate/create

**Tag:** [CertificationAPI](index.md)

**operationId:** `ProductAPI_ProductCertificateCreate`

**Добавить сертификаты для товаров**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `multipart/form-data`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `files` | array | ✓ | Массив сертификатов для товара. Допустимые расширения jpg, jpeg, png, pdf. |
| `name` | string | ✓ | Название сертификата. Максимум 100 символов. |
| `number` | string | ✓ | Номер сертификата. Максимум 100 символов. |
| `type_code` | string (enum: certificate_of_conformity, declaration, certificate_of_registration, registration_certificate, refused_letter, veterinary_cover_document, safety_data_sheet) | ✓ | Тип сертификата. Чтобы получить доступные типы, используйте метод [GET /v1/product/certificate/types](#operation/ProductAPI_ProductCertificateTypes). |
| `accordance_type_code` | string (enum: technical_regulations_rf, technical_regulations_cu, gost) |  | Тип соответствия требованиям. Чтобы получить доступные типы, используйте метод [GET /v1/product/certificate/accordance-types](#operation/ProductAPI_ProductCertificateAccordanceTypes). Параметр обязательный, если `type_code = declaration`, `certificate_of_conformity` или `safety_data_sheet`. |
| `issue_date` | string | ✓ | Дата начала действия сертификата. |
| `expire_date` | string |  | Дата окончания действия сертификата. Может быть пустым для бессрочных сертификатов.  Формат: `2021-04-30T11:31:26Z`.  |
## Responses

### `200` Идентификатор загруженного сертификата

`integer` — example: `{'id': 50058}`

[Response 200](../_shared/examples/POST__v1_product_certificate_create_200.json)

### `400` Неверный параметр


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 400](../_shared/examples/POST__v1_roles_default.json)

### `403` Доступ запрещён


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 403](../_shared/examples/POST__v1_roles_default.json)

### `404` Ответ не найден


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 404](../_shared/examples/POST__v1_roles_default.json)

### `409` Конфликт запроса


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 409](../_shared/examples/POST__v1_roles_default.json)

### `500` Внутренняя ошибка сервера


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 500](../_shared/examples/POST__v1_roles_default.json)
