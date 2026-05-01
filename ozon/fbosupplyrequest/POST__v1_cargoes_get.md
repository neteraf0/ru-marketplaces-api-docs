# `POST` /v1/cargoes/get

**Tag:** [FboSupplyRequest](index.md)

**operationId:** `CargoesGet`

**Получить информацию о грузоместах**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `supply_ids` | array | ✓ | Список идентификаторов поставок в заявке. |
## Responses

### `200` Информация о грузоместах


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `supply` | array |  | Информация о грузоместах. |

[Response 200](../_shared/examples/POST__v1_cargoes_get_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
