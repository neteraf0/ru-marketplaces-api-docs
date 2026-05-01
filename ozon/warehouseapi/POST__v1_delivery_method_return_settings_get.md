# `POST` /v1/delivery-method/return/settings/get

**Tag:** [WarehouseAPI](index.md)

**operationId:** `GetDeliveryMethodReturnSettingsV1`

**Получить информацию по возвратным настройкам rFBS и rFBS Express**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `delivery_method_id` | integer | ✓ | Идентификатор способа доставки. Получите значение параметра методом [/v2/delivery-method/list](#operation/WarehouseAPI_DeliveryMethodListV2). |
## Responses

### `200` Информация получена


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `settings` | GetDeliveryMethodReturnSettingsV1ResponseReturnSetting |  | Информация о возвратных настройках. |

[Response 200](../_shared/examples/POST__v1_delivery_method_return_settings_get_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
