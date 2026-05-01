# `GET` /v2/campaigns/{campaignId}/returns

**Tag:** [express](index.md)

**operationId:** `getReturns`

**Список невыкупов и возвратов**

{% include notitle [access](../../_auto/method_scopes/getReturns.md) %}

Получает список невыкупов и возвратов.

Чтобы получить информацию по одному невыкупу или возврату, выполните запрос [GET v2/campaigns/{campaignId}/orders/{orderId}/returns/{returnId}](../../reference/orders/getReturn.md).

{% note tip "Подключите API-уведомления" %}

Маркет отправит вам запрос [POST notification](../../push-notifications/reference/sendNotification.md), когда появится новый невыкуп или возврат.

[{#T}](../../push-notifications/index.md)

{% endnote %}

{% include notitle [limit](../../_auto/method_limits/getReturns.md) %}

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `campaignId` | path | integer | ✓ | Идентификатор кампании (магазина) — технический идентификатор, который представляет ваш магазин в системе Яндекс Маркета при работе через API. Он однозначно связывается с вашим магазином, но предназначен только для автоматизированного взаимодействия.  Его можно узнать с помощью запроса [GET v2/campaigns](../../reference/campaigns/getCampaigns.md) или найти в кабинете продавца на Маркете. Нажмите на иконку вашего аккаунта → **Настройки** и в меню слева выберите **API и модули**:  * блок **Идентификатор кампании**; * вкладка **Лог запросов** → выпадающий список в блоке **Показывать логи**.  ⚠️ Не путайте его с: - идентификатором магазина, который отображается в личном кабинете продавца; - рекламными кампаниями.  |
| `pageToken` | query | string |  | Идентификатор страницы c результатами.  Если параметр не указан, возвращается первая страница.  Передавайте значение выходного параметра `nextPageToken`, полученное при последнем запросе.  |
| `limit` | query | integer |  |   |
| `orderIds` | query | array |  | Идентификаторы заказов — для фильтрации результатов.  Несколько идентификаторов перечисляются через запятую без пробела.  |
| `statuses` | query | array |  | Фильтр по статусам возврата денег за возвраты.  Несколько статусов перечисляются через запятую.  *Example: `['STARTED_BY_USER', 'WAITING_FOR_DECISION']`* |
| `shipmentStatuses` | query | array |  | Фильтр по логистическим статусам невыкупов и возвратов.  Несколько статусов перечисляются через запятую.  *Example: `['READY_FOR_PICKUP', 'IN_TRANSIT']`* |
| `type` | query | string (enum: UNREDEEMED, RETURN) |  | Тип заказа для фильтрации:  * `UNREDEEMED` — невыкуп.  * `RETURN` — возврат.  Если не указать, в ответе будут и невыкупы, и возвраты.  |
| `fromDate` | query | string |  | Начальная дата для фильтрации невыкупов или возвратов по дате обновления.  Формат: `ГГГГ-ММ-ДД`.  *Example: `2022-10-31`* |
| `toDate` | query | string |  | Конечная дата для фильтрации невыкупов или возвратов по дате обновления.  Формат: `ГГГГ-ММ-ДД`.  *Example: `2022-11-30`* |
| `from_date` | query | string |  | {% note warning "Вместо него используйте `fromDate`." %}     {% endnote %}  Начальная дата для фильтрации невыкупов или возвратов по дате обновления.  *Example: `2022-10-31`* |
| `to_date` | query | string |  | {% note warning "Вместо него используйте `toDate`." %}     {% endnote %}  Конечная дата для фильтрации невыкупов или возвратов по дате обновления.  *Example: `2022-11-30`* |

## Responses

### `200` Постраничные невыкупы или возвраты магазина.


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 200](../_shared/examples/GET__v2_campaigns__campaignId__returns_200.json)

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
