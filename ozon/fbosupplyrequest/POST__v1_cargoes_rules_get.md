# `POST` /v1/cargoes/rules/get

**Tag:** [FboSupplyRequest](index.md)

**operationId:** `CargoesAPI_CargoesRulesGet`

**Чек-лист по установке грузомест FBO**

Метод для получения чек-листа с правилами по установке грузомест.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `supply_ids` | array | ✓ | Список идентификаторов поставок в заявке.  Максимум 100 идентификаторов.  |
## Responses

### `200` Чек-лист по установке грузомест


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `supply_check_lists` | array |  | Список чек-листов с правилами заполнения грузомест по поставкам. |

[Response 200](../_shared/examples/POST__v1_cargoes_rules_get_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
