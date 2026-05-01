# `POST` /v1/barcode/add

**Tag:** [BarcodeAPI](index.md)

**operationId:** `add-barcode`

**Привязать штрихкод к товару**

Если у товара есть штрихкод, который не указан в системе Ozon, привяжите его с помощью этого метода.
Если штрихкода нет, вы можете создать его через метод [/v1/barcode/generate](#operation/generate-barcode).

На одном товаре может быть до 100 штрихкодов.
С одного аккаунта продавца можно использовать метод не больше 20 раз в минуту.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `barcodes` | array | ✓ | Список штрихкодов и товаров. |

[Request example](examples/POST__v1_barcode_add_req.json)

## Responses

### `200` Штрихкод привязан


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `errors` | array |  | Список ошибок. |

[Response 200](../_shared/examples/POST__v1_barcode_add_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
