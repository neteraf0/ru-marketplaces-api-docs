# `POST` /v2/campaigns/{campaignId}/orders/status-update

**Tag:** [orders](index.md)

**operationId:** `updateOrderStatuses`

**Изменение статусов нескольких заказов**

{% include notitle [access](../../_auto/method_scopes/updateOrderStatuses.md) %}

Изменяет статусы нескольких заказов.

Возможные изменения статусов:

* Если магазин подтвердил и подготовил заказ к отправке, то заказ из статуса `"status": "PROCESSING"`и этапа обработки `"substatus": "STARTED"` нужно перевести в статус `"status": "PROCESSING"` и этап обработки `"substatus": "READY_TO_SHIP"`.
* Если магазин подтвердил заказ, но не может его выполнить (например, товар числится в базе, но отсутствует на складе или нет нужного цвета), то заказ из статуса `"status": "PROCESSING"` и этапа обработки `"substatus": "STARTED"` нужно перевести в статус `"status": "CANCELLED"` с причиной отмены заказа `"substatus": "SHOP_FAILED"`.
* Если магазин подготовил заказ к отгрузке, но не может его выполнить (например, последний товар был поврежден или оказался с браком), то заказ из статуса `"status": "PROCESSING"` и этапа обработки `"substatus": "READY_TO_SHIP"` нужно перевести в статус `"status": "CANCELLED"` с причиной отмены заказа `"substatus": "SHOP_FAILED"`.

Полная информация о статусной модели DBS-заказов: [Как изменяются статусы заказов](../../concepts/dbs-order-status-model.md).

{% cut "**Как подтвердить LaaS-заказ**" %}

Для подтверждения черновика заказа передайте статус `"status": "PROCESSING"` с подстатусом `"substatus": "STARTED"`.

Подтверждение заказа, созданного с параметром `draft` равным `false`, не требуется.

{% endcut %}

{% cut "**Как отменить LaaS-заказ**" %}

Передайте статус `"status": "CANCELLED"` с причиной отмены заказа `"substatus": "SHOP_FAILED"`.

При успешном выполнении запроса отмена произойдет через некоторое время. [Как проверить статус операции](../../reference/operations/getOperations.md)

{% endcut %}

{% include notitle [limit](../../_auto/method_limits/updateOrderStatuses.md) %}

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `campaignId` | path | integer | ✓ | Идентификатор кампании (магазина) — технический идентификатор, который представляет ваш магазин в системе Яндекс Маркета при работе через API. Он однозначно связывается с вашим магазином, но предназначен только для автоматизированного взаимодействия.  Его можно узнать с помощью запроса [GET v2/campaigns](../../reference/campaigns/getCampaigns.md) или найти в кабинете продавца на Маркете. Нажмите на иконку вашего аккаунта → **Настройки** и в меню слева выберите **API и модули**:  * блок **Идентификатор кампании**; * вкладка **Лог запросов** → выпадающий список в блоке **Показывать логи**.  ⚠️ Не путайте его с: - идентификатором магазина, который отображается в личном кабинете продавца; - рекламными кампаниями.  |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `orders` | array | ✓ | Список заказов. |
## Responses

### `200` Возвращается информация об обновленных статусах заказов.


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 200](../_shared/examples/POST__v2_campaigns__campaignId__orders_status_update_200.json)

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

### `404` Запрашиваемый ресурс не найден. [Подробнее об ошибке](../../concepts/error-codes.md#404)


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 404](../_shared/examples/POST__v2_businesses__businessId__settings_400.json)

### `420` Превышено ограничение на доступ к ресурсу. [Подробнее об ошибке](../../concepts/error-codes.md#420)


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 420](../_shared/examples/POST__v2_businesses__businessId__settings_400.json)

### `500` Внутренняя ошибка Маркета. [Подробнее об ошибке](../../concepts/error-codes.md#500)


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 500](../_shared/examples/POST__v2_businesses__businessId__settings_400.json)
