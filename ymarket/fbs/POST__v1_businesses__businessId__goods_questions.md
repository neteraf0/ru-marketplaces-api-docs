# `POST` /v1/businesses/{businessId}/goods-questions

**Tag:** [fbs](index.md)

**operationId:** `getGoodsQuestions`

**Получение вопросов о товарах продавца**

{% include notitle [access](../../_auto/method_scopes/getGoodsQuestions.md) %}

Возвращает вопросы о товарах продавца по указанным фильтрам.

Результаты возвращаются постранично, одна страница содержит не более 50 вопросов.

{% include notitle [limit](../../_auto/method_limits/getGoodsQuestions.md) %}

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
| `categoryIds` | array |  | Идентификаторы категорий товаров. |
| `dateFrom` | string |  | Дата начала периода создания вопроса.  Если параметр не указан, возвращается информация за 1 месяц до указанной в `dateTo` даты.  Максимальный интервал 1 месяц.  *Example: `2020-02-02`* |
| `dateTo` | string |  | Дата окончания периода создания вопроса.  Если параметр не указан, используется текущая дата.  Максимальный интервал 1 месяц.  *Example: `2020-02-02`* |
| `needAnswer` | boolean |  | Нужен ли ответ на вопрос.  * `true` — только вопросы, которые ждут ответа. * `false` — все вопросы.  |
| `sort` | string (enum: CREATED_AT_DESC, CREATED_AT_ASC) |  | Порядок сортировки вопросов. * `CREATED_AT_DESC` — по дате создания вопроса по убыванию; * `CREATED_AT_ASC` — по дате создания вопроса по возрастанию.  |
## Responses

### `200` Список вопросов.


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 200](../_shared/examples/POST__v1_businesses__businessId__goods_questions_200.json)

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
