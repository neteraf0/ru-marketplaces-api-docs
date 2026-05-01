# `POST` /v1/cargoes-label/get

**Tag:** [FboSupplyRequest](index.md)

**operationId:** `CargoesAPI_CargoesLabelGet`

**Получить идентификатор этикетки для грузомест**

Возвращает статус формирования этикеток и ссылку на PDF-файл с ними.

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

### `200` Этикетка для грузомест


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | v1CargoesLabelGetResponseResult |  | Информация об этикетках. |
| `status` | v1CargoesLabelGetResponseStatus |  | Статус формирования этикеток: - `SUCCESS` — готовы. - `IN_PROGRESS` — формируются. - `FAILED` — ошибка при формировании.  |
| `errors` | v1CargoesLabelCreateErrors |  | Ошибки. |

[Response 200](../_shared/examples/POST__v1_cargoes_label_get_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
