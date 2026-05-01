# `POST` /v1/cargoes/delete/status

**Tag:** [FboSupplyRequest](index.md)

**operationId:** `CargoesAPI_CargoesDeleteStatus`

**Информация о статусе удаления грузоместа**

Метод для получения статуса удаления грузомест в заявке на поставку.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `operation_id` | string | ✓ | Идентификатор операции. |
## Responses

### `200` Статус удаления грузоместа


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `errors` | v1CargoesDeleteStatusResponseError |  | Список ошибок, которые возникли при удалении грузомест. |
| `status` | CargoesDeleteStatusResponseStatusEnum |  | Статус удаления грузоместа.  Возможные статусы: - `SUCCESS` — грузоместо удалено, - `IN_PROGRESS` — грузоместо в процессе удаления, - `ERROR` — возникла ошибка при удалении грузоместа.  |

[Response 200](../_shared/examples/POST__v1_cargoes_delete_status_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
