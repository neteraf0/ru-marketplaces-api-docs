# `POST` /v1/fbp/order/get

**Tag:** [DeliveryFBP](index.md)

**operationId:** `FbpAPI_FbpOrderGet`

**Получить информацию о конкретной поставке**

Вы можете оставить обратную связь по этому методу в комментариях к [обсуждению](https://dev.ozon.ru/community/1700-FBP-metody/) в сообществе разработчиков Ozon for dev.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `supply_id` | string | ✓ | Идентификатор поставки. |
## Responses

### `200` Детали поставки


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `attention_reasons` | array |  | Причины предупреждения: - `ORDER_ATTENTION_TYPE_UNSPECIFIED` — не определена; - `OLD` — устаревшая заявка; - `TIME_SLOT_EXPIRED` — таймслот просрочен.  |
| `bundle_uuid` | string |  | Идентификатор товарного состава. |
| `can_be_cancelled` | boolean |  | `true`, если заявку можно отменить.  |
| `cancellation_state` | v1CancellationState |  | Статус отмены. |
| `created_date` | string |  | Дата создания поставки. |
| `delivery_details` | fbpv1DeliveryDetails |  | Детали доставки. |
| `draft_id` | integer |  | Идентификатор черновика. |
| `has_consignment_note` | boolean |  | `true`, если есть подписанные документы.  |
| `has_label` | boolean |  | `true`, если есть этикетки.  |
| `id` | integer |  | Идентификатор заявки на поставку. |
| `locked` | boolean |  | `true`, если нельзя редактировать поставку.  |
| `order_number` | string |  | Номер поставки. |
| `package_units_count` | integer |  | Количество грузомест. |
| `receive_date` | string |  | Дата и время принятия поставки. |
| `row_version` | integer |  | Идентификатор актуальной версии черновика. |
| `status` | v1OrderStatusEnum |  | Статус заказа:  - `ORDER_STATUS_UNSPECIFIED` — не определён;  - `READY_TO_SUPPLY` — готов к отгрузке;  - `FILLING_DELIVERY_DETAILS` — заполнение данных поставки;  - `COURIER_ASSIGNED` — курьер назначен;  - `COURIER_PICKED_UP` — курьер забрал поставку;  - `ACCEPTANCE_AT_DROP_OFF_POINT` — принято на drop-off пункте;  - `IN_TRANSIT_TO_STORAGE_WAREHOUSE` — в пути на склад размещения;  - `ACCEPTANCE_AT_STORAGE_WAREHOUSE` — приёмка на складе;  - `CANCELLED` — заявка отменена.  |
| `supply_id` | string |  | Идентификатор поставки. |
| `warehouse_id` | integer |  | Идентификатор склада. |

[Response 200](../_shared/examples/POST__v1_fbp_order_get_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
