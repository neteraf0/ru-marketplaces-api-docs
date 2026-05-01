# `GET` /v2/campaigns/{campaignId}/first-mile/shipments/{shipmentId}/act

**Tag:** [shipments](index.md)

**operationId:** `downloadShipmentAct`

**Получение акта приема-передачи**

{% include notitle [access](../../_auto/method_scopes/downloadShipmentAct.md) %}

{% note warning "Экспресс‑доставка" %}

Если ваш магазин подключен к экспресс‑доставке и вы отгружаете заказы курьерам [Яндекс Go](https://go.yandex/), подготавливать акт приема‑передачи не нужно.

{% endnote %}

Запрос формирует акт приема-передачи заказов, входящих в отгрузку, и возвращает акт в формате PDF. В акте содержатся собранные и готовые к отправке заказы.

Метод доступен только для подтвержденной отгрузки. Сначала подтвердите отгрузку запросом [POST v2/campaigns/{campaignId}/shipments/{shipmentId}/confirm](../../reference/shipments/confirmShipment.md), затем вызовите этот метод.

При формировании акта Маркет автоматически находит и подставляет в шаблон следующие данные:

{% cut "Данные, из которых Маркет формирует акт" %}

#|
|| **Данные в акте**                                         | **Описание**                                                                                                                                                                                                                                                         ||
|| Дата                                                      | Дата запроса.                                                                                                                                                                                                                                                        ||
|| Отправитель                                               | Название вашего юридического лица, указанное в кабинете продавца на Маркете.                                                                                                                                                                                         ||
|| Исполнитель                                               | Название юридического лица сортировочного центра или службы доставки.                                                                                                                                                                                                ||
|| № отправления в системе заказчика                         | Внешний идентификатор заказа продавца, который можно передать запросом [POST v2/campaigns/{campaignId}/orders/{orderId}/external-id](../../reference/orders/updateExternalOrderId.md).                                                                            ||
|| № отправления в системе исполнителя (субподрядчика)       |
  Идентификатор заказа на Маркете, как в выходных данных запроса:

  * [POST v1/businesses/{businessId}/orders](../../reference/orders/getBusinessOrders.md).||

|| Объявленная ценность                                      |
  Общая сумма заказа без учета стоимости доставки, как в выходных данных запроса:

  * [POST v1/businesses/{businessId}/orders](../../reference/orders/getBusinessOrders.md).||

|| Вес                                                       |
  Масса брутто грузового места (суммарная масса упаковки и содержимого), как в выходных данных запроса:

  * [POST v1/businesses/{businessId}/orders](../../reference/orders/getBusinessOrders.md).||

|| Количество мест                                           |
  Количество грузовых мест в заказе, как в выходных данных запроса:

  * [POST v1/businesses/{businessId}/orders](../../reference/orders/getBusinessOrders.md). ||
|#

{% endcut %}

В распечатанном акте укажите отправителя и исполнителя. Они должны подписать акт и указать фамилию и инициалы рядом с подписью. При необходимости также заполните реквизиты доверенности.

{% include notitle [limit](../../_auto/method_limits/downloadShipmentAct.md) %}

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `campaignId` | path | integer | ✓ | Идентификатор кампании (магазина) — технический идентификатор, который представляет ваш магазин в системе Яндекс Маркета при работе через API. Он однозначно связывается с вашим магазином, но предназначен только для автоматизированного взаимодействия.  Его можно узнать с помощью запроса [GET v2/campaigns](../../reference/campaigns/getCampaigns.md) или найти в кабинете продавца на Маркете. Нажмите на иконку вашего аккаунта → **Настройки** и в меню слева выберите **API и модули**:  * блок **Идентификатор кампании**; * вкладка **Лог запросов** → выпадающий список в блоке **Показывать логи**.  ⚠️ Не путайте его с: - идентификатором магазина, который отображается в личном кабинете продавца; - рекламными кампаниями.  |
| `shipmentId` | path | integer | ✓ | Идентификатор отгрузки. |

## Responses

### `200` Акт приема-передачи для отгрузки в формате :no-translate[PDF].

`string`

[Response 200](../_shared/examples/GET__v2_campaigns__campaignId__orders__orderId__delivery_shipments__shipmentId.json)

### `400` Запрос содержит неправильные данные. [Подробнее об ошибках при работе с отгрузками](../../concepts/error-codes#shipments)


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
