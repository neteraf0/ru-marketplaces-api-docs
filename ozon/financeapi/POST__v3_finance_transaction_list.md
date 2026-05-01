# `POST` /v3/finance/transaction/list

**Tag:** [FinanceAPI](index.md)

**operationId:** `FinanceAPI_FinanceTransactionListV3`

**Список транзакций**


Используйте метод с последовательной отправкой запросов.
Данные могут не соответствовать информации в личном кабинете.


Возвращает подробную информацию по всем начислениям. Максимальный период, за который можно получить информацию в одном запросе — 1 месяц.

Если в запросе не указывать `posting_number`, то в ответе будут все отправления за указанный период или отправления определённого типа.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `filter` | FinanceTransactionListV3RequestFilter |  | Фильтр. |
| `page` | integer | ✓ | Номер страницы, возвращаемой в запросе. |
| `page_size` | integer | ✓ | Количество элементов на странице. |

[Request example](examples/POST__v3_finance_transaction_list_req.json)

## Responses

### `200` Список транзакций


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | financev3FinanceTransactionListV3ResponseResult |  | Результаты запроса. |

[Response 200](../_shared/examples/POST__v3_finance_transaction_list_200.json)

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
