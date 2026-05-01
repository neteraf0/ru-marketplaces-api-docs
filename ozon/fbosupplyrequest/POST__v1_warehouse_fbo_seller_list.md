# `POST` /v1/warehouse/fbo/seller/list

**Tag:** [FboSupplyRequest](index.md)

**operationId:** `WarehouseFboSellerList`

**Получить список складов продавца**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Responses

### `200` Список складов


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `warehouses` | array |  | Список складов продавца. |

[Response 200](../_shared/examples/POST__v1_warehouse_fbo_seller_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
