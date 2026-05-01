# `POST` /v1/warehouse/fbs/update

**Tag:** [FBSWarehouseSetup](index.md)

**operationId:** `UpdateWarehouseFBS`

**Обновить склад**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `address_coordinates` | v1UpdateWarehouseFBSRequestAddressCoordinates | ✓ | Координаты склада. |
| `name` | string |  | Название склада. |
| `options` | v1UpdateWarehouseFBSRequestOptions |  | Параметры склада. |
| `phone` | string |  | Номер телефона склада. |
| `warehouse_id` | integer | ✓ | Идентификатор склада. |
| `working_days` | array |  | Рабочие дни склада: - `MONDAY` — понедельник; - `TUESDAY` — вторник; - `WEDNESDAY` — среда; - `THURSDAY` — четверг; - `FRIDAY` — пятница; - `SATURDAY` — суббота; - `SUNDAY` — воскресенье.  |

[Request example](examples/POST__v1_warehouse_fbs_update_req.json)

## Responses

### `200` Склад обновлён


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
