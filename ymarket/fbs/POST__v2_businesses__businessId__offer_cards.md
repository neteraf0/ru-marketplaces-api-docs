# `POST` /v2/businesses/{businessId}/offer-cards

**Tag:** [fbs](index.md)

**operationId:** `getOfferCardsContentStatus`

**Получение информации о заполненности карточек магазина**

{% include notitle [access](../../_auto/method_scopes/getOfferCardsContentStatus.md) %}

Возвращает сведения о состоянии контента для заданных товаров:

* создана ли карточка товара и в каком она статусе;
* рейтинг карточки — на сколько процентов она заполнена;
* переданные характеристики товаров;
* есть ли ошибки или предупреждения, связанные с контентом;
* рекомендации по заполнению карточки.

Чтобы получить другие характеристики товаров, воспользуйтесь методом [POST v2/businesses/{businessId}/offer-mappings](../../reference/business-assortment/getOfferMappings.md).

{% include notitle [limit](../../_auto/method_limits/getOfferCardsContentStatus.md) %}

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
| `offerIds` | array |  | Идентификаторы товаров, информация о которых нужна.  ⚠️ Не используйте это поле одновременно с фильтрами по статусам карточек, категориям, брендам или тегам. Если вы хотите воспользоваться фильтрами, оставьте поле пустым.  |
| `cardStatuses` | array |  | Фильтр по статусам карточек.  [Что такое карточка товара](https://yandex.ru/support/marketplace/assortment/content/index.html)  |
| `categoryIds` | array |  | Фильтр по категориям на Маркете. |
| `withRecommendations` | boolean |  | Возвращать ли список рекомендаций к заполнению карточки и средний рейтинг карточки у товаров той категории, которая указана в `marketCategoryId`.  Значение по умолчанию: `false`. Если информация нужна, передайте значение `true`.  |
## Responses

### `200` Информация о карточках указанных товаров.


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 200](../_shared/examples/POST__v2_businesses__businessId__offer_cards_200.json)

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
