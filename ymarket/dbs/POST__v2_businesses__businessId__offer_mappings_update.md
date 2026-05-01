# `POST` /v2/businesses/{businessId}/offer-mappings/update

**Tag:** [dbs](index.md)

**operationId:** `updateOfferMappings`

**Добавление товаров в каталог и изменение информации о них**

{% include notitle [access](../../_auto/method_scopes/updateOfferMappings.md) %}

Добавляет товары в каталог и передает:

* их [листовые категории](*list-categories) на Маркете и категорийные характеристики;
* основные характеристики;
* цены на товары в кабинете.

Также объединяет товары на карточке, редактирует и удаляет информацию об уже добавленных товарах, в том числе цены в кабинете и категории товаров.

Список категорий Маркета можно получить с помощью запроса [POST v2/categories/tree](../../reference/categories/getCategoriesTree.md), а характеристики товаров по категориям с помощью [POST v2/category/{categoryId}/parameters](../../reference/content/getCategoryContentParameters.md).

{% cut "Добавить новый товар" %}

Передайте его с новым идентификатором, который раньше никогда не использовался в каталоге.

Обязательно укажите параметры: `offerId`, `name`, `marketCategoryId`, `pictures`, `vendor`, `description`.

Старайтесь сразу передать как можно больше информации — она потребуется Маркету для подбора подходящей карточки или создания новой.

Если известно, какой карточке на Маркете соответствует товар, можно сразу указать идентификатор этой карточки (SKU на Маркете) в поле `marketSKU`.

**Для продавцов Market Yandex Go:**

Когда вы добавляете товары в каталог, указывайте значения параметров `name` и `description` на русском языке. Чтобы на витрине они отображались и на другом языке, еще раз выполните запрос `POST v2/businesses/{businessId}/offer-mappings/update`, где укажите:

  * язык в параметре `language`;
  * значения параметров `name` и `description` на указанном языке.

  Повторно передавать остальные характеристики товара не нужно.

{% endcut %}

{% cut "Изменить информацию о товаре" %}

Передайте новые данные, указав в `offerId` SKU товара в вашей системе.

Поля, в которых ничего не меняется, можно не передавать.

{% endcut %}

{% cut "Удалить переданные ранее параметры товара" %}

В `deleteParameters` укажите значения параметров, которые хотите удалить. Можно передать сразу несколько значений.

Для параметров с типом `string` также можно передать пустое значение.

{% endcut %}

Параметр `offerId` (SKU товара в вашей системе) должен быть **уникальным** для всех товаров, которые вы передаете.

{% note warning "Правила использования SKU" %}

* У каждого товара SKU должен быть свой.

* Уже заданный SKU нельзя освободить и использовать заново для другого товара. Каждый товар должен получать новый идентификатор, до того никогда не использовавшийся в вашем каталоге.

SKU товара можно изменить в кабинете продавца на Маркете. О том, как это сделать, читайте [в Справке Маркета для продавцов](https://yandex.ru/support2/marketplace/ru/assortment/operations/edit-sku).

{% endnote %}

{% note info "Данные в каталоге обновляются не мгновенно" %}

Это занимает до нескольких минут.

{% endnote %}

{% include notitle [limit](../../_auto/method_limits/updateOfferMappings.md) %}

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `businessId` | path | integer | ✓ | Идентификатор кабинета. Чтобы его узнать, воспользуйтесь запросом [GET v2/campaigns](../../reference/campaigns/getCampaigns.md).  ℹ️ [Что такое кабинет и магазин на Маркете](https://yandex.ru/support/marketplace/account/introduction.html)  |
| `language` | query | string (enum: RU, UZ) |  | Язык, на котором принимаются и возвращаются значения в параметрах `name` и `description`.  Значение по умолчанию: `RU`.  |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `offerMappings` | array | ✓ | Список товаров, которые нужно добавить или обновить.  {% note warning "Скоро мы уменьшим максимальное количество товаров в запросе" %}  Уже сейчас не передавайте больше 100.  {% endnote %}     |
| `onlyPartnerMediaContent` | boolean |  | Будут ли использоваться только переданные вами данные о товарах.  Значение по умолчанию: `false`. Чтобы удалить данные, которые добавил Маркет, передайте значение `true`.  |
## Responses

### `200` Запрос выполнен корректно, данные обработаны.

{% note warning "Ответ `200` сам по себе не значит, что переданные значения корректны" %}

Обязательно посмотрите детали ответа: `status`, а также перечень ошибок (`results.errors`) и замечаний (`results.warnings`), если они есть.

- Если хотя бы по одному товару вернулась ошибка (`results.errors`), поле `status` = `ERROR`. Изменения по всем переданным товарам не будут применены.
- Если ошибок нет, но хотя бы по одному товару вернулось замечание (`results.warnings`), поле `status` = `OK`, и изменения будут применены.

{% endnote %}


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 200](../_shared/examples/POST__v2_businesses__businessId__offer_mappings_update_200.json)

### `400` ⚠️ Даже если проблема связана всего с одним товаром в запросе, в каталог не отправится ни один.

Запрос содержит неправильные данные. [Подробнее об ошибках при работе с товарами](../../concepts/error-codes#offers) и [об ошибках при работе с ценами](../../concepts/error-codes#prices)


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
