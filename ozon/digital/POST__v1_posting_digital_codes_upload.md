# `POST` /v1/posting/digital/codes/upload

**Tag:** [Digital](index.md)

**operationId:** `UploadPostingCodes`

**Загрузить коды цифровых товаров для отправления**

Метод доступен только продавцам, работающим с цифровыми товарами. Вы можете загрузить коды цифровых товаров в течение 24 часов с момента получения заказа.

Передайте все коды цифровых товаров к каждому товару в заказе за один запрос. Если передадите не все коды, запрос вернётся с ошибкой.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `exemplars_by_sku` | array |  | Данные о кодах цифрового товара по SKU. |
| `posting_number` | string |  | Номер отправления. |

[Request example](examples/POST__v1_posting_digital_codes_upload_req.json)

## Responses

### `200` Коды цифровых товаров загружены


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `exemplars_by_sku` | array |  | Данные о кодах цифрового товара по SKU. |

[Response 200](../_shared/examples/POST__v1_posting_digital_codes_upload_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
