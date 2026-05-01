# `POST` /v1/warehouse/fbs/pickup/courier/cancel

**Tag:** [FBSWarehouseSetup](index.md)

**operationId:** `WarehouseFbsPickUpCourierCancel`

**Отменить вызов курьера на забор отгрузки pick-up**

Метод позволяет отменить запланированный приезд курьера.

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
| `warehouse_id` | integer | ✓ | Идентификатор склада. |
## Responses

- **200** Вызов отменён
### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
