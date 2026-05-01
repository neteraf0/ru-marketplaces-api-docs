# `POST` /v1/invoice/file/upload

**Tag:** [SupplierAPI](index.md)

**operationId:** `invoice_upload`

**Загрузка счёта-фактуры**

Доступные форматы: JPEG и PDF. Максимальный размер файла: 10 МБ.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `base64_content` | string | ✓ | Счёт-фактура в кодировке Base64. |
| `posting_number` | string | ✓ | Номер отправления. |
## Responses

### `200` Ссылка на счёт-фактуру


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `url` | string |  | Ссылка на счёт-фактуру. |

[Response 200](../_shared/examples/POST__v1_invoice_file_upload_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
