# `POST` /v1/delivery/map

**Tag:** [DeliveryAPI](index.md)

**operationId:** `DeliveryMap`

**Отрисовать точки на карте**

Возвращает объединённые кластеры точек самовывоза на области из параметра `viewport`.

Используйте значения из параметра `clusters.viewport`, чтобы получить список точек или мелких кластеров внутри большого кластера.

Используйте метод [/v1/delivery/point/info](#operation/DeliveryPointInfo), чтобы получить информацию о конкретной точке самовывоза.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `viewport` | v1DeliveryMapRequestViewport |  | Область карты для получения кластеров и точек самовывоза. |
| `zoom` | integer |  | Масштаб карты. |
## Responses

### `200` Успешно


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `clusters` | array |  | Кластеры. |

[Response 200](../_shared/examples/POST__v1_delivery_map_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
