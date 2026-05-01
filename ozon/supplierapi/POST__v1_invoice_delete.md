# `POST` /v1/invoice/delete

**Tag:** [SupplierAPI](index.md)

**operationId:** `invoice_delete`

**Удалить ссылку на счёт-фактуру**

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `posting_number` | string | ✓ | Номер отправления. |
## Responses

### `200` Ссылка удалена


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | boolean |  | Результат работы метода. |

[Response 200](../_shared/examples/POST__v1_product_update_discount_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
