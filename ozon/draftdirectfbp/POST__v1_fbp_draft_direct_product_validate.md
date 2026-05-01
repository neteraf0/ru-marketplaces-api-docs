# `POST` /v1/fbp/draft/direct/product/validate

**Tag:** [DraftDirectFBP](index.md)

**operationId:** `FbpDraftDirectProductValidate`

**Проверить список товаров для склада партнёра**

Вы можете оставить обратную связь по этому методу в комментариях к [обсуждению](https://dev.ozon.ru/community/1700-FBP-metody/) в сообществе разработчиков Ozon for dev.

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
| `approved_items` | array |  | Подтверждённые товары. |
| `bundle_generated` | boolean |  | `true`, если провалидированный список товаров создан. |
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
