# `POST` /v1/return/giveout/is-enabled

**Tag:** [ReturnAPI](index.md)

**operationId:** `ReturnAPI_GiveoutIsEnabled`

**Проверить возможность получения возвратных отгрузок по штрихкоду**

Если у вас есть доступ, в параметре `enabled` будет указано значение `true`.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
## Responses

### `200` Результат проверки


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `enabled` | boolean |  | `true`, если вы можете получить возвратную отгрузку по штрихкоду.  |

[Response 200](../_shared/examples/POST__v1_return_giveout_is_enabled_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
