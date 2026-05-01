# `POST` /v1/businesses/{businessId}/operations

**Tag:** [laas](index.md)

**operationId:** `getOperations`

**Получение статусов операций**

{% include notitle [access](../../_auto/method_scopes/getOperations.md) %}

Возвращает статусы запущенных операций по их идентификаторам.

{% include notitle [limit](../../_auto/method_limits/getOperations.md) %}

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `businessId` | path | integer | ✓ | Идентификатор кабинета. Чтобы его узнать, воспользуйтесь запросом [GET v2/campaigns](../../reference/campaigns/getCampaigns.md).  ℹ️ [Что такое кабинет и магазин на Маркете](https://yandex.ru/support/marketplace/account/introduction.html)  |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `operationType` | string (enum: ORDER_RECIPIENT_UPDATE, ORDER_DELIVERY_INTERVAL_UPDATE, ORDER_STATUS_UPDATE, RETURN_CANCELLATION) | ✓ | Тип операции:  * `ORDER_RECIPIENT_UPDATE` — изменение данных получателя.  * `ORDER_DELIVERY_INTERVAL_UPDATE` — изменение интервала дат доставки.  * `ORDER_STATUS_UPDATE` — обновление статуса заказа для его отмены.  * `RETURN_CANCELLATION` — отмена возврата.  |
| `operationIds` | array | ✓ | Список идентификаторов операций.  |
## Responses

### `200` Информация об операциях.


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 200](../_shared/examples/POST__v1_businesses__businessId__operations_200.json)

### `400` Запрос содержит неправильные данные. [Подробнее об ошибке](../../concepts/error-codes.md#400)


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 400](../_shared/examples/POST__v2_businesses__businessId__settings_400.json)

### `401` В запросе не указаны данные для авторизации. [Подробнее об ошибке](../../concepts/error-codes.md#401)


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 401](../_shared/examples/POST__v2_businesses__businessId__settings_400.json)

### `403` Данные для авторизации неверны или доступ к ресурсу запрещен. [Подробнее об ошибке](../../concepts/error-codes.md#403)


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 403](../_shared/examples/POST__v2_businesses__businessId__settings_400.json)

### `420` Превышено ограничение на доступ к ресурсу. [Подробнее об ошибке](../../concepts/error-codes.md#420)


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 420](../_shared/examples/POST__v2_businesses__businessId__settings_400.json)

### `500` Внутренняя ошибка Маркета. [Подробнее об ошибке](../../concepts/error-codes.md#500)


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 500](../_shared/examples/POST__v2_businesses__businessId__settings_400.json)
