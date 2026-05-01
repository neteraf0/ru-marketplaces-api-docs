# `POST` /v1/analytics/product-queries/details

**Tag:** [Premium](index.md)

**operationId:** `AnalyticsAPI_AnalyticsProductQueriesDetails`

**Получить детализацию запросов по товару**

Используйте метод, чтобы получить данные по запросам на конкретный товар. Полная аналитика доступна с подпиской [Premium](https://seller-edu.ozon.ru/seller-rating/about-rating/premium-program), [Premium Plus](https://seller-edu.ozon.ru/seller-rating/about-rating/subscription-premium-plus) или [Premium Pro](https://seller-edu.ozon.ru/seller-rating/about-rating/podpiska-premium-pro). Без подписки вы можете посмотреть часть показателей. Метод аналогичен просмотру данных по товару на вкладке **Товары в поиске → Запросы моего товара** в личном кабинете.

Аналитику по запросам можно проверить за определённые даты. Для этого укажите интервал в полях `date_from` и `date_to`. Данные за последний месяц доступны в любом интервале, кроме текущей даты — расчёт происходит в течение 1–2 дней. Аналитика за даты раньше месяца назад доступна только с подпиской [Premium](https://seller-edu.ozon.ru/seller-rating/about-rating/premium-program), [Premium Plus](https://seller-edu.ozon.ru/seller-rating/about-rating/subscription-premium-plus) или [Premium Pro](https://seller-edu.ozon.ru/seller-rating/about-rating/podpiska-premium-pro) и только по неделям — в запросе укажите параметр `date_from`.

[Подробнее о работе с запросами товара в Базе знаний продавца](https://seller-edu.ozon.ru/analytics-and-metrics/graphs/analitika-po-zaprosu)

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `date_from` | string | ✓ | Дата начала формирования аналитики. |
| `date_to` | string |  | Дата окончания формирования аналитики. |
| `limit_by_sku` | integer | ✓ | Лимит числа запросов по одному SKU. Максимум — 15 запросов. |
| `page` | integer |  | Номер страницы, возвращаемой в запросе. Минимум — 0. |
| `page_size` | integer | ✓ | Количество элементов на странице. Максимум — 100. |
| `skus` | array | ✓ | Список SKU, идентификаторов товара в системе Ozon. По ним вернётся аналитика по запросам. Максимум — 1000 SKU. |
| `sort_by` | v1AnalyticsProductQueriesDetailsRequestSortBy |  | Параметр, по которому товары будут отсортированы. Возможные значения:  - `BY_SEARCHES` — по количеству запросов; - `BY_VIEWS` — по количеству просмотров; - `BY_POSITION` — по средней позиции товара; - `BY_CONVERSION` — по значению конверсии; - `BY_GMV` — по объёму продаж по запросам.  Сортировка по параметрам `BY_VIEWS`, `BY_POSITION` и `BY_CONVERSION` доступна только с подпиской [Premium](https://seller-edu.ozon.ru/seller-rating/about-rating/premium-program) или [Premium Plus](https://seller-edu.ozon.ru/seller-rating/about-rating/subscription-premium-plus).  |
| `sort_dir` | v1AnalyticsProductQueriesDetailsRequestSortDir |  | Направление сортировки: - `DESCENDING` — по убыванию; - `ASCENDING` — по возрастанию.  |

[Request example](examples/POST__v1_analytics_product_queries_details_req.json)

## Responses

### `200` Информация о запросах по конкретному товару


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `analytics_period` | v1AnalyticsProductQueriesDetailsResponseAnalyticsPeriod |  | Период, за который формируется аналитика. |
| `page_count` | integer |  | Количество страниц. |
| `queries` | array |  | Список запросов. |
| `total` | integer |  | Общее количество запросов. |

[Response 200](../_shared/examples/POST__v1_analytics_product_queries_details_200.json)

### `400` Неверный параметр


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 400](../_shared/examples/POST__v1_roles_default.json)
