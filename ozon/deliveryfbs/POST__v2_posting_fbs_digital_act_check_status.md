# `POST` /v2/posting/fbs/digital/act/check-status

**Tag:** [DeliveryFBS](index.md)

**operationId:** `PostingAPI_PostingFBSDigitalActCheckStatus`

**Статус формирования накладной**


Метод устаревает и будет отключён 22 марта 2026 года. Переключитесь на /v2/posting/fbs/act/check-status.


> ⚠️ **Deprecated**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `id` | integer | ✓ | Номер задания на формирование документов (также идентификатор перевозки) из метода [POST /v2/posting/fbs/act/create](#operation/PostingAPI_PostingFBSActCreate). |
## Responses

### `200` Статус формирования накладной


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `id` | integer |  | Номер задания на формирование документов. |
| `status` | string |  | Cтатус формирования документов: - `FORMING` — ещё не готовы, - `FORMED` — сформированы успешно, - `CONFIRMED` — подписаны Ozon, - `CONFIRMED_WITH_MISMATCH` — подписаны Ozon с расхождениями, - `NOT_FOUND` — документы не найдены, - `UNKNOWN_ERROR` — произошла ошибка.  |

[Response 200](../_shared/examples/POST__v2_posting_fbs_digital_act_check_status_200.json)

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
