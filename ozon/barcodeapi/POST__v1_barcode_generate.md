# `POST` /v1/barcode/generate

**Tag:** [BarcodeAPI](index.md)

**operationId:** `generate-barcode`

**Создать штрихкод для товара**

Если у товара нет штрихкода, вы можете создать его с помощью этого метода.
Если штрихкод уже есть, но он не указан в системе Ozon, вы можете привязать его через метод [/v1/barcode/add](#operation/add-barcode).

За один запрос вы можете создать штрихкоды не больше чем для 100 товаров.
С одного аккаунта продавца можно использовать метод не больше 20 раз в минуту.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `product_ids` | array | ✓ | Идентификаторы товаров, для которых нужно создать штрихкод. |

[Request example](examples/POST__v1_barcode_generate_req.json)

## Responses

### `200` Штрихкод создан


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `errors` | array |  | Ошибки при создании штрихкода. |

[Response 200](../_shared/examples/POST__v1_barcode_generate_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
