# `POST` /v1/campaigns/{campaignId}/returns/cancel

**Tag:** [returns](index.md)

**operationId:** `cancelReturn`

**Отмена возврата**

{% include notitle [access](../../_auto/method_scopes/cancelReturn.md) %}

Отменяет возврат.

Это можно сделать только до принятия в пункте выдачи (`"shipmentStatus": "CREATED"`).

{% note info "Возврат отменяется не мгновенно" %}

Отмена возврата применяется в течение нескольких минут и только в случае успешного завершения операции. [Как проверить статус операции](../../reference/operations/getOperations.md)

{% endnote %}

{% note tip "Используйте этот метод в подобных ситуациях" %}

Вы создали возврат, в котором указали 3 товара. Но покупатель передумал и решил вернуть только 2. Отмените возврат и создайте новый.

{% endnote %}

{% include notitle [limit](../../_auto/method_limits/cancelReturn.md) %}

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `campaignId` | path | integer | ✓ | Идентификатор кампании (магазина) — технический идентификатор, который представляет ваш магазин в системе Яндекс Маркета при работе через API. Он однозначно связывается с вашим магазином, но предназначен только для автоматизированного взаимодействия.  Его можно узнать с помощью запроса [GET v2/campaigns](../../reference/campaigns/getCampaigns.md) или найти в кабинете продавца на Маркете. Нажмите на иконку вашего аккаунта → **Настройки** и в меню слева выберите **API и модули**:  * блок **Идентификатор кампании**; * вкладка **Лог запросов** → выпадающий список в блоке **Показывать логи**.  ⚠️ Не путайте его с: - идентификатором магазина, который отображается в личном кабинете продавца; - рекламными кампаниями.  |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `returnId` | integer | ✓ | Идентификатор возврата. |
## Responses

### `200` Информация об операции по отмене возврата.

{% note warning "Ответ `200` не значит, что возврат отменен" %}

При успешном выполнении запроса это произойдет через некоторое время. [Как проверить статус операции](../../reference/operations/getOperations.md)

{% endnote %}


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 200](../_shared/examples/POST__v1_campaigns__campaignId__returns_cancel_200.json)

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
