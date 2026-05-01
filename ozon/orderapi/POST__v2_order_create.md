# `POST` /v2/order/create

**Tag:** [OrderAPI](index.md)

**operationId:** `OrderAPI_OrderCreate`

**Создать заказ**

Создаёт заказ для покупателя и получателя в системе Ozon. Передайте вариант доставки из ответа метода [/v2/delivery/checkout](#operation/DeliveryCheckout).

В ответе могут быть не все отправления. Получите список всех отправлений по номеру заказа `order_number` методом:
- [/v2/posting/fbo/list](#operation/PostingAPI_GetFboPostingList) — для схемы FBO;
- [/v3/posting/fbs/list](#operation/PostingAPI_GetFbsPostingListV3) — для схемы FBS.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `buyer` | OrderCreateRequestBuyer | ✓ | Информация о покупателе. |
| `delivery` | OrderCreateRequestDelivery | ✓ | Информация о доставке. |
| `delivery_schema` | OrderCreateRequestV2DeliverySchemaEnum | ✓ | Схема доставки: - `MIX` — на выбор Ozon; - `FBO` — FBO; - `FBS` — FBS.  |
| `recipient` | OrderCreateRequestRecipient | ✓ | Информация о получателе. |
| `splits` | array | ✓ | Информация об отправлениях в заказе. |
## Responses

### `200` Заказ создан


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `order_number` | string |  | Номер заказа. |
| `postings` | array |  | Отправления. |

[Response 200](../_shared/examples/POST__v2_order_create_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
