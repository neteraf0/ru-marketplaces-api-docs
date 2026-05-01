# `POST` /v2/analytics/stock_on_warehouses

**Tag:** [AnalyticsAPI](index.md)

**operationId:** `AnalyticsAPI_AnalyticsGetStockOnWarehousesV2`

**Отчёт по остаткам и товарам**


В будущем метод будет отключён. Переключитесь на /v1/analytics/stocks.


Метод для получения отчёта по остаткам и товарам в перемещении по складам Ozon.


Отличается от отчёта в разделе Аналитика → Отчёты → Отчёт по остаткам и товарам в пути на склады Ozon в личном кабинете.


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `limit` | integer | ✓ | Количество ответов на странице. По умолчанию — 100. |
| `offset` | integer |  | Количество элементов, которое будет пропущено в ответе. Например, если `offset = 10`, то ответ начнётся с 11-го найденного элемента. |
| `warehouse_type` | AnalyticsGetStockOnWarehousesRequestWarehouseType |  | Фильтр по типу склада:   - `EXPRESS_DARK_STORE` — склады Ozon с доставкой Fresh.   - `NOT_EXPRESS_DARK_STORE` — склады Ozon без доставки Fresh.   - `ALL` — все склады Ozon.  |

[Request example](examples/POST__v2_analytics_stock_on_warehouses_req.json)

## Responses

### `200` Отчёт по остаткам и товарам


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | analyticsStockOnWarehouseResponseResult |  | Результат запроса. |

[Response 200](../_shared/examples/POST__v2_analytics_stock_on_warehouses_200.json)

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
