# `PUT` /v2/campaigns/{campaignId}/orders/{orderId}/items

**Tag:** [dbs](index.md)

**operationId:** `updateOrderItems`

**Удаление товаров из заказа или уменьшение их числа**

{% include notitle [access](../../_auto/method_scopes/updateOrderItems.md) %}

{% note warning "Если вы работаете по модели FBS" %}

Используйте метод [PUT v2/campaigns/{campaignId}/orders/{orderId}/boxes](../../reference/orders/setOrderBoxLayout.md).

{% endnote %}

Удаляет один или несколько товаров из заказа, если магазин не может поставить их все.

Заказ должен находится в статусе `"status": "PROCESSING"` этапа обработки `"substatus": "STARTED"`. Изменить состав нельзя после передачи статуса `"substatus": "READY_TO_SHIP"`.

{% cut "Уменьшить количество одинаковых товаров" %}

Передайте обновленное значение в параметре `count`.

{% endcut %}

{% cut "Удалить товар из заказа" %}

Передайте значение `0` в параметре `count` или не передавайте `item`.

{% endcut %}

Нельзя удалить или уменьшить количество товара, если он:

* добавлен по акции;
* составляет 99% стоимости заказа;
* единственный товар в заказе.

В таком случае отмените заказ — в методе [PUT v2/campaigns/{campaignId}/orders/{orderId}/status](../../reference/orders/updateOrderStatus.md) передайте статус заказа `CANCELLED` с причиной отмены `SHOP_FAILED`.

### Как вернутся деньги {#money}

  Если покупатель оплатил товар при оформлении, Маркет вернет ему деньги за удаленные из заказа товары в течение двух дней:

  * при оплате банковской картой — с момента, когда магазин переведет заказ в статус `SHIPPED`;

  * при оплате через :no-translate[Apple Pay] или :no-translate[Google Pay] — с момента, когда магазин удалит товар из заказа.

{% endcut %}

{% include notitle [limit](../../_auto/method_limits/updateOrderItems.md) %}

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `campaignId` | path | integer | ✓ | Идентификатор кампании (магазина) — технический идентификатор, который представляет ваш магазин в системе Яндекс Маркета при работе через API. Он однозначно связывается с вашим магазином, но предназначен только для автоматизированного взаимодействия.  Его можно узнать с помощью запроса [GET v2/campaigns](../../reference/campaigns/getCampaigns.md) или найти в кабинете продавца на Маркете. Нажмите на иконку вашего аккаунта → **Настройки** и в меню слева выберите **API и модули**:  * блок **Идентификатор кампании**; * вкладка **Лог запросов** → выпадающий список в блоке **Показывать логи**.  ⚠️ Не путайте его с: - идентификатором магазина, который отображается в личном кабинете продавца; - рекламными кампаниями.  |
| `orderId` | path | integer | ✓ | Идентификатор заказа. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `items` | array | ✓ | Список товаров в заказе.  Если магазин не передал информацию о товаре во входных данных, он будет удален из заказа.  Обязательный параметр.  |
| `reason` | string (enum: PARTNER_REQUESTED_REMOVE, USER_REQUESTED_REMOVE) |  | Причина, почему обновился состав заказа:  * `PARTNER_REQUESTED_REMOVE` — магазин удалил товар. * `USER_REQUESTED_REMOVE` — покупатель попросил удалить товар.  |
## Responses

- **200** Маркет успешно обработал ваш запрос. Выходные данные не ожидаются.
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
