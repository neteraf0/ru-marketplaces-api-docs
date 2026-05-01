# `POST` /v2/posting/fbs/act/get-pdf

**Tag:** [DeliveryFBS](index.md)

**operationId:** `PostingAPI_PostingFBSGetAct`

**Получить PDF c документами**

С помощью метода можно получить:
- продацам из России — лист отгрузки и транспортную накладную;
- продавцам из СНГ — акт и транспортную накладную.

Получите список доступных документов для отгрузки в параметре `available_actions` метода [/v1/carriage/get](#operation/CarriageGet).

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `id` | integer | ✓ | Номер задания на формирование документов (также идентификатор перевозки) из методов [/v2/posting/fbs/act/create](#operation/PostingAPI_PostingFBSActCreate) или [/v1/carriage/create](#operation/CarriageAPI_CarriageCreate). |

[Request example](examples/POST__v2_posting_fbs_act_get_pdf_req.json)

## Responses

### `200` Документы


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `file_content` | string |  | Содержание файла в бинарном виде. |
| `file_name` | string |  | Название файла. |
| `content_type` | string |  | Тип файла. |

[Response 200](../_shared/examples/POST__v2_posting_fbs_act_get_pdf_200.json)

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
