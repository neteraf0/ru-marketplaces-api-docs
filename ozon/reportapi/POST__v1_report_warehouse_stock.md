# `POST` /v1/report/warehouse/stock

**Tag:** [ReportAPI](index.md)

**operationId:** `ReportAPI_CreateStockByWarehouseReport`

**Отчёт об остатках на FBS-складе**

Отчёт с информацией о количестве доступных и зарезервированных единиц товара на складе.
Соответствует разделу **FBS → Управление логистикой → Управление остатками → Скачать в XLS** в личном кабинете.

В результате запроса будет не сам отчёт, а его уникальный идентификатор.
Чтобы получить отчёт, отправьте идентификатор в запросе метода [/v1/report/info](#operation/ReportAPI_ReportInfo).

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `language` | reportLanguage |  | Язык ответа:   - `RU` — русский,   - `EN` — английский.  |
| `warehouseId` | string | ✓ | Идентификаторы складов. Ограничение значений в запросе. Максимум — 50.  |
## Responses

### `200` Результат запроса


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | CreateReportResponseCode |  | Результаты запроса. |

[Response 200](../_shared/examples/POST__v1_report_discounted_create_200.json)

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
