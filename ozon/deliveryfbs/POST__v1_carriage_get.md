# `POST` /v1/carriage/get

**Tag:** [DeliveryFBS](index.md)

**operationId:** `CarriageGet`

**Информация о перевозке**

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `carriage_id` | integer | ✓ | Идентификатор перевозки. |
## Responses

### `200` Информация о перевозке


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `act_type` | string |  | Тип акта приёма-передачи. Актуально для продавцов FBS. |
| `all_blr_traceable` | boolean |  | `true`, если отгрузка с прослеживаемыми товарами.  |
| `is_waybill_enabled` | boolean |  | `true`, если доступна печать транспортной накладной.  |
| `is_econom` | boolean |  | `true`, если отгрузка относится к товарам «Суперэконом».  |
| `arrival_pass_ids` | array |  | Список идентификаторов пропусков, оформленных на перевозку. |
| `available_actions` | array |  | Доступные действия с перевозкой: - `get_shipping_list` — получить лист отгрузки; - `get_act_of_acceptance` — получить акт приёма-передачи; - `get_waybill` — получить товарную накладную в формате PDF; - `set_arrival_passes` — [оформить пропуск](#operation/carriagePassCreate).  |
| `cancel_availability` | carriageCarriageGetResponseCancelAvailability |  | Возможность отмены. |
| `carriage_id` | integer |  | Идентификатор перевозки. |
| `company_id` | integer |  | Идентификатор продавца. |
| `containers_count` | integer |  | Количество грузовых мест. |
| `created_at` | string |  | Дата создания перевозки. |
| `delivery_method_id` | integer |  | Идентификатор метода доставки. |
| `departure_date` | string |  | Дата выполнения перевозки. |
| `first_mile_type` | string |  | Тип первой мили. |
| `has_postings_for_next_carriage` | boolean |  | `true`, если есть отправления, которые не попали в перевозку, но нужно отгрузить.  |
| `integration_type` | string |  | Тип перевозки. |
| `is_container_label_printed` | boolean |  | `true`, если вы уже напечатали этикетки на грузовые места.  |
| `is_partial` | boolean |  | `true`, если перевозка частичная.  |
| `partial_num` | integer |  | Порядковый номер частичной перевозки. |
| `retry_count` | integer |  | Количество повторных попыток создания перевозки. |
| `status` | string |  | Статус перевозки: - `received` — идёт приёмка, - `closed` — завершена после приёмки, - `sended` — отправлена, - `cancelled` — отменена.  |
| `tpl_provider_id` | integer |  | Идентификатор провайдера доставки. |
| `updated_at` | string |  | Дата последнего обновления информации о перевозке. |
| `warehouse_id` | integer |  | Идентификатор склада. |

[Response 200](../_shared/examples/POST__v1_carriage_get_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
