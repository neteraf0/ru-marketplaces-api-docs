# `POST` /v1/returns/settings/utilization/history

**Tag:** [ReturnsAPI](index.md)

**operationId:** `UtilizationHistory`

**Получить историю изменений автоутилизации**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Responses

### `200` История изменений


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `history` | array |  | История изменений. |

[Response 200](../_shared/examples/POST__v1_returns_settings_utilization_history_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
