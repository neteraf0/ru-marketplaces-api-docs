# `POST` /v1/warehouse/fbo/list

**Tag:** [FboSupplyRequest](index.md)

**operationId:** `SupplyDraftAPI_DraftGetWarehouseFboList`

**Поиск точек для отгрузки поставки**

Используйте метод, чтобы найти точки отгрузки для кросс-докинга и прямых поставок.

Вы можете посмотреть адреса всех точек на карте и в виде таблицы в [Базе знаний](https://seller-edu.ozon.ru/fbo/warehouses/adresa-skladov-fbo).

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `filter_by_supply_type` | array | ✓ | Тип поставки: - `CREATE_TYPE_CROSSDOCK` — кросс-докинг, - `CREATE_TYPE_DIRECT` — прямая.  |
| `search` | string | ✓ | Поиск по названию склада. Для поиска пунктов выдачи заказов укажите полное название. |
## Responses

### `200` Информация о складах


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `search` | array |  | Результат поиска складов. |

[Response 200](../_shared/examples/POST__v1_warehouse_fbo_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
