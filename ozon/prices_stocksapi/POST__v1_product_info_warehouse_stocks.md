# `POST` /v1/product/info/warehouse/stocks

**Tag:** [Prices&StocksAPI](index.md)

**operationId:** `ProductInfoWarehouseStocks`

**Получить информацию по остаткам на складе FBS и rFBS**

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `cursor` | string |  | Указатель для выборки следующих данных. |
| `limit` | integer | ✓ | Количество значений на странице. |
| `warehouse_id` | integer | ✓ | Идентификатор склада. |

[Request example](examples/POST__v1_product_info_warehouse_stocks_req.json)

## Responses

### `200` Количество товара на складе FBS и rFBS


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `cursor` | string |  | Указатель для выборки следующих данных. Если параметр пустой, данных больше нет. |
| `has_next` | boolean |  | Признак, что в ответе вернули не все товары: - `true` — сделайте повторный запрос с другим значением `cursor`, чтобы получить остальные значения; - `false` — ответ содержит все значения.  |
| `stocks` | array |  | Информация об остатках товара. |

[Response 200](../_shared/examples/POST__v1_product_info_warehouse_stocks_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
