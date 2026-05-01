# `POST` /v1/returns/settings/utilization/info

**Tag:** [ReturnsAPI](index.md)

**operationId:** `UtilizationInfo`

**Получить настройки автоутилизации**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Responses

### `200` Настройки автоутилизации


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `min_price` | minUtilizationMoney |  | Минимальная цена товара, с которой можно установить автоутилизацию методом [/v1/returns/settings/utilization/update](#operation/UtilizationUpdate). |
| `utilization_settings` | ReturnsSettingsUtilizationInfoResponseUtilizationSettings |  | Настройки утилизации. |

[Response 200](../_shared/examples/POST__v1_returns_settings_utilization_info_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
