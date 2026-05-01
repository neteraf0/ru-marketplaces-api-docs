# `POST` /v1/returns/settings/utilization/update

**Tag:** [ReturnsAPI](index.md)

**operationId:** `UtilizationUpdate`

**Обновить настройки автоутилизации**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `utilization_price` | ReturnsSettingsUtilizationUpdateRequestUtilizationPrice | ✓ | Максимальная цена автоутилизации для товаров без дефектов. |
| `utilization_price_defects` | ReturnsSettingsUtilizationUpdateRequestUtilizationPriceDefects | ✓ | Максимальная цена автоутилизации для товаров с дефектами. |
## Responses

- **200** Настройки обновлены
### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
