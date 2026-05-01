# `POST` /v1/warehouse/fbs/create/drop-off/list

**Tag:** [FBSWarehouseSetup](index.md)

**operationId:** `WarehouseAPI_ListDropOffPointsForCreateFBSWarehouse`

**Получить список drop-off пунктов для создания склада**

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `coordinates` | v1ListDropOffPointsForCreateFBSWarehouseRequestCoordinates |  | Координаты. |
| `country_code` | string | ✓ | Код страны в формате ISO 2.  |
| `is_kgt` | boolean | ✓ | `true`, если товар крупногабаритный.  |
| `search` | ListDropOffPointsForCreateFBSWarehouseRequestSearch |  | Параметры поиска. |

[Request example](examples/POST__v1_warehouse_fbs_create_drop_off_list_req.json)

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
