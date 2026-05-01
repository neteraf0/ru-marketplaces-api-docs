# `POST` /v1/fbp/act-to/get

**Tag:** [DeliveryFBP](index.md)

**operationId:** `FbpAPI_FbpCheckConsignmentNoteState`

**Получить статус генерации транспортной накладной**

Вы можете оставить обратную связь по этому методу в комментариях к [обсуждению](https://dev.ozon.ru/community/1700-FBP-metody/) в сообществе разработчиков Ozon for dev.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string | ✓ | Идентификатор транспортной накладной. |
| `supply_id` | string | ✓ | Идентификатор поставки. |
## Responses

### `200` Статус генерации транспортной накладной


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `error_message` | string |  | Описание ошибки. |
| `label_url` | string |  | Ссылка на этикетки для поставки. |
| `state` | FbpCheckConsignmentNoteStateResponseStateType |  | Статус генерации: - `STATE_TYPE_UNSPECIFIED` — не определён; - `IN_PROGRESS` — в процессе; - `FINISHED` — завершилась успешно; - `FAILED` — ошибка.  |

[Response 200](../_shared/examples/POST__v1_fbp_act_to_get_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
