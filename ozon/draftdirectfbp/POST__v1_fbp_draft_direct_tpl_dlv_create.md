# `POST` /v1/fbp/draft/direct/tpl-dlv/create

**Tag:** [DraftDirectFBP](index.md)

**operationId:** `FbpAPI_FbpDraftDirectTplDlvCreate`

**Создать черновик заявки на доставку сторонней транспортной компанией**

Вы можете оставить обратную связь о работе метода в [комментариях](https://dev.ozon.ru/community/1700-FBP-metody/) в сообществе разработчиков Ozon for dev.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `bundle_id` | string | ✓ | Идентификатор комплекта. |
| `delivery_details` | v1FbpDraftDirectTplDlvCreateRequestDirectDetails | ✓ | Детали доставки. |
| `package_units_count` | integer | ✓ | Количество грузомест. |
| `warehouse_id` | integer | ✓ | Идентификатор склада. |
## Responses

### `200` Статус генерации


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `draft_id` | integer |  | Идентификатор черновика. |
| `row_version` | integer |  | Идентификатор актуальной версии черновика. |
| `supply_id` | string |  | Идентификатор поставки. |

[Response 200](../_shared/examples/POST__v1_fbp_draft_direct_seller_dlv_create_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
