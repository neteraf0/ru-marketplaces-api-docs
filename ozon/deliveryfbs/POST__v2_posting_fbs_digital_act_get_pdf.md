# `POST` /v2/posting/fbs/digital/act/get-pdf

**Tag:** [DeliveryFBS](index.md)

**operationId:** `PostingAPI_PostingFBSGetDigitalAct`

**Получить лист отгрузки по перевозке**


Метод устаревает и будет отключён 22 марта 2026 года. Переключитесь на /v2/posting/fbs/act/get-pdf.


Вы можете получить документы, если в ответе метода [/v2/posting/fbs/digital/act/check-status](#operation/PostingAPI_PostingFBSDigitalActCheckStatus) был один из статусов:
- `FORMED` — перевозка сформирована успешно,
- `CONFIRMED` — перевозка подтверждена Ozon,
- `CONFIRMED_WITH_MISMATCH` — перевозка принята Ozon с расхождениями.

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
| `doc_type` |  |  | Тип электронного документа: - `act_of_acceptance` — лист отгрузки, - `act_of_mismatch` — акт о расхождениях, - `act_of_excess` — акт об излишках, - `waybill` — транспортная накладная.  |

[Request example](examples/POST__v2_posting_fbs_digital_act_get_pdf_req.json)

## Responses

### `200` Файл с документом


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `file_content` | string |  | Содержание файла в бинарном виде. |
| `file_name` | string |  | Название файла. |
| `content_type` | string |  | Тип файла. |

[Response 200](../_shared/examples/POST__v2_posting_fbs_digital_act_get_pdf_200.json)

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
