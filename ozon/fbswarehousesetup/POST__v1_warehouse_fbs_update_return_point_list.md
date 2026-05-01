# `POST` /v1/warehouse/fbs/update/return-point/list

**Tag:** [FBSWarehouseSetup](index.md)

**operationId:** `WarehouseFBSUpdateReturnPointList`

**Получить список пунктов возврата для обновления склада**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `current_dropoff_point_id` | integer |  | Идентификатор выбранной точки отгрузки на складе. |
| `current_return_point_id` | integer |  | Установленный пункт возврата. Получите значение параметра методом [/v1/warehouse/fbs/return-mile/info](#operation/WarehouseFBSReturnMileInfo). |
| `last_id` | integer |  | Идентификатор последнего значения на странице. |
| `limit` | integer | ✓ | Количество значений в ответе. |
| `search` | v1WarehouseFBSUpdateReturnPointListRequestSearch |  | Параметры поиска. |
| `warehouse_id` | integer | ✓ | Идентификатор склада. |
## Responses

### `200` Успешно


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `has_next` | boolean |  | Признак, что в ответе вернули не все пункты возврата. |
| `is_selected_point_available` | boolean |  | Признак доступности пункта возврата для выбора. |
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
