# `POST` /v1/warehouse/fbs/create

**Tag:** [FBSWarehouseSetup](index.md)

**operationId:** `WarehouseAPI_CreateWarehouseFBS`

**Создать склад**

Если создаёте склад с доставкой в drop-off пункт, используйте метод [/v1/warehouse/fbs/create/drop-off/list](#operation/WarehouseAPI_ListDropOffPointsForCreateFBSWarehouse), чтобы получить точки.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `address_coordinates` | CreateWarehouseFBSRequestAddressCoordinates | ✓ | Координаты адреса склада. |
| `cut_in_time` | integer | ✓ | Время на приём заказов в минутах. Например, если вы передадите `3000`, приём заказов будет завершён через 50 часов с момента передачи.  |
| `drop_off_point_id` | integer |  | Идентификатор drop-off пункта. |
| `first_mile_type` | CreateWarehouseFBSRequestFirstMileTypeEnum | ✓ | Тип первой мили: - `PICK_UP` — отгрузка заказов курьеру; - `DROP_OFF` — отгрузка заказов в пункт приёма.  |
| `is_kgt` | boolean | ✓ | `true`, если товар крупногабаритный.  |
| `name` | string | ✓ | Название склада. |
| `options` | CreateWarehouseFBSRequestOptions |  | Параметры склада. |
| `phone` | string | ✓ | Номер телефона склада. Укажите в формате +7(XXX)XXX-XX-XX. |
| `timeslot_id` | integer | ✓ | Идентификатор таймслота. |
| `return_point_id` | integer |  | Идентификатор пункта возврата. Получите значение параметра методом [/v1/warehouse/fbs/create/return-point/list](#operation/WarehouseFBSCreateReturnPointList). |
| `working_days` | array |  | Рабочие дни склада: - `MONDAY` — понедельник, - `TUESDAY` — вторник, - `WEDNESDAY` — среда, - `THURSDAY` — четверг, - `FRIDAY` — пятница, - `SATURDAY` — суббота, - `SUNDAY` — воскресенье.  |

[Request example](examples/POST__v1_warehouse_fbs_create_req.json)

## Responses

### `200` Склад создан


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `operation_id` | string |  | Идентификатор операции на создание FBS-склада. Чтобы получить статус операции, используйте метод [/v1/warehouse/operation/status](#operation/GetWarehouseFBSOperationStatus). |

[Response 200](../_shared/examples/POST__v1_warehouse_fbs_create_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
