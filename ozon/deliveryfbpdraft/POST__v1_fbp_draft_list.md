# `POST` /v1/fbp/draft/list

**Tag:** [DeliveryFBPDraft](index.md)

**operationId:** `FbpAPI_FbpDraftList`

**Список черновиков поставки**

Вы можете оставить обратную связь о работе метода в [комментариях](https://dev.ozon.ru/community/1700-FBP-metody/) в сообществе разработчиков Ozon for dev.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `count` | integer | ✓ | Количество элементов в ответе. |
| `last_id` | integer |  | Идентификатор последнего значения на странице. Оставьте это поле пустым при выполнении первого запроса.  Чтобы получить следующие значения, укажите `last_id` из ответа предыдущего запроса.  |
## Responses

### `200` Список черновиков поставки


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `has_next` | boolean |  | `true`, если в ответе вернулись не все значения.  |
| `items` | array |  | Черновики. |
| `last_id` | integer |  | Идентификатор последнего значения на странице. |

[Response 200](../_shared/examples/POST__v1_fbp_draft_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
