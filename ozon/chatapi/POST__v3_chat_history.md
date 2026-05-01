# `POST` /v3/chat/history

**Tag:** [ChatAPI](index.md)

**operationId:** `ChatAPI_ChatHistoryV3`

**История чата**

Возвращает историю сообщений чата. По умолчанию от самого нового сообщения к старым.  Получите список чатов с покупателем `chats.chat.chat_type="Buyer_Seller"` в ответе метода [/v3/chat/list](#operation/ChatAPI_ChatListV3).

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `chat_id` | string | ✓ | Идентификатор чата. |
| `direction` | string |  | Направление сортировки сообщений: - `Forward` — от старых к новым. - `Backward` — от новых к старым.  Значение по умолчанию — `Backward`. Количество сообщений можно установить в параметре `limit`.  |
| `filter` | ChatHistoryRequestFilter |  | Фильтр по сообщениям. |
| `from_message_id` | integer |  | Идентификатор сообщения, с которого нужно начать вывод истории чата. По умолчанию — последнее видимое сообщение.  Параметр `from_message_id` обязательный, если `direction = Forward`.  |
| `limit` | integer |  | Количество сообщений в ответе. По умолчанию — 50. Максимальное значение — 1000. |

[Request example](examples/POST__v3_chat_history_req.json)

## Responses

### `200` История чата


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `has_next` | boolean |  | Признак, что в ответе вернули не все сообщения. |
| `messages` | array |  | Массив сообщений, отсортированный в соответствии с параметром `direction` из тела запроса. |

[Response 200](../_shared/examples/POST__v3_chat_history_200.json)

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
