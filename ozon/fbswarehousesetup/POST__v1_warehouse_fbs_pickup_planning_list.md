# `POST` /v1/warehouse/fbs/pickup/planning/list

**Tag:** [FBSWarehouseSetup](index.md)

**operationId:** `WarehouseFbsPickUpPlanningList`

**Получить список складов для планирования отгрузок курьеру**

Чтобы создать отгрузку, используйте метод [/v1/warehouse/fbs/pickup/courier/create](#operation/WarehouseFbsPickUpCourierCreate).

[Подробнее об отгрузках курьеру на FBS в Базе знаний](https://seller-edu.ozon.ru/fbs/ozon-logistika/otgruzka-kyruery)

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Responses

### `200` Список складов


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | v1WarehouseFbsPickUpPlanningListResponseResult |  | Список складов. |

[Response 200](../_shared/examples/POST__v1_warehouse_fbs_pickup_planning_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
