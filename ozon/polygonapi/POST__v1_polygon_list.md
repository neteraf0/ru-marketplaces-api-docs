# `POST` /v1/polygon/list

**Tag:** [PolygonAPI](index.md)

**operationId:** `PolygonList`

**Получить список установленных полигонов на метод доставки**

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
| `warehouse_id` | integer | ✓ | Идентификатор склада. |
## Responses

### `200` Список полигонов


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `polygons` | array |  | Список полигонов. |

[Response 200](../_shared/examples/POST__v1_polygon_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
