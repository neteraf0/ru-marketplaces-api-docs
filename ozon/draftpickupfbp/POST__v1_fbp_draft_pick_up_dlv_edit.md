# `POST` /v1/fbp/draft/pick-up/dlv/edit

**Tag:** [DraftPickupFBP](index.md)

**operationId:** `FbpAPI_FbpDraftPickupDlvEdit`

**Изменить черновик заявки на pick-up поставку**

Вы можете оставить обратную связь по этому методу в комментариях к [обсуждению](https://dev.ozon.ru/community/1700-FBP-metody/) в сообществе разработчиков Ozon for dev.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `pickup_details` | v1FbpDraftPickupDlvEditRequestDeliveryDetails | ✓ | Детали доставки. |
| `row_version` | integer | ✓ | Идентификатор актуальной версии черновика. |
| `supply_id` | string | ✓ | Идентификатор поставки. |
## Responses

### `200` Информация отредактирована


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `row_version` | integer |  | Идентификатор актуальной версии черновика. |

[Response 200](../_shared/examples/POST__v1_fbp_draft_drop_off_dlv_edit_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
