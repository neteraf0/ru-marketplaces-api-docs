# `POST` /v2/businesses/{businessId}/offer-cards/update

**Tag:** [fbs](index.md)

**operationId:** `updateOfferContent`

**Редактирование категорийных характеристик товара**

{% include notitle [access](../../_auto/method_scopes/updateOfferContent.md) %}

Редактирует характеристики товара, которые специфичны для категории, к которой он относится.

{% note warning "Здесь только то, что относится к конкретной категории" %}

Если вам нужно изменить основные параметры товара (название, описание, изображения, видео, производитель, штрихкод), воспользуйтесь запросом [POST v2/businesses/{businessId}/offer-mappings/update](../../reference/business-assortment/updateOfferMappings.md).

{% endnote %}

Чтобы удалить характеристики, которые заданы в параметрах с типом `string`, передайте пустое значение.

{% note info "Данные в каталоге обновляются не мгновенно" %}

Это занимает до нескольких минут.

{% endnote %}

{% include notitle [limit](../../_auto/method_limits/updateOfferContent.md) %}

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `businessId` | path | integer | ✓ | Идентификатор кабинета. Чтобы его узнать, воспользуйтесь запросом [GET v2/campaigns](../../reference/campaigns/getCampaigns.md).  ℹ️ [Что такое кабинет и магазин на Маркете](https://yandex.ru/support/marketplace/account/introduction.html)  |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `offersContent` | array | ✓ | Список товаров с указанными характеристиками. |
## Responses

### `200` Запрос выполнен корректно, данные обработаны.

{% note warning "Ответ `200` сам по себе не значит, что переданные значения корректны" %}

Обязательно посмотрите детали ответа: `status`, а также перечень ошибок (`results.errors`) и замечаний (`results.warnings`), если они есть.

- Если хотя бы по одному товару вернулась ошибка (`results.errors`), поле `status` = `ERROR`. Изменения по всем переданным товарам не будут применены.
- Если ошибок нет, но хотя бы по одному товару вернулось замечание (`results.warnings`), поле `status` = `OK`, и изменения будут применены.

{% endnote %}

Если в `status` вернулось `ERROR`, убедитесь, что:

* все обязательные характеристики заполнены;
* характеристики действительно существуют в указанных категориях;
* значения соответствуют характеристикам;
* ваши собственные значения имеют нужный тип данных.

Найти проблемы помогут поля `errors` и `warnings`.


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 200](../_shared/examples/POST__v2_businesses__businessId__offer_cards_update_200.json)

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

### `423` К ресурсу нельзя применить указанный метод. [Подробнее об ошибке](../../concepts/error-codes.md#423)


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 423](../_shared/examples/POST__v2_businesses__businessId__settings_400.json)

### `500` Внутренняя ошибка Маркета. [Подробнее об ошибке](../../concepts/error-codes.md#500)


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 500](../_shared/examples/POST__v2_businesses__businessId__settings_400.json)
