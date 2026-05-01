# `POST` /v1/cargoes/create/info

**Tag:** [FboSupplyRequest](index.md)

**operationId:** `CargoesAPI_CargoesCreateInfo`

**Получить информацию по установке грузомест**


7 ноября 2025 года метод будет отключён. Переключитесь на /v2/cargoes/create/info.


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `operation_id` | string | ✓ | Идентификатор операции. |
## Responses

### `200` Результат запроса


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | CargoesCreateInfoResponseResult |  | Результат запроса. |
| `status` | v1CargoesCreateInfoResponseStatus |  | Статус формирования грузомест:   - `SUCCESS` — успешно.   - `IN_PROGRESS` — формируются.   - `FAILED` — при формировании грузомест произошла ошибка.  |
| `errors` | v1CargoesCreateErrors |  | Ошибки. |

[Response 200](../_shared/examples/POST__v1_cargoes_create_info_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
