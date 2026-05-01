# `POST` /v1/return/giveout/barcode

**Tag:** [ReturnAPI](index.md)

**operationId:** `ReturnAPI_GiveoutGetBarcode`

**Значение штрихкода для возвратных отгрузок**

Используйте этот метод, чтобы получить штрихкод из ответа методов [/v1/return/giveout/get-png](#operation/ReturnAPI_GiveoutGetPNG) и [/v1/return/giveout/get-pdf](#operation/ReturnAPI_GiveoutGetPDF) в текстовом виде.

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

### `200` Значение штрихкода


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `barcode` | string |  | Значение штрихкода в текстовом виде. |

[Response 200](../_shared/examples/POST__v1_return_giveout_barcode_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
