# `POST` /v1/return/giveout/get-pdf

**Tag:** [ReturnAPI](index.md)

**operationId:** `ReturnAPI_GiveoutGetPDF`

**Штрихкод для получения возвратной отгрузки в формате PDF**

Возвращает PDF-файл со штрихкодом. Метод работает только для схемы FBS.

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

### `200` Штрихкод для возвратной отгрузки


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `file_content` | string |  | PDF-файл со штрихкодом в бинарном виде. |
| `file_name` | string |  | Название файла. |
| `content_type` | string |  | Тип файла. |

[Response 200](../_shared/examples/POST__v1_return_giveout_get_pdf_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
