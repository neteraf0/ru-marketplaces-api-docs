# `POST` /v1/fbp/act-from/create

**Tag:** [DeliveryFBP](index.md)

**operationId:** `FbpAPI_FbpCreateAct`

**Сгенерировать акт приёмки**

Вы можете оставить обратную связь по этому методу в комментариях к [обсуждению](https://dev.ozon.ru/community/1700-FBP-metody/) в сообществе разработчиков Ozon for dev.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `supply_id` | string | ✓ | Идентификатор поставки. |
## Responses

### `200` Успешно


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `errors` | array |  | Причина ошибки: - `CREATE_ACT_ERROR_REASON_UNSPECIFIED` — не определена; - `INVALID_ORDER_TYPE` — нельзя создать акт для указанного идентификатора поставки.  |
| `file_uuid` | string |  | Идентификатор акта приёмки. |
| `is_success` | boolean |  | `true`, если в запросе нет ошибок.  |

[Response 200](../_shared/examples/POST__v1_fbp_act_from_create_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
