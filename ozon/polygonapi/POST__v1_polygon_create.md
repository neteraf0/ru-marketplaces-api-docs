# `POST` /v1/polygon/create

**Tag:** [PolygonAPI](index.md)

**operationId:** `PolygonAPI_CreatePolygon`

**Создайте полигон доставки**

Вы можете добавить полигон к методу доставки.

Создайте полигон, получив его координаты на https://geojson.io: отметьте на карте минимум 3 точки и соедините их линиями.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `coordinates` | string | ✓ | Координаты полигона доставки в формате `[[[lat long]]]`.  |

[Request example](examples/POST__v1_polygon_create_req.json)

## Responses

### `200` Полигон создан


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `polygon_id` | integer |  | Идентификатор полигона. |

[Response 200](../_shared/examples/POST__v1_polygon_create_200.json)

### `400` Неверный параметр


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Информация об ошибке. |
| `message` | string |  | Сообщение об ошибке:    - `coordinates not provided` — координаты не переданы;   - `invalid coordinates, must have two points in coordinate` — в какой-то точке передана только широта или долгота, нужно передать две точки;   - `the first and last points in loop must be same` — первая и последняя точка не совпадают (по стандартным правилам geojson точки должны совпадать);   - `non-full loops must have at least 4 unique vertices for polygons` — для полигона передано менее четырех точек.  |

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
