# `POST` /v1/warehouse/operation/status

**Tag:** [WarehouseAPI](index.md)

**operationId:** `GetWarehouseFBSOperationStatus`

**Получить статус операции**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `operation_id` | string | ✓ | Идентификатор операции. |

[Request example](examples/POST__v1_warehouse_operation_status_req.json)

## Responses

### `200` Статус операции


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `error` | GetWarehouseFBSOperationStatusResponseError |  | Ошибка при обработке операции. |
| `result` | GetWarehouseFBSOperationStatusResponseResult |  | Результат операции. |
| `status` | GetWarehouseFBSOperationStatusResponseStatusEnum |  | Статус операции: - `UNSPECIFIED` — не определено; - `IN_PROGRESS` — в процессе; - `SUCCESS` — выполнена; - `ERROR` — завершилась с ошибкой.  |
| `type` | GetWarehouseFBSOperationStatusResponseTypeEnum |  | Тип операции: - `UNSPECIFIED` — не определено; - `CREATE_FBS_WAREHOUSE` — создание FBS-склада; - `UPDATE_FBS_WAREHOUSE` — обновление FBS-склада; - `SET_FIRST_MILE` — установка первой мили; - `WAREHOUSE_ENABLE_DISABLE` — архивация или разархивация FBS-склада; - `WAREHOUSE_PAUSE_UNPAUSE` — включение или выключение паузы rFBS-склада.  |

[Response 200](../_shared/examples/POST__v1_warehouse_operation_status_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
