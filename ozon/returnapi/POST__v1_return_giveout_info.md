# `POST` /v1/return/giveout/info

**Tag:** [ReturnAPI](index.md)

**operationId:** `ReturnAPI_GiveoutInfo`

**Информация о возвратной отгрузке**

Метод для получения информации о возвратной отгрузке.
В параметр `giveout_id` передаётся значение, полученное в методе [/v1/return/giveout/list](#operation/ReturnAPI_GiveoutList).

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `giveout_id` | integer | ✓ | Идентификатор отгрузки. |
## Responses

### `200` Информация о возвратной отгрузке


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `articles` | array |  | Артикулы товаров. |
| `giveout_id` | integer |  | Идентификатор отгрузки. |
| `giveout_status` | v1GiveoutStatus |  | Статусы возвратной отгрузки:  - `GIVEOUT_STATUS_UNSPECIFIED` — не определён, напишите в поддержку.  - `GIVEOUT_STATUS_CREATED` — создана.  - `GIVEOUT_STATUS_APPROVED` — одобрена.  - `GIVEOUT_STATUS_COMPLETED` — завершена.  - `GIVEOUT_STATUS_CANCELLED` — отменена.  |
| `warehouse_address` | string |  | Адрес склада. |
| `warehouse_name` | string |  | Название склада. |

[Response 200](../_shared/examples/POST__v1_return_giveout_info_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
