# `POST` /v1/finance/mutual-settlement

**Tag:** [FinanceAPI](index.md)

**operationId:** `ReportAPI_CreateMutualSettlementReport`

**Отчёт о взаиморасчётах**

Используйте метод, чтобы получить отчёт о взаиморасчетах. Соответствует разделу **Финансы → Документы → Аналитические отчеты → Отчет о взаиморасчетах** в личном кабинете.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

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
