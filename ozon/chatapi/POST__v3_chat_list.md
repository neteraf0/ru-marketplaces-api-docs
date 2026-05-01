# `POST` /v3/chat/list

**Tag:** [ChatAPI](index.md)

**operationId:** `ChatAPI_ChatListV3`

**Список чатов**

Возвращает информацию о чатах по указанным фильтрам.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `filter` | v3ChatListRequestFilter |  | Фильтр по чатам. |
| `limit` | integer | ✓ | Количество значений в ответе. Значение по умолчанию — 30. Максимальное значение — 100. |
| `cursor` | string |  | Указатель для выборки следующих данных. |

[Request example](examples/POST__v3_chat_list_req.json)

## Responses

### `200` Список чатов


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `chats` |  |  | Данные чатов. |
| `total_unread_count` | integer |  | Общее количество непрочитанных сообщений. |
| `cursor` | string |  | Указатель для выборки следующих данных. |
| `has_next` | boolean |  | Признак, что в ответе вернулись не все чаты: - `true` — сделайте повторный запрос с новым параметром `cursor` для получения остальных чатов; - `false` — ответ содержит все чаты для фильтра, который был задан в запросе.  |

[Response 200](../_shared/examples/POST__v3_chat_list_200.json)

### `400` Неверный параметр


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 400](../_shared/examples/POST__v1_roles_default.json)

### `403` Доступ запрещён


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 403](../_shared/examples/POST__v1_roles_default.json)

### `404` Ответ не найден


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 404](../_shared/examples/POST__v1_roles_default.json)

### `409` Конфликт запроса


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 409](../_shared/examples/POST__v1_roles_default.json)

### `500` Внутренняя ошибка сервера


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 500](../_shared/examples/POST__v1_roles_default.json)
