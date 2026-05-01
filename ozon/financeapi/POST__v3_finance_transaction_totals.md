# `POST` /v3/finance/transaction/totals

**Tag:** [FinanceAPI](index.md)

**operationId:** `FinanceAPI_FinanceTransactionTotalV3`

**Суммы транзакций**


Данные могут не соответствовать информации в личном кабинете.


Возвращает итоговые суммы по транзакциям за указанный период.

Если вы неправильно заполните номера отправлений, в ответе вернутся нулевые значения.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `date` | FinanceTransactionTotalsV3RequestDate |  | Фильтр по дате. |
| `posting_number` | string |  | Номер отправления. |
| `transaction_type` | string |  | Тип операции:  - `all` — все,  - `orders` — заказы,  - `returns` — возвраты и отмены,  - `services` — сервисные сборы,  - `compensation` — компенсация,  - `transferDelivery` — стоимость доставки,  - `other` — прочее.  |

[Request example](examples/POST__v3_finance_transaction_totals_req.json)

## Responses

### `200` Суммы транзакций


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | financev3FinanceTransactionTotalsV3ResponseResult |  | Результаты запроса. |

[Response 200](../_shared/examples/POST__v3_finance_transaction_totals_200.json)

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
