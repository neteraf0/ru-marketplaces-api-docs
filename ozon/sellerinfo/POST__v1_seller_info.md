# `POST` /v1/seller/info

**Tag:** [SellerInfo](index.md)

**operationId:** `SellerAPI_SellerInfo`

**Информация о кабинете продавца**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Responses

### `200` Информация о кабинете продавца


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `company` | SellerInfoResponseCompany |  | Компания. |
| `ratings` | array |  | Список рейтингов. |
| `subscription` | SellerInfoResponseSubscription |  | Подписка. |

[Response 200](../_shared/examples/POST__v1_seller_info_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
