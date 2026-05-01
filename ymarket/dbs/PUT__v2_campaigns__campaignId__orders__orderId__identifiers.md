# `PUT` /v2/campaigns/{campaignId}/orders/{orderId}/identifiers

**Tag:** [dbs](index.md)

**operationId:** `provideOrderItemIdentifiers`

**Передача кодов маркировки единиц товара**

{% include notitle [access](../../_auto/method_scopes/provideOrderItemIdentifiers.md) %}

{% note warning "Если вы работаете по модели FBS" %}

Используйте метод [PUT v2/campaigns/{campaignId}/orders/{orderId}/boxes](../../reference/orders/setOrderBoxLayout.md).

{% endnote %}

Передает Маркету коды маркировки для единиц товара в указанном заказе. Подробнее о работе с маркируемыми товарами читайте в [Справке продавца на Маркете](https://yandex.ru/support/marketplace/orders/cz.html).

Маркировка товаров в системе [«Честный ЗНАК»](https://честныйзнак.рф/) **необязательна** для заказов от физических лиц, но **обязательна** для заказов от бизнеса.

Для модели DBS коды маркировки в системе [«Честный ЗНАК»](https://честныйзнак.рф/) не проверяются в ГИС МТ — проверка выполняется только для моделей FBS и Экспресс.

Принимаются коды следующих типов:

* Коды в системе [«Честный ЗНАК»](https://честныйзнак.рф/) или [«ASL BELGISI»](https://aslbelgisi.uz) (для продавцов :no-translate[Market Yandex Go]).
* УИН для ювелирных изделий.
* РНПТ и ГТД для импортных прослеживаемых товаров.

Для каждой позиции в заказе, требующей маркировки, нужно передать список кодов — по одному для каждой единицы товара. Например, если в заказе две пары тапочек и одна пара туфель, получится список из двух кодов для первой позиции и список из одного кода для второй.

{% include notitle [limit](../../_auto/method_limits/provideOrderItemIdentifiers.md) %}

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `campaignId` | path | integer | ✓ | Идентификатор кампании (магазина) — технический идентификатор, который представляет ваш магазин в системе Яндекс Маркета при работе через API. Он однозначно связывается с вашим магазином, но предназначен только для автоматизированного взаимодействия.  Его можно узнать с помощью запроса [GET v2/campaigns](../../reference/campaigns/getCampaigns.md) или найти в кабинете продавца на Маркете. Нажмите на иконку вашего аккаунта → **Настройки** и в меню слева выберите **API и модули**:  * блок **Идентификатор кампании**; * вкладка **Лог запросов** → выпадающий список в блоке **Показывать логи**.  ⚠️ Не путайте его с: - идентификатором магазина, который отображается в личном кабинете продавца; - рекламными кампаниями.  |
| `orderId` | path | integer | ✓ | Идентификатор заказа. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `items` | array | ✓ | Список позиций, требующих маркировки.  |
## Responses

### `200` Ответ `200` обозначает, что коды успешно записались. Ответ содержит краткие сведения о промаркированных товарах.


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 200](../_shared/examples/PUT__v2_campaigns__campaignId__orders__orderId__identifiers_200.json)

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
