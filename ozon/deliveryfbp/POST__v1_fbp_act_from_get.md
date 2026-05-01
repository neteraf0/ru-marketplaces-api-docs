# `POST` /v1/fbp/act-from/get

**Tag:** [DeliveryFBP](index.md)

**operationId:** `FbpAPI_FbpCheckActState`

**Получить статус генерации акта приёмки**

Вы можете оставить обратную связь по этому методу в комментариях к [обсуждению](https://dev.ozon.ru/community/1700-FBP-metody/) в сообществе разработчиков Ozon for dev.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `file_uuid` | string | ✓ | Идентификатор акта приёмки. |
## Responses

### `200` Статус генерации акта приёмки


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `cdn_url` | string |  | Ссылка на акт приёмки. |
| `error` | FbpCheckActStateResponseErrorReason |  | Ошибка генерации: - `ERROR_REASON_UNSPECIFIED` — не определена; - `INVALID_COMPANY` — неверная компания; - `FILE_NOT_FOUND` — файл не найден; - `GENERATE_TIMEOUT_REACHED` — превышено время генерации; - `GENERATION_ERROR` — ошибка во время генерации.  |
| `status` | v1FbpCheckActStateResponseStatus |  | Статус генерации: - `STATUS_UNSPECIFIED` — не определён; - `NOT_EXIST` — не существует; - `PROCESSING` — в процессе; - `EXIST` — завершена; - `ERROR` — ошибка.  |

[Response 200](../_shared/examples/POST__v1_fbp_act_from_get_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
