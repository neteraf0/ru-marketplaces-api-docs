# `POST` /v2/campaigns/{campaignId}/orders/{orderId}/deliverDigitalGoods

**Tag:** [orders](index.md)

**operationId:** `provideOrderDigitalCodes`

**Передача ключей цифровых товаров**

{% include notitle [access](../../_auto/method_scopes/provideOrderDigitalCodes.md) %}

Передает ключи цифровых товаров, которые покупатель заказал и оплатил. После выполнения запроса Маркет отправит ему письмо с ключами и инструкциями по активации. Если письмо будет доставлено, Маркет переведет заказ в финальный статус `DELIVERED`.

{% note tip "После передачи кода покупателю статус заказа изменится не сразу" %}

Подключите API-уведомления — Маркет отправит вам запрос [POST notification](../../push-notifications/reference/sendNotification.md), когда заказ перейдет в статус `DELIVERED`.

[{#T}](../../push-notifications/index.md)

{% endnote %}

Ключ нужно передать в течение 30 минут после перехода заказа в статус `PROCESSING`.

Если в один заказ входят несколько ключей, передавайте их все в одном запросе.

Каждый товар с уникальным `id` передавайте в виде отдельного элемента в массиве `items`, а ключи товара — в массиве `codes`.

{% cut "Пример" %}

```json translate=no
{
  "items": [
    {
      "id": 1,
      "codes": [
        "code1", "code2", "code3"
      ],
      "slip": "slip",
      "activate_till": "2025-02-18"
    },
    {
      "id": 2,
      "codes": [
        "code4", "code5", "code6"
      ],
      "slip": "slip",
      "activate_till": "2025-02-18"
    }
  ]
}
```
{% endcut %}

{% include notitle [limit](../../_auto/method_limits/provideOrderDigitalCodes.md) %}

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `campaignId` | path | integer | ✓ | Идентификатор кампании (магазина) — технический идентификатор, который представляет ваш магазин в системе Яндекс Маркета при работе через API. Он однозначно связывается с вашим магазином, но предназначен только для автоматизированного взаимодействия.  Его можно узнать с помощью запроса [GET v2/campaigns](../../reference/campaigns/getCampaigns.md) или найти в кабинете продавца на Маркете. Нажмите на иконку вашего аккаунта → **Настройки** и в меню слева выберите **API и модули**:  * блок **Идентификатор кампании**; * вкладка **Лог запросов** → выпадающий список в блоке **Показывать логи**.  ⚠️ Не путайте его с: - идентификатором магазина, который отображается в личном кабинете продавца; - рекламными кампаниями.  |
| `orderId` | path | integer | ✓ | Идентификатор заказа. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `items` | array | ✓ | Список проданных товаров.  Для товара с одинаковым `id` передавайте один элемент и массив `codes` по количеству ключей.  |
## Responses

### `200` Пустой ответ.

{% note warning "Ответ `200` сам по себе не значит, что ключи переданы покупателю" %}

Если письмо с ключами удалось доставить, Маркет переведет заказ в финальный статус `DELIVERED`.

Статус заказа можно узнать с помощью метода [POST v1/businesses/{businessId}/orders](../../reference/orders/getBusinessOrders.md).

{% endnote %}


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 200](../_shared/examples/PUT__v2_campaigns__campaignId__orders__orderId__cancellation_accept_200.json)

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
