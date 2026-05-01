# `POST` /v2/invoice/get

**Tag:** [SupplierAPI](index.md)

**operationId:** `invoice_getV2`

**Получить информацию о счёте-фактуре**

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `posting_number` | string | ✓ | Номер отправления. |
## Responses

### `200` Информация о счёте-фактуре


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | InvoiceGetV2ResponseResult |  | Информация о счёте-фактуре. |

[Response 200](../_shared/examples/POST__v2_invoice_get_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
