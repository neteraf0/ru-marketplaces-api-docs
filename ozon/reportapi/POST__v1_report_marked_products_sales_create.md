# `POST` /v1/report/marked-products-sales/create

**Tag:** [ReportAPI](index.md)

**operationId:** `CreateCompanyMarkedProductsSalesReport`

**Сгенерировать отчёт по продажам товаров с маркировкой**

В одном отчёте вы можете получить не больше 50 000 кодов маркировки. Чтобы получить остальные данные, уменьшите период формирования отчёта.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `date` | ReportMarkedProductsSalesCreateRequestDate |  | Период формирования отчёта. |
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
