# `POST` /v1/fbp/draft/drop-off/product/validate

**Tag:** [DraftDropOffFBP](index.md)

**operationId:** `FbpDraftDropOffProductValidate`

**Проверить список товаров, которые склад партнёра может принять**

Вы можете оставить обратную связь о работе метода в [комментариях](https://dev.ozon.ru/community/1700-FBP-metody/) в сообществе разработчиков Ozon for dev.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `skus` | array | ✓ | Идентификаторы товаров в системе Ozon — SKU. |
| `warehouse_id` | integer | ✓ | Идентификатор склада. |
## Responses

### `200` Результат проверки


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `approved_items` | array |  | Принятые товары. |
| `bundle_generated` | boolean |  | `true`, если создан товарный состав.  |
| `bundle_id` | string |  | Идентификатор провалидированного списка товаров. |
| `rejected_items` | array |  | Отклонённые товары. |

[Response 200](../_shared/examples/POST__v1_fbp_draft_direct_product_validate_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
