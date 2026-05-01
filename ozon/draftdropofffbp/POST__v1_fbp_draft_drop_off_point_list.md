# `POST` /v1/fbp/draft/drop-off/point/list

**Tag:** [DraftDropOffFBP](index.md)

**operationId:** `FbpDraftDropOffPointList`

**Получить список drop-off пунктов в провинции**

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
| `next_page_number` | integer |  | Следующий номер страницы. |
| `page_size` | integer | ✓ | Количество элементов на странице. |
| `province_uuid` | string | ✓ | Уникальный идентификатор провинции. |
| `warehouse_id` | integer | ✓ | Идентификатор склада. |
## Responses

### `200` Список drop-off пунктов


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `drop_off_points` | array |  | Список drop-off пунктов. |

[Response 200](../_shared/examples/POST__v1_fbp_draft_drop_off_point_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
