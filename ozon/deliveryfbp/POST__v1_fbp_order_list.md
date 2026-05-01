# `POST` /v1/fbp/order/list

**Tag:** [DeliveryFBP](index.md)

**operationId:** `FbpAPI_FbpOrderList`

**Получить список поставок**

Вы можете оставить обратную связь по этому методу в комментариях к [обсуждению](https://dev.ozon.ru/community/1700-FBP-metody/) в сообществе разработчиков Ozon for dev.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `count` | integer | ✓ | Количество поставок в ответе. |
| `last_id` | integer |  | Идентификатор последней поставки на странице. Для первого запроса оставьте это поле пустым.  Чтобы получить следующие значения, укажите `id` последней поставки из ответа предыдущего запроса.  |
## Responses

### `200` Список поставок


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `has_next` | boolean |  | `true`, если в ответе вернули не все поставки.  |
| `items` | array |  | Поставки. |
| `last_id` | integer |  | Идентификатор последней поставки на странице. |

[Response 200](../_shared/examples/POST__v1_fbp_order_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
