# `POST` /v1/warehouse/fbs/pickup/courier/create

**Tag:** [FBSWarehouseSetup](index.md)

**operationId:** `WarehouseFbsPickUpCourierCreate`

**Создать вызов курьера на забор отгрузки pick-up**

Метод позволяет запланировать приезд курьера для отгрузки ему отправлений.

[Подробнее об отгрузках курьеру на FBS в Базе знаний](https://seller-edu.ozon.ru/fbs/ozon-logistika/otgruzka-kyruery)

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `warehouse_id` | integer | ✓ | Идентификатор склада.   Чтобы получить список складов для планирования выездов, используйте [/v1/warehouse/fbs/pickup/planning/list](#operation/WarehouseFbsPickUpPlanningList).  |
## Responses

- **200** Вызов создан
### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
