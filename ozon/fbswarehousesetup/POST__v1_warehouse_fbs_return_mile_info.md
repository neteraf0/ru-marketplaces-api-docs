# `POST` /v1/warehouse/fbs/return-mile/info

**Tag:** [FBSWarehouseSetup](index.md)

**operationId:** `WarehouseFBSReturnMileInfo`

**Получить информацию о возвратной миле**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `warehouse_ids` | array | ✓ | Идентификаторы складов. |
## Responses

### `200` Успешно


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `return_mile_settings` | array |  | Информация о возвратной миле на складе. |

[Response 200](../_shared/examples/POST__v1_warehouse_fbs_return_mile_info_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
