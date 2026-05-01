# `POST` /v1/receipts/upload

**Tag:** [Receipt](index.md)

**operationId:** `UploadReceipt`

**Загрузить чек**


 Метод доступен продавцам, которые заключили договор с ТОО «ОЗОН Маркетплейс Казахстан».


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `multipart/form-data`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `content` | string | ✓ | Содержание файла в бинарном виде. |
| `operation_type` | string | ✓ | Тип операции. Получите значение параметра методом [/v1/receipts/seller/list](#operation/ReceiptsSellerList). |
| `parent_receipt_id` | string |  | Идентификатор родительского чека. Передайте параметр с идентификатором чека, который нужно изменить. |
| `posting_numbers` | array | ✓ | Номера отправлений. |
| `receipt_number` | string | ✓ | Номер чека. |
| `type` | v1UploadReceiptRequestTypeEnum | ✓ | Тип чека:   - `INCOMING` — чек реализации;   - `REFUND` — чек возврата.  |
## Responses

### `200` Чек загружен


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `receipt_id` | string |  | Идентификатор чека. |

[Response 200](../_shared/examples/POST__v1_receipts_upload_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
