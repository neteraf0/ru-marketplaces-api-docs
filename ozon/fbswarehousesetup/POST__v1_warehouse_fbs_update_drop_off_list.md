# `POST` /v1/warehouse/fbs/update/drop-off/list

**Tag:** [FBSWarehouseSetup](index.md)

**operationId:** `WarehouseAPI_ListDropOffPointsForUpdateFBSWarehouse`

**Получить список drop-off пунктов для изменения информации склада**

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `search` | ListDropOffPointsForUpdateFBSWarehouseRequestSearch |  | Параметры поиска. |
| `warehouse_id` | integer | ✓ | Фильтр по существующему FBS-складу. |

[Request example](examples/POST__v1_warehouse_fbs_update_drop_off_list_req.json)

## Responses

### `200` Список получен


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `points` | array |  | Список пунктов. |

[Response 200](../_shared/examples/POST__v1_warehouse_fbs_create_drop_off_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
