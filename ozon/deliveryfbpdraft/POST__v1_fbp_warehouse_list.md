# `POST` /v1/fbp/warehouse/list

**Tag:** [DeliveryFBPDraft](index.md)

**operationId:** `FbpWarehouseList`

**Получить список партнёрских складов**

Вы можете оставить обратную связь о работе метода в [комментариях](https://dev.ozon.ru/community/1700-FBP-metody/) в сообществе разработчиков Ozon for dev.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Responses

### `200` Список партнёрских складов


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `warehouses` | array |  | Список складов. |

[Response 200](../_shared/examples/POST__v1_fbp_warehouse_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
