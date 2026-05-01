# `POST` /v1/product/action/timer/update

**Tag:** [Prices&StocksAPI](index.md)

**operationId:** `ProductAPI_ActionTimerUpdate`

**Обновление таймера актуальности минимальной цены**

Минимальная цена действует 30 дней после установки.
После этого настройка выключается. Вы можете продлить её: вызовите метод повторно и укажите `product_ids`.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `product_ids` | array |  | Список идентификаторов товаров в системе Ozon — `product_id`. *Example: `[1234567890]`* |

[Request example](examples/POST__v1_product_action_timer_update_req.json)

## Responses

- **200** Обновлено
### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
