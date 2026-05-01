# `POST` /v1/fbp/label/get

**Tag:** [DeliveryFBP](index.md)

**operationId:** `FbpAPI_FbpGetLabel`

**Получить статус задания на генерацию этикеток**

Вы можете оставить обратную связь по этому методу в комментариях к [обсуждению](https://dev.ozon.ru/community/1700-FBP-metody/) в сообществе разработчиков Ozon for dev.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string | ✓ | Идентификатор задания на генерацию этикеток. |
| `supply_id` | string | ✓ | Идентификатор поставки. |
## Responses

### `200` Задание создано


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `label_url` | string |  | Ссылка на этикетки для поставки. |
| `state` | FbpGetLabelResponseLabelCreationStateTypeEnum |  | Статус задания на генерацию этикеток: - `UNSPECIFIED` — не определён; - `IN_PROGRESS` — в процессе генерации; - `FINISHED` — генерация завершилась успешно; - `FAILED` — генерация завершилась с ошибкой.  |

[Response 200](../_shared/examples/POST__v1_fbp_label_get_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
