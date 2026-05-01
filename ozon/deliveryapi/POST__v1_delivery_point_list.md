# `POST` /v1/delivery/point/list

**Tag:** [DeliveryAPI](index.md)

**operationId:** `DeliveryAPI_DeliveryPointList`

**Получить список точек самовывоза**

Возвращает координаты всех точек самовывоза без объединения в кластеры.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
## Responses

### `200` Список точек самовывоза


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `points` | array |  | Точки самовывоза. |

[Response 200](../_shared/examples/POST__v1_delivery_point_list_200.json)
