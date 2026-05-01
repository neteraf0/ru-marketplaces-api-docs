# `POST` /v1/supply-order/details

**Tag:** [FBO](index.md)

**operationId:** `SupplyOrderAPI_SupplyOrderDetails`

**Получить подробную информацию о заявке на поставку**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `order_id` | integer | ✓ | Идентификатор заявки на поставку. |
## Responses

### `200` Подробная информация о заявке


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `created_date` | string |  | Дата создания заявки на поставку. |
| `data_filling_deadline_utc` | string |  | Время в секундах, оставшееся на заполнение данных по поставке. Только для заявок с вРЦ. |
| `dropoff_warehouse_id` | integer |  | Идентификатор пункта отгрузки. |
| `order_id` | integer |  | Идентификатор заявки на поставку. |
| `order_number` | string |  | Номер заявки на поставку. |
| `order_tags` | SupplyOrderDetailsResponseOrderTags |  | Метки заявки на поставку. |
| `state` | SupplyOrderDetailsResponseOrderStateEnum |  | Статус заявки на поставку: - `UNSPECIFIED` — не определён; - `DATA_FILLING` — заполнение данных; - `READY_TO_SUPPLY` — готова к отгрузке; - `ACCEPTED_AT_SUPPLY_WAREHOUSE` — принята на точке отгрузки; - `IN_TRANSIT` — в пути; - `ACCEPTANCE_AT_STORAGE_WAREHOUSE` — приёмка на складе; - `REPORTS_CONFIRMATION_AWAITING` — согласование актов; - `REPORT_REJECTED` — спор; - `COMPLETED` — завершена; - `REJECTED_AT_SUPPLY_WAREHOUSE` — отказано в приемке; - `CANCELLED` — отменена; - `OVERDUE` — просрочена.  |
| `state_updated_date` | string |  | Дата обновления статуса заявки на поставку. |
| `supplies` | array |  | Информация о поставках. |
| `timeslot` | v1SupplyOrderDetailsResponseTimeslot |  | Информация о таймслоте. |
| `vehicle` | SupplyOrderDetailsResponseVehicle |  | Информация о водителе и машине. |

[Response 200](../_shared/examples/POST__v1_supply_order_details_200.json)

### `400` Неверный параметр


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 400](../_shared/examples/POST__v1_roles_default.json)

### `403` Доступ запрещён


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 403](../_shared/examples/POST__v1_roles_default.json)

### `404` Ответ не найден


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 404](../_shared/examples/POST__v1_roles_default.json)

### `409` Конфликт запроса


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 409](../_shared/examples/POST__v1_roles_default.json)

### `500` Внутренняя ошибка сервера


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 500](../_shared/examples/POST__v1_roles_default.json)
