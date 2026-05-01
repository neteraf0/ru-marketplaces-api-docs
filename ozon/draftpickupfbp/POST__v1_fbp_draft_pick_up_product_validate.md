# `POST` /v1/fbp/draft/pick-up/product/validate

**Tag:** [DraftPickupFBP](index.md)

**operationId:** `FbpAPI_FbpDraftPickUpProductValidate`

**Провалидировать список товаров для pick-up поставки**

Вы можете оставить обратную связь по этому методу в комментариях к [обсуждению](https://dev.ozon.ru/community/1700-FBP-metody/) в сообществе разработчиков Ozon for dev.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `skus` | array | ✓ | Список идентификаторов товаров — SKU. |
| `warehouse_id` | integer | ✓ | Идентификатор склада. |
## Responses

### `200` Список провалидирован


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `approved_items` | array |  | Подтверждённые товары. |
| `bundle_generated` | boolean |  | `true`, если проверенный список товаров создан.  |
| `bundle_id` | string |  | Идентификатор провалидированного списка товаров. |
| `rejected_items` | array |  | Отклонённые товары. |

[Response 200](../_shared/examples/POST__v1_fbp_draft_pick_up_product_validate_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
