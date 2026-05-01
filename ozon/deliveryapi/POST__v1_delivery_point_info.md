# `POST` /v1/delivery/point/info

**Tag:** [DeliveryAPI](index.md)

**operationId:** `DeliveryPointInfo`

**Получить информацию о точке самовывоза**

Возвращает подробную информацию о точке самовывоза для пользователя.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `map_point_ids` | array |  | Идентификаторы точек на карте. |
## Responses

### `200` Информация о точке самовывоза


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `points` | array |  | Информация о пунктах самовывоза. |

[Response 200](../_shared/examples/POST__v1_delivery_point_info_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
