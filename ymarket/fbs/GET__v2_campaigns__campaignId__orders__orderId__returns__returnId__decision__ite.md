# `GET` /v2/campaigns/{campaignId}/orders/{orderId}/returns/{returnId}/decision/{itemId}/image/{imageHash}

**Tag:** [fbs](index.md)

**operationId:** `getReturnPhoto`

**Получение фотографий товаров в возврате**

{% include notitle [access](../../_auto/method_scopes/getReturnPhoto.md) %}

Получает фотографии товаров, которые покупатель приложил к заявлению на возврат.

Хеш изображения (`imageHash`) можно получить из ответов методов [GET v2/campaigns/{campaignId}/orders/{orderId}/returns/{returnId}](../../reference/orders/getReturn.md) и [GET v2/campaigns/{campaignId}/returns](../../reference/orders/getReturns.md) — в поле `images` решения по товару.

Максимальный размер изображения — 50 МБ.

Тип изображения можно определить по заголовку `Content-Type` в ответе.

{% include notitle [limit](../../_auto/method_limits/getReturnPhoto.md) %}

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `campaignId` | path | integer | ✓ | Идентификатор кампании (магазина) — технический идентификатор, который представляет ваш магазин в системе Яндекс Маркета при работе через API. Он однозначно связывается с вашим магазином, но предназначен только для автоматизированного взаимодействия.  Его можно узнать с помощью запроса [GET v2/campaigns](../../reference/campaigns/getCampaigns.md) или найти в кабинете продавца на Маркете. Нажмите на иконку вашего аккаунта → **Настройки** и в меню слева выберите **API и модули**:  * блок **Идентификатор кампании**; * вкладка **Лог запросов** → выпадающий список в блоке **Показывать логи**.  ⚠️ Не путайте его с: - идентификатором магазина, который отображается в личном кабинете продавца; - рекламными кампаниями.  |
| `orderId` | path | integer | ✓ | Идентификатор заказа. |
| `returnId` | path | integer | ✓ | Идентификатор невыкупа или возврата. |
| `itemId` | path | integer | ✓ | Идентификатор товара в возврате. |
| `imageHash` | path | string | ✓ | Хеш ссылки изображения для загрузки. |

## Responses

### `200` Фотография товаров.

`string`

[Response 200](../_shared/examples/GET__v2_campaigns__campaignId__orders__orderId__delivery_shipments__shipmentId.json)

`string`

[Response 200](../_shared/examples/GET__v2_campaigns__campaignId__orders__orderId__delivery_shipments__shipmentId.json)

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
