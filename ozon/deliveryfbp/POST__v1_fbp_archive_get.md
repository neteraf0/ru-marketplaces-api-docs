# `POST` /v1/fbp/archive/get

**Tag:** [DeliveryFBP](index.md)

**operationId:** `FbpAPI_FbpArchiveGet`

**Получить информацию о завершённой поставке**

Вы можете оставить обратную связь по этому методу в комментариях к [обсуждению](https://dev.ozon.ru/community/1700-FBP-metody/) в сообществе разработчиков Ozon for dev.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `supply_id` | string | ✓ | Идентификатор поставки. |
## Responses

### `200` Информация о завершённой поставке


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `act_file_uuid` | string |  | Идентификатор акта приёмки. |
| `bundle_id` | string |  | Идентификатор провалидированного списка товаров. |
| `bundle_sku_summary` | v1ArchiveSkuSummary |  | Сводная информация по товарам в поставке. |
| `business_flow_type_id` | integer |  | Идентификатор типа поставки. |
| `created_date` | string |  | Дата и время создания заявки на поставку. |
| `decline_reason` | v1ArchiveDeclineReason |  | Причина отклонения поставки. |
| `delivery_details` | fbpv1DeliveryDetails |  | Детали доставки. |
| `has_act` | boolean |  | `true`, если был сформирован акт приёмки.  |
| `has_label` | boolean |  | `true`, если были сформированы этикетки.  |
| `id` | integer |  | Номер записи в архиве. |
| `order_draft_id` | integer |  | Идентификатор черновика поставки. |
| `order_number` | string |  | Идентификатор завершённой поставки. |
| `package_units_count` | integer |  | Количество грузомест. |
| `receive_date` | string |  | Дата и время принятия поставки. |
| `row_version` | integer |  | Идентификатор актуальной версии черновика. |
| `status` | v1ArchiveStatusEnum |  | Статус завершённой поставки:   - `ARCHIVE_STATUS_UNSPECIFIED` — не определён;   - `COMPLETED` — завершена;   - `REJECTED_AT_SUPPLY_WAREHOUSE` — отклонена складом;   - `CANCELLED_BY_SELLER` — отменена продавцом.  |
| `supply_id` | string |  | Идентификатор поставки. |
| `warehouse_id` | integer |  | Идентификатор склада. |

[Response 200](../_shared/examples/POST__v1_fbp_archive_get_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
