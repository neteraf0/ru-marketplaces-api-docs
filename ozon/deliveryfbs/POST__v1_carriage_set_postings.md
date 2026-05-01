# `POST` /v1/carriage/set-postings

**Tag:** [DeliveryFBS](index.md)

**operationId:** `CarriageAPI_SetPostings`

**Изменение состава отгрузки**


Метод недоступен для продавцов из СНГ.

Полностью перезаписывает список заказов в отгрузке. Передавайте только те заказы, которые находятся в статусе Ожидает отгрузки, и вы готовы их отгрузить.


Чтобы вернуться к списку заказов, удалите отгрузку с помощью метода /v1/carriage/cancel, и создайте новую.


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `carriage_id` | integer | ✓ | Идентификатор отгрузки. |
| `posting_numbers` | array | ✓ | Актуальный список отправлений. |
## Responses

### `200` Информация об отправлении


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` |  |  |  |

[Response 200](../_shared/examples/POST__v1_carriage_set_postings_200.json)

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
