# `POST` /v1/finance/document-b2b-sales

**Tag:** [FinanceAPI](index.md)

**operationId:** `ReportAPI_CreateDocumentB2BSalesReport`

**Реестр продаж юридическим лицам**

Используйте метод, чтобы получить отчёт по продажам юридическим лицам. Соответствует разделу **Финансы → Документы → Реестр продаж юр. лицам** в личном кабинете.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `date` | string | ✓ | Отчётный период в формате `YYYY-MM`. |
| `language` | commonLanguage |  | Язык ответа:   - `RU` — русский,   - `EN` — английский.  |
## Responses

### `200` Результат запроса


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | CreateReportResponseCode |  | Результаты запроса. |

[Response 200](../_shared/examples/POST__v1_report_marked_products_sales_create_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
