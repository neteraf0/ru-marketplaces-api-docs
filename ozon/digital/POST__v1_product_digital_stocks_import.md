# `POST` /v1/product/digital/stocks/import

**Tag:** [Digital](index.md)

**operationId:** `DigitalProductAPI_StocksImport`

**Обновить количество цифровых товаров**

Метод доступен только продавцам, работающим с цифровыми товарами.

Используйте метод, чтобы изменить информацию о количестве товара в наличии.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `stocks` | array |  | Данные об остатках. |

[Request example](examples/POST__v1_product_digital_stocks_import_req.json)

## Responses

### `200` Количество товаров обновлено


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `status` | array |  | Информация о товарах. |

[Response 200](../_shared/examples/POST__v1_product_digital_stocks_import_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
