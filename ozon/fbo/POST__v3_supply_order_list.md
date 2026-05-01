# `POST` /v3/supply-order/list

**Tag:** [FBO](index.md)

**operationId:** `SupplyOrderList`

**Список заявок на поставку на склад Ozon**

Учитываются заявки с поставкой на конкретный склад и через [виртуальный распределительный центр (вРЦ)](https://seller-edu.ozon.ru/fbo/scheme-of-work/about#чем-отличаются-процессы-при-заявках-через-врц-и-напрямую-на-склад).

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `filter` | SupplyOrderListRequestFilter | ✓ | Фильтр. |
| `last_id` | string |  | Идентификатор последнего значения на странице. При первом запросе оставьте это поле пустым.  Чтобы получить следующие значения, укажите `last_id` из ответа предыдущего запроса.  |
| `limit` | integer | ✓ | Количество значений на странице. |
| `sort_by` | SupplyOrderListRequestSortByEnum | ✓ | Параметр, по которому заявки на поставку будут отсортированы:  - `ORDER_CREATION` — по дате создания заявки;  - `ORDER_STATE_UPDATED_AT` — по обновлению статуса заявки;  - `TIMESLOT_FROM_UTC` — по таймслоту в UTC;  - `TIMESLOT_FROM_LOCAL` — по таймслоту в локальном времени.  |
| `sort_dir` | SupplyOrderListRequestSortDirEnum |  | Направление сортировки: - `ASC` — по возрастанию; - `DESC` — по убыванию.  |

[Request example](examples/POST__v3_supply_order_list_req.json)

## Responses

### `200` Список заявок на поставку


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `last_id` | string |  | Идентификатор последнего значения на странице.  Чтобы получить следующие значения, укажите полученное значение в следующем запросе в параметре `last_id`.  |
| `order_ids` | array |  | Идентификаторы заявок на поставку. |

[Response 200](../_shared/examples/POST__v3_supply_order_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
