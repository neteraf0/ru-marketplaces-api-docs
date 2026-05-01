# `POST` /v2/businesses/{businessId}/promos

**Tag:** [promos](index.md)

**operationId:** `getPromos`

**Получение списка акций**

{% include notitle [access](../../_auto/method_scopes/getPromos.md) %}

Возвращает информацию об акциях Маркета. Не возвращает данные об акциях, которые создал продавец.

По умолчанию возвращаются акции, в которых продавец участвует или может принять участие.

Чтобы получить текущие или завершенные акции, передайте параметр `participation`.

Типы акций, которые возвращаются в ответе:

* прямая скидка;
* флеш-акция;
* скидка по промокоду.

{% include notitle [limit](../../_auto/method_limits/getPromos.md) %}

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `businessId` | path | integer | ✓ | Идентификатор кабинета. Чтобы его узнать, воспользуйтесь запросом [GET v2/campaigns](../../reference/campaigns/getCampaigns.md).  ℹ️ [Что такое кабинет и магазин на Маркете](https://yandex.ru/support/marketplace/account/introduction.html)  |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `participation` | string (enum: PARTICIPATING_NOW, PARTICIPATED) |  | Без указания фильтра возвращаются акции, в которых продавец участвует или может принять участие.  Какие акции вернутся при указании фильтра:  * `PARTICIPATING_NOW` — текущие акции, в которых участвует продавец.  * `PARTICIPATED` — завершенные акции, в которых продавец участвовал за последний год. Если за год их было меньше 15, в ответе придут 15 последних акций за все время.  |
| `mechanics` | string (enum: DIRECT_DISCOUNT, BLUE_FLASH, MARKET_PROMOCODE) |  | Тип акции:  * `DIRECT_DISCOUNT` — прямая скидка.  * `BLUE_FLASH` — флеш-акция.  * `MARKET_PROMOCODE` — скидка по промокоду.  |
## Responses

### `200` Список акций Маркета.


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 200](../_shared/examples/POST__v2_businesses__businessId__promos_200.json)

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
