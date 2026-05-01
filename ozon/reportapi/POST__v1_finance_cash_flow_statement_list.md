# `POST` /v1/finance/cash-flow-statement/list

**Tag:** [ReportAPI](index.md)

**operationId:** `FinanceAPI_FinanceCashFlowStatementList`

**Финансовый отчёт**

Метод для получения финансового отчёта за периоды с 01 по 15 и с 16 по 31.
Запросить отчёт за отдельные дни не получится.
Соответствует разделу **Финансы → Выплаты** в личном кабинете.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `date` | financev3Period | ✓ | Период формирования отчёта. |
| `page` | integer | ✓ | Номер страницы, возвращаемой в запросе. |
| `with_details` | boolean |  | `true`, если нужно добавить дополнительные параметры в ответ. |
| `page_size` | integer | ✓ | Количество элементов на странице. |

[Request example](examples/POST__v1_finance_cash_flow_statement_list_req.json)

## Responses

### `200` Финансовый отчёт


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | v3FinanceCashFlowStatementListResponseResult |  | Результат работы метода. |

[Response 200](../_shared/examples/POST__v1_finance_cash_flow_statement_list_200.json)

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
