# `POST` /v1/polygon/bind

**Tag:** [PolygonAPI](index.md)

**operationId:** `PolygonAPI_BindPolygon`

**Свяжите метод доставки с полигоном доставки**


Метод устаревает и будет отключён в будущем. Переключитесь на /v2/polygon/bind .


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `delivery_method_id` | integer | ✓ | Идентификатор метода доставки. |
| `polygons` | array | ✓ | Список полигонов. |
| `warehouse_location` | PolygonBindRequestwh_location | ✓ | Расположение склада. |

[Request example](examples/POST__v1_polygon_bind_req.json)

## Responses

### `200` Успешно


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 200](../_shared/examples/POST__v1_pricing_strategy_update_200.json)

### `400` Неверный параметр


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  |  |
| `details` | array |  |  |
| `message` | string |  | Сообщение об ошибке:    - **delivery target polygons not provided** — полигоны не переданы;   - **no delivery method id provided** — delivery_method_id не передан;   - **no warehouse points provided** — не передана координата склада;   - **polygon id .... not found** — переданы ID полигонов, которые не найдены в базе данных;   - **not found polygon for warehouse point** — точка склада не принадлежит ни одному переданному полигону.  |

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
