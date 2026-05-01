# `POST` /v1/delivery/check

**Tag:** [DeliveryAPI](index.md)

**operationId:** `DeliveryCheck`

**Проверить доступность доставки для покупателя**

Проверяет доступность доставки Ozon для покупателя. Не учитывает ограничения по сумме покупки, категории товаров и географии.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `client_phone` | string | ✓ | Номер телефона покупателя. |
## Responses

### `200` Успешно


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `is_possible` | boolean |  | `true`, если доставка доступна.  |

[Response 200](../_shared/examples/POST__v1_delivery_check_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
