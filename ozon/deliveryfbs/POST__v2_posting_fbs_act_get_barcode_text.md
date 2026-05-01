# `POST` /v2/posting/fbs/act/get-barcode/text

**Tag:** [DeliveryFBS](index.md)

**operationId:** `PostingAPI_PostingFBSGetBarcodeText`

**Значение штрихкода для отгрузки отправления**

Используйте этот метод, чтобы получить штрихкод из ответа
[/v2/posting/fbs/act/get-barcode](#operation/PostingAPI_PostingFBSGetBarcode) в текстовом виде.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `id` | integer | ✓ | Идентификатор перевозки. |

[Request example](examples/POST__v2_posting_fbs_act_get_barcode_text_req.json)

## Responses

### `200` Значение штрихкода


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | string |  | Штрихкод в текстовом виде. |

[Response 200](../_shared/examples/POST__v2_posting_fbs_act_get_barcode_text_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
