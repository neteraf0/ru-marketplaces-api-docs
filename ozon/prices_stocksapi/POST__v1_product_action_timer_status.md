# `POST` /v1/product/action/timer/status

**Tag:** [Prices&StocksAPI](index.md)

**operationId:** `ProductAPI_ActionTimerStatus`

**Получить статус установленного таймера**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `product_ids` |  |  | Список идентификаторов товаров в системе Ozon — `product_id`. |
## Responses

### `200` Статусы


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `statuses` |  |  |  |

[Response 200](../_shared/examples/POST__v1_product_action_timer_status_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
