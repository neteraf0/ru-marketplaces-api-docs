# `POST` /v2/polygon/bind

**Tag:** [PolygonAPI](index.md)

**operationId:** `PolygonBind`

**Связать метод доставки с полигоном**

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
| `polygon_id` | integer | ✓ | Идентификатор полигона. |
| `time` | integer (enum: 15, 30, 45, 60, 90, 120, 150) | ✓ | Время доставки в минутах. |
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
