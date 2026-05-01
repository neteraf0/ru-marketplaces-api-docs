# `POST` /v1/cargoes/delete

**Tag:** [FboSupplyRequest](index.md)

**operationId:** `CargoesAPI_CargoesDelete`

**Удалить грузоместо в заявке на поставку**

Метод для удаления грузомест в заявке на поставку.

Чтобы проверить статус удаления, используйте метод [/v1/cargoes/delete/status](#operation/CargoesAPI_CargoesDeleteStatus).

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `cargo_ids` | array | ✓ | Список идентификаторов грузомест, которые нужно удалить.  Максимум 70 значений.  |
| `supply_id` | integer | ✓ | Идентификатор поставки. |
## Responses

### `200` Грузоместо удалено


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `errors` | v1CargoesDeleteResponseError |  | Список ошибок, которые возникли при удалении грузомест. |
| `operation_id` | string |  | Идентификатор операции. |

[Response 200](../_shared/examples/POST__v1_cargoes_delete_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
