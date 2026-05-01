# `POST` /v2/delivery/checkout

**Tag:** [DeliveryAPI](index.md)

**operationId:** `DeliveryCheckout`

**Получить доступные варианты доставки**

Проверяет доступность доставки товаров на указанный адрес или в точку выдачи и отображает сроки доставки.

Проверяйте наличие товаров и маршруты во время оформления заказа, чтобы точно рассчитать сроки доставки.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `buyer_phone` | string |  | Номер телефона покупателя. |
| `delivery_schema` | v2DeliveryCheckoutRequestV2DeliverySchemaEnum |  | Схема доставки: - `MIX` — на выбор Ozon; - `FBO` — FBO; - `FBS` — FBS.  |
| `delivery_type` | v1DeliveryCheckoutRequestDeliveryType |  | Способ доставки. |
| `items` | array |  | Информация о товарах. |
## Responses

### `200` Успешно


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `splits` | array |  | Результат запроса. |

[Response 200](../_shared/examples/POST__v2_delivery_checkout_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
