# `POST` /v1/polygon/time/set

**Tag:** [PolygonAPI](index.md)

**operationId:** `PolygonTimeSet`

**Установить новое время доставки в полигоне**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `current_time` | integer (enum: 15, 30, 45, 60, 90, 120, 150) | ✓ | Текущее время доставки в минутах. |
| `delivery_method_id` | integer | ✓ | Идентификатор метода доставки. |
| `new_time` | integer (enum: 15, 30, 45, 60, 90, 120, 150) | ✓ | Новое время доставки в минутах. |
| `polygon_id` | integer | ✓ | Идентификатор полигона. |
| `warehouse_id` | integer | ✓ | Идентификатор склада. |
## Responses

- **200** Успешно
### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
