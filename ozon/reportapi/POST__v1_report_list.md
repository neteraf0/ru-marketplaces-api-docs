# `POST` /v1/report/list

**Tag:** [ReportAPI](index.md)

**operationId:** `ReportAPI_ReportList`

**Список отчётов**

Возвращает список отчётов, которые были сформированы раньше.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `page` | integer | ✓ | Номер страницы. |
| `page_size` | integer | ✓ | Количество значений на странице:   - по умолчанию — 100,   - маĸсимальное значение — 1000.  |
| `report_type` | ReportListRequestReportType |  | Тип отчёта:   - `ALL` — все отчёты;   - `SELLER_PRODUCTS` — отчёт по товарам;   - `SELLER_STOCK` — отчёт об остатках товаров;   - `SELLER_RETURNS` — отчёт о возвратах;   - `SELLER_POSTINGS` — отчёт об отправлениях;   - `SELLER_DISCOUNTED` — отчёт об уценённых товарах;   - `MUTUAL_SETTLEMENT` — отчёт о взаиморасчётах;   - `DOCUMENT_B2B_SALES` — отчёт о продажах юридическим лицам;   - `COMPENSATION_REPORT` — отчёт о компенсациях;   - `DECOMPENSATION_REPORT` — отчёт о декомпенсациях;   - `MARKED_PRODUCTS_SALES` — отчёт по продажам маркированных товаров;   - `SELLER_PLACEMENT_BY_PRODUCTS` — отчёт о стоимости размещения по товарам;   - `SELLER_PLACEMENT_BY_SUPPLIES` — отчёт о стоимости размещения по поставкам.  |

[Request example](examples/POST__v1_report_list_req.json)

## Responses

### `200` Список отчётов


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | ReportListResponseResult |  | Результаты запроса. |

[Response 200](../_shared/examples/POST__v1_report_list_200.json)

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
