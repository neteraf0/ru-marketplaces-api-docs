# `POST` /v1/fbp/draft/get

**Tag:** [DeliveryFBPDraft](index.md)

**operationId:** `FbpAPI_FbpDraftGet`

**Получить информацию о черновике поставки**

Вы можете оставить обратную связь о работе метода в [комментариях](https://dev.ozon.ru/community/1700-FBP-metody/) в сообществе разработчиков Ozon for dev.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `supply_id` | string | ✓ | Идентификатор поставки. |
## Responses

### `200` Детали черновика поставки


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `bundle_id` | string |  | Идентификатор списка провалидированных товаров. |
| `cancellation_state` | v1CancellationState |  | Статус отмены. |
| `created_at` | string |  | Дата создания черновика. |
| `decline_reason` | FbpDraftGetResponseDeclineReason |  | Причина отказа. |
| `deleted_at` | string |  | Дата удаления черновика. |
| `delivery_details` | v1fbpDeliveryDetails |  | Детали доставки. |
| `editable` | boolean |  | `true`, если черновик можно изменить.  |
| `id` | integer |  | Идентификатор черновика. |
| `is_cancelable` | boolean |  | `true`, если черновик можно отменить.  |
| `is_deletable` | boolean |  | `true`, если черновик можно удалить.  |
| `is_registration_available` | boolean |  | `true`, если доступна регистрация.  |
| `locked` | boolean |  | `true`, если черновик заблокирован.  |
| `package_units_count` | integer |  | Количество грузомест. |
| `row_version` | integer |  | Идентификатор актуальной версии черновика. |
| `status` | v1DraftStatusEnum |  | Статус черновика: - `DRAFT_STATUS_UNSPECIFIED` — не определён; - `NEW` — новый; - `SUPPLY_VARIANT_CONFIRMATION` — ожидает подтверждения; - `SUPPLY_NOT_CONFIRMED` — отклонён складом.  |
| `supply_id` | string |  | Идентификатор поставки. |
| `warehouse_id` | integer |  | Идентификатор склада. |

[Response 200](../_shared/examples/POST__v1_fbp_draft_get_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
