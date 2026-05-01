# `POST` /v1/roles

**Tag:** [APIkey](index.md)

**operationId:** `AccessAPI_RolesByToken`

**Получить список ролей и методов по API-ключу**

Метод для получения информации и ролях и методах, привязанных к API-ключу.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Responses

### `200` Список ролей и методов


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `expires_at` | string |  | Дата истечения срока действия ключа. |
| `roles` | array |  | Информация о доступных ролях и методах. |

[Response 200](../_shared/examples/POST__v1_roles_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
