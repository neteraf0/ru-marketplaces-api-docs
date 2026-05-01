# `POST` /v1/analytics/turnover/stocks

**Tag:** [AnalyticsAPI](index.md)

**operationId:** `AnalyticsAPI_StocksTurnover`

**Оборачиваемость товара**

Используйте метод, чтобы узнать оборачиваемость товара и количество дней, на которое хватит текущего остатка.
Метод соответствует разделу [**FBO -> Управление остатками**](https://seller.ozon.ru/app/supply/stocks-management) в личном кабинете.
Вы можете делать не больше 1 запроса в минуту по одному кабинету `Client-Id`.

Если вы запрашиваете список товаров по `sku`, параметры `limit` и `offset` необязательны.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `limit` | integer |  | Количество значений в ответе.  |
| `offset` | integer |  | Количество элементов, которое будет пропущено в ответе.  Например, если `offset = 10`, ответ начнётся с 11-го найденного элемента.  |
| `sku` | array |  | Идентификаторы товаров в системе Ozon — SKU. |
## Responses

### `200` Информация об оборачиваемости


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `items` | array |  | Товары. |

[Response 200](../_shared/examples/POST__v1_analytics_turnover_stocks_200.json)

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
