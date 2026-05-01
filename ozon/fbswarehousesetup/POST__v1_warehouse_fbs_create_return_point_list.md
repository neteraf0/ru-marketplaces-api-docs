# `POST` /v1/warehouse/fbs/create/return-point/list

**Tag:** [FBSWarehouseSetup](index.md)

**operationId:** `WarehouseFBSCreateReturnPointList`

**Получить список пунктов возврата для создания склада**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `coordinates` | v1WarehouseFBSCreateReturnPointListRequestCoordinates | ✓ | Координаты пункта возврата. |
| `country_code` | string | ✓ | Код страны в формате ISO 2. |
| `last_id` | integer |  | Идентификатор последнего значения на странице. |
| `limit` | integer | ✓ | Количество значений в ответе. |
| `search` | v1WarehouseFBSCreateReturnPointListRequestSearch |  | Параметры поиска. |
| `selected_dropoff_point_id` | integer |  | Идентификатор выбранной точки отгрузки на складе. |
## Responses

### `200` Успешно


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `has_next` | boolean |  | Признак, что в ответе вернули не все пункты возврата. |
| `is_selected_point_available` | boolean |  | Признак доступности пункта возврата. |
| `last_id` | integer |  | Идентификатор последнего значения на странице. |
| `points` | array |  | Список пунктов возврата. |

[Response 200](../_shared/examples/POST__v1_warehouse_fbs_create_return_point_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
