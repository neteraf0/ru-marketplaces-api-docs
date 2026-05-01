# `POST` /v1/notification/set

**Tag:** [Notification](index.md)

**operationId:** `SetNotification`

**Подключить URL-адрес для уведомлений**

Вы можете оставить обратную связь о работе метода в [комментариях](https://dev.ozon.ru/community/1978-Novye-beta-metody-dlia-upravleniia-podkliucheniiami-PUSH-uvedomlenii/) в сообществе разработчиков Ozon for dev.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `types` | array | ✓ | Типы уведомлений: - `TYPE_NEW_MESSAGE` — новое сообщение в чате; - `TYPE_UPDATE_MESSAGE` — изменение сообщения в чате; - `TYPE_MESSAGE_READ` — ваше сообщение прочитано покупателем или поддержкой; - `TYPE_CHAT_CLOSED` — чат закрыт; - `TYPE_NEW_POSTING` — новое отправление; - `TYPE_POSTING_SHIPPED` — отправление в доставке; - `TYPE_POSTING_CANCELLED` — отмена отправления; - `TYPE_STATE_CHANGED` — изменение статуса отправления; - `TYPE_DELIVERY_DATE_CHANGED` — изменение даты доставки отправления; - `TYPE_CUTOFF_DATE_CHANGED` — изменение даты отгрузки отправления; - `TYPE_CREATE_ITEM` — создание товара или ошибка при его создании; - `TYPE_UPDATE_ITEM` — обновление товара или ошибка при обновлении; - `TYPE_CREATE_OR_UPDATE_ITEM` — создание и обновление товара или ошибка в процессе; - `TYPE_STOCKS_CHANGED` — изменение остатков на складах продавца.  |
| `url` | string | ✓ | URL-адрес. |
## Responses

- **200** URL-адрес подключён
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
