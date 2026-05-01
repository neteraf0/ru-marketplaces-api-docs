# `POST` /v1/warehouse/fbs/create/pick-up/timeslot/list

**Tag:** [FBSWarehouseSetup](index.md)

**operationId:** `WarehouseFbsCreatePickUpTimeslotList`

**Получить список таймслотов для создания склада с отгрузкой pick-up**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `address_coordinates` | v1WarehouseFbsCreatePickUpTimeslotListRequestAddressCoordinates | ✓ | Координаты склада. |
| `is_kgt` | boolean | ✓ | Признак крупногабаритного товара. |

[Request example](examples/POST__v1_warehouse_fbs_create_pick_up_timeslot_list_req.json)

## Responses

### `200` Список таймслотов


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `is_pickup_supported` | boolean |  | Признак поддержки отгрузки pick-up. |
| `timeslots` | array |  | Список таймслотов. |

[Response 200](../_shared/examples/POST__v1_warehouse_fbs_create_pick_up_timeslot_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
