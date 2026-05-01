# `POST` /v2/invoice/create-or-update

**Tag:** [SupplierAPI](index.md)

**operationId:** `InvoiceAPI_InvoiceCreateOrUpdateV2`

**Создать или изменить счёт-фактуру**

Создание или изменение таможенного счёта-фактуры для возврата НДС продавцам из Турции.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `date` | string | ✓ | Дата счёта-фактуры. |
| `hs_codes` | array |  | HS-коды товаров. |
| `number` | string |  | Номер счёта-фактуры. Номер может содержать буквы и цифры, максимальная длина — 50 символов. |
| `posting_number` | string | ✓ | Номер отправления. |
| `price` | number |  | Стоимость, указанная в счёте-фактуре. Разделитель дробной части — точка, до двух знаков после точки. |
| `price_currency` | string |  | Валюта счёта-фактуры: - `USD` — доллар,  - `EUR` — евро,  - `TRY` — турецкая лира,  - `CNY` — юань,  - `RUB` — рубль,  - `GBP` — фунт стерлингов.  Значение по умолчанию — `USD`.  |
| `url` | string | ✓ | Ссылка на счёт-фактуру. Чтобы создать ссылку, используйте метод [v1/invoice/file/upload](#operation/invoice_upload). |

[Request example](examples/POST__v2_invoice_create_or_update_req.json)

## Responses

### `200` Счёт-фактура создана или изменена


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | boolean |  | Результат работы метода. |

[Response 200](../_shared/examples/POST__v1_product_update_discount_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
