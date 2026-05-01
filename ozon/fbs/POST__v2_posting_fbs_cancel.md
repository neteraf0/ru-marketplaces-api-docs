# `POST` /v2/posting/fbs/cancel

**Tag:** [FBS](index.md)

**operationId:** `PostingAPI_CancelFbsPosting`

**Отменить отправление**

Меняет статус отправления на `cancelled`.

Перед началом работы проверьте причины отмены для конкретного отправления методом [/v1/posting/fbs/cancel-reason](#operation/PostingAPI_GetPostingFbsCancelReasonV1).

Условно-доставленные отправления отменить нельзя.

Если значение параметра `cancel_reason_id` — 402, заполните поле `cancel_reason_message`.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `cancel_reason_id` | integer | ✓ | Идентификатор причины отмены отправления. |
| `cancel_reason_message` | string |  | Дополнительная информация по отмене. Если `cancel_reason_id = 402`, параметр обязательный. |
| `posting_number` | string | ✓ | Идентификатор отправления. |

[Request example](examples/POST__v2_posting_fbs_cancel_req.json)

## Responses

### `200` Отправление отменено


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | boolean |  | Результат обработки запроса. `true`, если запрос выполнился без ошибок. |

[Response 200](../_shared/examples/POST__v1_product_archive_200.json)

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
