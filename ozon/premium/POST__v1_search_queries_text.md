# `POST` /v1/search-queries/text

**Tag:** [Premium](index.md)

**operationId:** `SearchQueriesAPI_SearchQueriesText`

**Получить список поисковых запросов по тексту**

Доступно для продавцов с подпиской [Premium Pro](https://seller-edu.ozon.ru/seller-rating/about-rating/podpiska-premium-pro).

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `limit` | string | ✓ | Количество значений на странице. |
| `offset` | string | ✓ | Количество элементов, которое будет пропущено в ответе. |
| `sort_by` | SearchQueriesTextRequestSortBy |  | Параметр, по которому сортируются поисковые запросы:  - `CLIENT_COUNT` — популярность запроса;  - `ADD_TO_CART` — добавления в корзину;  - `CONVERSION_TO_CART` — конверсия в корзине;  - `AVG_PRICE` — средняя цена.  |
| `sort_dir` | SearchQueriesTextRequestSortDir |  | Направление сортировки: - `ASC` — по возрастанию; - `DESC` — по убыванию.  |
| `text` | string | ✓ | Поиск по тексту. |

[Request example](examples/POST__v1_search_queries_text_req.json)

## Responses

### `200` Список поисковых запросов


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `offset` | string |  | Количество поисковых запросов на странице. |
| `search_queries` | array |  | Информация о поисковых запросах. |
| `total` | string |  | Общее количество поисковых запросов. |

[Response 200](../_shared/examples/POST__v1_search_queries_text_200.json)

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
