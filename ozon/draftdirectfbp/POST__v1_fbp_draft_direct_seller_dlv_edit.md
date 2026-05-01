# `POST` /v1/fbp/draft/direct/seller-dlv/edit

**Tag:** [DraftDirectFBP](index.md)

**operationId:** `FbpDraftDirectSellerDlvEdit`

**Обновить информацию о доставке силами продавца в черновике**

Вы можете оставить обратную связь о работе метода в [комментариях](https://dev.ozon.ru/community/1700-FBP-metody/) в сообществе разработчиков Ozon for dev.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `driver_name` | string | ✓ | ФИО водителя. |
| `row_version` | integer | ✓ | Идентификатор актуальной версии черновика. |
| `supply_id` | string | ✓ | Идентификатор заявки на поставку. |
| `vehicle_number` | string | ✓ | Номер автомобиля. |
| `vehicle_type` | string | ✓ | Тип автомобиля. |
## Responses

### `200` Черновик обновлён


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `error` | v1OrderDraftValidationError |  | Информация об ошибке. |
| `is_error` | boolean |  | `true`, если есть ошибка.  |
| `row_version` | integer |  | Идентификатор актуальной версии черновика. |

[Response 200](../_shared/examples/POST__v1_fbp_draft_direct_seller_dlv_edit_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
