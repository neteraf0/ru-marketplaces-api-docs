# `POST` /v1/warehouse/fbs/first-mile/update

**Tag:** [FBSWarehouseSetup](index.md)

**operationId:** `UpdateWarehouseFBSFirstMile`

**Обновить первую милю**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `cut_in_time` | integer | ✓ | Время на приём заказов в минутах. Например, если вы передадите `3000`, приём заказов будет завершён через 50 часов с момента передачи.  |
| `drop_off_point_id` | integer |  | Идентификатор drop-off пункта. Если `first_mile_type = DROP_OFF`, параметр обязательный. |
| `first_mile_type` | v1UpdateWarehouseFBSFirstMileRequestFirstMileTypeEnum | ✓ | Тип первой мили: - `PICK_UP` — отгрузка заказов курьеру; - `DROP_OFF` — отгрузка заказов в пункт приёма.  |
| `timeslot_id` | integer | ✓ | Идентификатор таймслота. |
| `return_point_id` | integer |  | Идентификатор пункта возврата. Получите значение параметра методом [/v1/warehouse/fbs/update/return-point/list](#operation/WarehouseFBSUpdateReturnPointList). |
| `warehouse_id` | integer | ✓ | Идентификатор склада. |

[Request example](examples/POST__v1_warehouse_fbs_first_mile_update_req.json)

## Responses

### `200` Первая миля обновлена


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
