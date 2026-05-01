# `POST` /v1/businesses/{businessId}/orders

**Tag:** [fby](index.md)

**operationId:** `getBusinessOrders`

**Информация о заказах в кабинете**

{% include notitle [access](../../_auto/method_scopes/getBusinessOrders.md) %}

Возвращает информацию о заказах в кабинете. Запрос можно использовать для отслеживания заказов и их статусов.

{% note tip "Вы также можете настроить API-уведомления" %}

Маркет отправит вам [запрос](../../push-notifications/reference/sendNotification.md), когда появится новый заказ или изменится его статус. А полную информацию можно получить с помощью этого метода.

[{#T}](../../push-notifications/index.md)

{% endnote %}

Доступна фильтрация по параметрам:

* дата оформления заказа;

* дата и время обновления заказа;

* дата отгрузки;

* статусы заказов (`statuses`);

* этапы обработки или причины отмены (`substatuses`);

* идентификаторы кампаний;

* идентификаторы заказов;

* внешние идентификаторы заказов;

* тип заказа (настоящий или тестовый);

* модели размещения;

* наличие запросов от покупателей на отмену заказа.

Максимальный диапазон дат за один запрос — 30 дней (передается в параметрах `fromDate` и `toDate`). Если их не передать, возвращается информация за последние 30 дней.

Результаты возвращаются постранично. Для навигации используйте параметры `page_token` и `limit`.

Получить более подробную информацию о покупателе и его номере телефона можно с помощью запроса [GET v2/campaigns/{campaignId}/orders/{orderId}/buyer](../../reference/orders/getOrderBuyerInfo.md).

{% include notitle [limit](../../_auto/method_limits/getBusinessOrders.md) %}

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `businessId` | path | integer | ✓ | Идентификатор кабинета. Чтобы его узнать, воспользуйтесь запросом [GET v2/campaigns](../../reference/campaigns/getCampaigns.md).  ℹ️ [Что такое кабинет и магазин на Маркете](https://yandex.ru/support/marketplace/account/introduction.html)  |
| `pageToken` | query | string |  | Идентификатор страницы c результатами.  Если параметр не указан, возвращается первая страница.  Передавайте значение выходного параметра `nextPageToken`, полученное при последнем запросе.  |
| `limit` | query | integer |  |   |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `orderIds` | array |  | Идентификаторы заказов. |
| `externalOrderIds` | array |  | Внешние идентификаторы заказов. |
| `programTypes` | array |  | Модели работы магазина на Маркете. |
| `campaignIds` | array |  | Идентификаторы кампаний магазинов. |
| `statuses` | array |  | Статусы заказов. |
| `substatuses` | array |  | Этапы обработки или причины отмены заказов. |
| `dates` | object |  | Фильтр по датам заказов. |
| `fake` | boolean |  | Тип заказа:  * `false` — настоящий заказ покупателя.  * `true` — [тестовый заказ](../../concepts/sandbox.md) Маркета.  |
| `waitingForCancellationApprove` | boolean |  | **Только для модели DBS**  Фильтр для получения заказов, по которым есть запросы на отмену.  При значении `true` возвращаются только те заказы, которые находятся в статусе `DELIVERY` или `PICKUP`, и пользователи решили их отменить.  |
| `sourcePlatforms` | array |  | Площадки-источники заказов. |
## Responses

### `200` Список заказов в кабинете.


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `orders` | array | ✓ | Список заказов в кабинете. |
| `paging` | object |  | Идентификатор следующей страницы.  |

[Response 200](../_shared/examples/POST__v1_businesses__businessId__orders_200.json)

### `400` Запрос содержит неправильные данные. [Подробнее об ошибках при работе с заказами](../../concepts/error-codes#orders)


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
