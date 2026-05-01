# `POST` /v1/finance/compensation

**Tag:** [FinanceAPI](index.md)

**operationId:** `ReportAPI_GetCompensationReport`

**Отчёт о компенсациях**

Метод для получения отчёта о компенсациях. Соответствует отчёту из раздела **Финансы → Документы → Компенсации и прочие начисления** в личном кабинете.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `date` | string | ✓ | Отчётный период в формате `YYYY-MM`. |
| `language` | compensationReportLanguage |  | Язык отчёта:   - `RU` — русский,   - `EN` — английский.  |

[Request example](examples/POST__v1_finance_compensation_req.json)

## Responses

### `200` Отчёт о компенсациях


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | CreateReportResponseCodeNoDeadline |  | Результат запроса. |

[Response 200](../_shared/examples/POST__v1_report_marked_products_sales_create_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
