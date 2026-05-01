# `POST` /v1/fbp/draft/direct/seller-dlv/create

**Tag:** [DraftDirectFBP](index.md)

**operationId:** `FbpDraftDirectSellerDlvCreate`

**Создать черновик с доставкой силами продавца**

Вы можете оставить обратную связь о работе метода в [комментариях](https://dev.ozon.ru/community/1700-FBP-metody/) в сообществе разработчиков Ozon for dev.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `bundle_id` | string | ✓ | Идентификатор провалидированного списка товаров. |
| `delivery_details` | v1FbpDraftDirectSellerDlvCreateRequestDirectDetails | ✓ | Детали доставки. |
| `package_units_count` | integer | ✓ | Количество грузомест. |
| `warehouse_id` | integer | ✓ | Идентификатор склада продавца. |
## Responses

### `200` Черновик создан


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `draft_id` | integer |  | Идентификатор черновика. |
| `row_version` | integer |  | Идентификатор актуальной версии черновика. |
| `supply_id` | string |  | Идентификатор заявки на поставку. |

[Response 200](../_shared/examples/POST__v1_fbp_draft_direct_seller_dlv_create_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
