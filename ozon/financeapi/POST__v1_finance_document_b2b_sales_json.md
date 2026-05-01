# `POST` /v1/finance/document-b2b-sales/json

**Tag:** [FinanceAPI](index.md)

**operationId:** `ReportAPI_CreateDocumentB2BSalesJSONReport`

**Реестр продаж юридическим лицам в JSON-формате**

Используйте метод, чтобы получить отчёт по продажам юридическим лицам в JSON-формате. Соответствует разделу **Финансы → Документы → Реестр продаж юр. лицам** в личном кабинете.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `date` | string | ✓ | Отчётный период в формате `YYYY-MM`. Отчёт доступен до января 2019 включительно. |
## Responses

### `200` Отчёт в JSON-формате


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `date_from` | string |  | Дата начала отчётного периода в формате `YYYY-MM-DD`. |
| `date_to` | string |  | Дата окончания отчётного периода в формате `YYYY-MM-DD`. |
| `invoices` | array |  | Список счетов-фактур. |
| `seller_info` | CreateDocumentB2BSalesJSONReportResponseSellerInfo |  | Информация о продавце. |

[Response 200](../_shared/examples/POST__v1_finance_document_b2b_sales_json_200.json)

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
