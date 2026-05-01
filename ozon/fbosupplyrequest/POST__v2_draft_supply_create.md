# `POST` /v2/draft/supply/create

**Tag:** [FboSupplyRequest](index.md)

**operationId:** `DraftSupplyCreate`

**Создать заявку на поставку по черновику**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `draft_id` | integer | ✓ | Идентификатор черновика из метода [/v2/draft/create/info](#operation/DraftCreateInfo). |
| `selected_cluster_warehouses` | array | ✓ | Информация о кластере и складах в нём. Можно передать один кластер для кросс-докинговой и прямой поставки или список всех кластеров для поставки в несколько кластеров. |
| `timeslot` | v2DraftSupplyCreateRequestTimeslot |  | Таймслот поставки. |
| `supply_type` | string (enum: CROSSDOCK, DIRECT, MULTI_CLUSTER) | ✓ | Тип поставки: - `CROSSDOCK` — кросс-докинг; - `DIRECT` — прямая; - `MULTI_CLUSTER` — для нескольких кластеров.  |
## Responses

### `200` Заявка создана


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `draft_id` | integer |  | Идентификатор черновика. |
| `error_reasons` | array |  | Причина ошибки:  - `UNSPECIFIED` — не определена;  - `SOME_SERVICE_ERROR` — ошибка при редактировании поставки;  - `ORDER_SKU_LIMIT` — количество товаров в поставке больше 5000;  - `INVALID_QUANTITY_OR_QUANT` —  некорректное количество товара или грузомест;  - `ORDER_ALREADY_CREATED` — заказ уже создан;  - `ORDER_CREATION_IN_PROGRESS` — создание заказа в процессе;  - `DRAFT_DOES_NOT_EXIST` — черновик не существует;  - `CONTRACTOR_CAN_NOT_CREATE_ORDER` — контрагент не может создать заказ;  - `INACTIVE_CONTRACT` — нельзя редактировать состав поставки с неактивным договором;  - `DRAFT_INCORRECT_STATE` — некорректный статус черновика;  - `INVALID_VOLUME` — некорректный объём поставки;  - `INVALID_ROUTE` — некорректный маршрут;  - `INVALID_STORAGE_WAREHOUSE` — некорректный склад хранения;  - `INVALID_STORAGE_REGION` — некорректный регион хранения;  - `INVALID_SPLITTING` — некорректное разделение;  - `INVALID_SUPPLY_CONTENT` — некорректное содержимое поставки;  - `TIMESLOT_NOT_AVAILABLE` — нет доступных таймслотов;  - `SKU_DISTRIBUTION_REQUIRED_BUT_NOT_POSSIBLE` — требуется распределение SKU, но оно невозможно;  - `XDOCK_IN_DELIVERY_POINT_DISABLED_FOR_SELLER` — поставка кросс-докингом через пункт выдачи заказов недоступна для продавца;  - `DRAFT_IS_LOCKED` — черновик заблокирован;  - `INVALID_PACKAGE_UNITS_COUNTS` — некорректное количество грузомест;  - `SELLER_CONVERSATION_DOES_NOT_EXIST` — точка отгрузки с таким `id` не существует;  - `USER_CAN_NOT_CREATE_SELLER_CONVERSATION` — пользователь не может создать диалог с продавцом;  - `SKU_WITH_ETTN_REQUIRED_TAG_NOT_ALLOWED_FOR_DROP_OFF_POINT` — товар с меткой `is_ettn_required` не разрешён для точки отгрузки;  - `INVALID_SELLER_WAREHOUSE` — склад продавца недоступен;  - `PICKUP_ORDER_LIMIT_EXCEEDED` — превышен лимит заказов на самовывоз;  - `MINIMUM_VOLUME_IN_LITRES_INVALID` — некорректный минимальный объём в литрах;  - `INVALID_CLUSTERS_COUNT` — переданы не все кластеры из расчёта;  - `CAN_NOT_CREATE_ORDER` — не удалось создать заказ;  - `UNDEFINED` — неизвестная ошибка.  |

[Response 200](../_shared/examples/POST__v2_draft_supply_create_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
