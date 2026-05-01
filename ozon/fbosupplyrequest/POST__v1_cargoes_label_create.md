# `POST` /v1/cargoes-label/create

**Tag:** [FboSupplyRequest](index.md)

**operationId:** `CargoesAPI_CargoesLabelCreate`

**Сгенерировать этикетки для грузомест**

Используйте метод, чтобы сгенерировать этикетки для грузомест из заявки на поставку.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `cargoes` | array |  | Информация о грузоместах. |
| `supply_id` | integer | ✓ | Идентификатор поставки. |
## Responses

### `200` Результат запроса


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `operation_id` | string |  | Идентификатор операции. |
| `errors` | v1CargoesLabelCreateErrors |  | Ошибки. |

[Response 200](../_shared/examples/POST__v1_cargoes_label_create_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
