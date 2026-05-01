# `POST` /v1/fbp/order/drop-off/timetable

**Tag:** [OrderDropOffFBP](index.md)

**operationId:** `FbpAPI_FbpOrderDropOffTimetable`

**Получить график работы drop-off пункта**

Вы можете оставить обратную связь по этому методу в комментариях к [обсуждению](https://dev.ozon.ru/community/1700-FBP-metody/) в сообществе разработчиков Ozon for dev.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `drop_off_point_id` | integer | ✓ | Идентификатор drop-off пункта. |
| `province_uuid` | string | ✓ | Уникальный идентификатор провинции. |
| `warehouse_id` | integer | ✓ | Идентификатор склада. |
## Responses

### `200` График работы получен


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `calendar` | array |  | Информация о графике работы drop-off пункта. |

[Response 200](../_shared/examples/POST__v1_fbp_draft_drop_off_point_timetable_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
