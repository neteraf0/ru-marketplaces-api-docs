# `POST` /v1/seller/ozon-logistics/info

**Tag:** [SellerInfo](index.md)

**operationId:** `SellerAPI_SellerOzonLogisticsInfo`

**Информация о подключении Ozon Доставки**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Responses

### `200` Информация о подключении Ozon Доставки


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `available_schemas` | array |  | Тип доступной схемы: - `UNKNOWN` — не определён, - `FBO`, - `FBS`.  |
| `ozon_logistics_enabled` | boolean |  | `true`, если Ozon Доставка подключена.  |

[Response 200](../_shared/examples/POST__v1_seller_ozon_logistics_info_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
