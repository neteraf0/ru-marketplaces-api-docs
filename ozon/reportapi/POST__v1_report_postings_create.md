# `POST` /v1/report/postings/create

**Tag:** [ReportAPI](index.md)

**operationId:** `ReportAPI_CreateCompanyPostingsReport`

**Отчёт об отправлениях**

Отчёт об отправлениях с информацией по заказам:
  - статусы заказов,
  - дата начала обработки,
  - номера заказов,
  - номера отправлений,
  - стоимость отправлений,
  - содержимое отправлений.
Соответствует разделу **FBO → Заказы со склада Ozon** и **FBS → Заказы с моих складов → CSV** в личном кабинете.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `filter` | reportCreateCompanyPostingsReportRequestFilter | ✓ | Фильтр. |
| `language` | reportLanguage |  | Язык ответа:   - `RU` — русский,   - `EN` — английский.  |
| `with` | CreateCompanyPostingsReportRequestWith |  | Дополнительные поля, которые нужно добавить в ответ. |

[Request example](examples/POST__v1_report_postings_create_req.json)

## Responses

### `200` Отчёт об отправлениях


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | CreateReportResponseCode |  | Результаты запроса. |

[Response 200](../_shared/examples/POST__v1_report_postings_create_200.json)

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
