# `POST` /v1/draft/create

**Tag:** [FboSupplyRequest](index.md)

**operationId:** `SupplyDraftAPI_DraftCreate`

**Создать черновик заявки на поставку**


Метод устаревает и будет отключён 16 марта 2026 года. Используйте /v1/draft/crossdock/create, /v1/draft/direct/create или /v1/draft/multi-cluster/create.


Черновик заявки на поставку доступен 30 минут.

Вы можете создавать черновики заявки на поставку 2 раза в минуту и 50 раз в час.
Максимум — 500 черновиков в день.

Если превысите лимит, вернётся ошибка 429.

Создать черновик заявки на поставку — прямой или кросс-докинг, а также указать поставляемые товары.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `cluster_ids` | array |  | Идентификаторы кластеров для поставки. Получите методом [/v1/cluster/list](#operation/SupplyDraftAPI_DraftClusterList). |
| `drop_off_point_warehouse_id` | integer |  | Идентификатор точки отгрузки — пункта выдачи заказов или сортировочного центра. Можно получить с помощью метода [/v1/warehouse/fbo/list](#operation/SupplyDraftAPI_DraftGetWarehouseFboList). Только для типа поставки `type = CREATE_TYPE_CROSSDOCK`.  |
| `items` | array | ✓ | Товары. |
| `type` | v1CreateType | ✓ | Тип поставки: - `CREATE_TYPE_CROSSDOCK` — кросс-докинг, - `CREATE_TYPE_DIRECT` — прямая.  |
## Responses

### `200` Черновик заявки создан


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `operation_id` | string |  | Идентификатор черновика заявки на поставку. |

[Response 200](../_shared/examples/POST__v1_warehouse_archive_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
