# `GET` /v1/cargoes-label/file/{file_guid}

**Tag:** [FboSupplyRequest](index.md)

**operationId:** `CargoesAPI_CargoesLabelFile`

**Получить PDF с этикетками грузовых мест**


  10 апреля 2026 года отключим метод. Переключитесь на /v1/cargoes-label/get.


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Responses

- **200** Этикетки грузовых мест
### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
