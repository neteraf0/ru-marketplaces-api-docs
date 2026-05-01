# `POST` /v1/fbp/act-to/create

**Tag:** [DeliveryFBP](index.md)

**operationId:** `FbpAPI_FbpCreateConsignmentNote`

**Сгенерировать транспортную накладную**

Вы можете оставить обратную связь по этому методу в комментариях к [обсуждению](https://dev.ozon.ru/community/1700-FBP-metody/) в сообществе разработчиков Ozon for dev.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `supply_id` | string | ✓ | Идентификатор поставки. |
## Responses

### `200` Успешно


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Идентификатор транспортной накладной. |

[Response 200](../_shared/examples/POST__v1_report_placement_by_products_create_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
