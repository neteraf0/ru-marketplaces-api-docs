# `POST` /v1/finance/products/buyout

**Tag:** [FinanceAPI](index.md)

**operationId:** `GetFinanceProductsBuyout`

**Отчёт о выкупленных товарах**

Возвращает отчёт о товарах, которые выкупил Ozon для продажи в ЕАЭС и другие страны. Соответствует разделу **Финансы → Документы → УПД по сделкам с юр. лицами → УПД по выкупленным товарам** в личном кабинете.

[Подробнее о продаже товаров в ЕАЭС и другие страны в Базе знаний](https://seller-edu.ozon.ru/commissions-tariffs/commissions-tariffs-ozon/prodaji-tovarov-v-eaes-i-drugie-strany?search=выкупленные+товары)

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `date_from` | string | ✓ | Дата, с которой будут данные в отчёте. |
| `date_to` | string | ✓ | Дата, по которую будут данные в отчёте.  Максимальный период — 31 день.  |

[Request example](examples/POST__v1_finance_products_buyout_req.json)

## Responses

### `200` Отчёт по выкупленным товарам


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `products` | array |  | Список выкупленных товаров |

[Response 200](../_shared/examples/POST__v1_finance_products_buyout_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
