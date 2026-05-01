# `POST` /v1/return/giveout/barcode-reset

**Tag:** [ReturnAPI](index.md)

**operationId:** `ReturnAPI_GiveoutBarcodeReset`

**Сгенерировать новый штрихкод**

Используйте метод, если ваш штрихкод попал в посторонние руки.

Метод возвращает PNG-файл с новым штрихкодом. После использования метода вы не сможете получить возвратную отгрузку по старым штрихкодам.
Чтобы получить новый штрихкод в PDF-формате, запросите его методом [/v1/return/giveout/get-pdf](#operation/ReturnAPI_GiveoutGetPDF).

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

### `200` Новый штрихкод


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `file_content` | string |  | Изображение со штрихкодом в бинарном виде. |
| `file_name` | string |  | Название файла. |
| `content_type` | string |  | Тип файла. |

[Response 200](../_shared/examples/POST__v1_return_giveout_get_png_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
