# `POST` /v1/fbp/draft/direct/tpl-dlv/edit

**Tag:** [DraftDirectFBP](index.md)

**operationId:** `FbpAPI_FbpDraftDirectTplDlvEdit`

**Редактировать черновик поставки со способом доставки сторонней транспортной компанией**

Вы можете оставить обратную связь о работе метода в [комментариях](https://dev.ozon.ru/community/1700-FBP-metody/) в сообществе разработчиков Ozon for dev.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `row_version` | integer | ✓ | Идентификатор актуальной версии черновика. |
| `supply_id` | string | ✓ | Идентификатор поставки. |
| `tracking_number` | string | ✓ | Трек-номер отправления. |
| `transport_company_name` | string | ✓ | Название транспортной компании. |
## Responses

### `200` Черновик изменён


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `error` | v1OrderDraftValidationError |  | Информация об ошибке. |
| `is_error` | boolean |  | `true`, если есть ошибка.  |
| `row_version` | integer |  | Идентификатор актуальной версии черновика. |

[Response 200](../_shared/examples/POST__v1_fbp_draft_direct_tpl_dlv_edit_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
