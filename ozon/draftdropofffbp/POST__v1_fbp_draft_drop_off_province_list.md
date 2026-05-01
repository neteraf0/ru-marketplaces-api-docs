# `POST` /v1/fbp/draft/drop-off/province/list

**Tag:** [DraftDropOffFBP](index.md)

**operationId:** `FbpDraftDropOffProvinceList`

**Получить список провинций**

Вы можете оставить обратную связь о работе метода в [комментариях](https://dev.ozon.ru/community/1700-FBP-metody/) в сообществе разработчиков Ozon for dev.

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

### `200` Список провинций


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `provinces` | array |  | Список провинций. |

[Response 200](../_shared/examples/POST__v1_fbp_draft_drop_off_province_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
