# `POST` /v1/warehouse/unarchive

**Tag:** [WarehouseAPI](index.md)

**operationId:** `UnarchiveWarehouseFBS`

**Перенести склад из архива**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `return_point_id` | integer |  | Идентификатор пункта возврата. Получите значение параметра методом [/v1/warehouse/fbs/update/return-point/list](#operation/WarehouseFBSUpdateReturnPointList). |
| `warehouse_id` | integer | ✓ | Идентификатор склада. |

[Request example](examples/POST__v1_warehouse_unarchive_req.json)

## Responses

### `200` Склад перенесён из архива


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `operation_id` | string |  | Идентификатор операции. Получите статус операции методом [/v1/warehouse/operation/status](#operation/GetWarehouseFBSOperationStatus). |

[Response 200](../_shared/examples/POST__v1_warehouse_archive_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
