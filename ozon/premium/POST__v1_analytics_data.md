# `POST` /v1/analytics/data

**Tag:** [Premium](index.md)

**operationId:** `AnalyticsAPI_AnalyticsGetData`

**Данные аналитики**

Уĸажите период и метриĸи, ĸоторые нужно посчитать. В ответе будет аналитиĸа, сгруппированная по параметру `dimensions`.

Для продавцов без подписки [Premium Plus](https://seller-edu.ozon.ru/seller-rating/about-rating/subscription-premium-plus):
- доступны данные за последние 3 месяца,
- есть ограничения по способам группировки данных и метрикам.

Для продавцов с подпиской [Premium Plus](https://seller-edu.ozon.ru/seller-rating/about-rating/subscription-premium-plus) или [Premium Pro](https://seller-edu.ozon.ru/seller-rating/about-rating/podpiska-premium-pro) ограничений нет.

Метод можно использовать не больше 1 раза в минуту.
Соответствует разделу **Аналитика → Графики** в личном кабинете.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `date_from` | string | ✓ | Дата, с которой будут данные в отчёте.  Если у вас нет Premium-подписки, укажите дату в пределах последних трёх месяцев.  |
| `date_to` | string | ✓ | Дата, по которую будут данные в отчёте. |
| `dimension` | array | ✓ | Группировка данных в отчёте.  Способы группировки, доступные всем продавцам:   - `unknownDimension` — неизвестное измерение,   - `sku` — идентификатор товара,   - `spu` — идентификатор товара — объединённая карточка,   - `day` — день,   - `week` — неделя,   - `month` — месяц.  Способы группировки, доступные только продавцам с подпиской [Premium Plus](https://seller-edu.ozon.ru/seller-rating/about-rating/subscription-premium-plus):   - `year` — год,   - `category1` — категория первого уровня,   - `category2` — категория второго уровня,   - `category3` — категория третьего уровня,   - `category4` — категория четвертого уровня,   - `brand` — бренд,   - `modelID` — модель.  |
| `filters` | array |  | Фильтры. |
| `limit` | integer | ✓ | Количество значений в ответе:   - максимум — 1000,   - минимум — 1.  |
| `metrics` | array | ✓ | Укажите до 14 метрик. Если их будет больше, вы получите ошибку с кодом `InvalidArgument`.  Список метриĸ, по ĸоторым будет сформирован отчёт.  Метрики, доступные всем продавцам:   - `revenue` — заказано на сумму,   - `ordered_units` — заказано товаров.  Метрики, доступные только продавцам с подпиской [Premium Plus](https://seller-edu.ozon.ru/seller-rating/about-rating/subscription-premium-plus):   - `unknown_metric` — неизвестная метрика.   - `hits_view_search` — показы в поиске и в категории.   - `hits_view_pdp` — показы на карточке товара.   - `hits_view` — всего показов.   - `hits_tocart_search` — в корзину из поиска или категории.   - `hits_tocart_pdp` — в корзину из карточки товара.   - `hits_tocart` — всего добавлено в корзину.   - `session_view_search` — сессии с показом в поиске или в каталоге. Считаются уникальные посетители с просмотром в поиске или каталоге.   - `session_view_pdp` — сессии с показом на карточке товара. Считаются уникальные посетители, которые просмотрели карточку товара.   - `session_view` — всего сессий. Считаются уникальные посетители.   - `conv_tocart_search` — конверсия в корзину из поиска или категории.   - `conv_tocart_pdp` — конверсия в корзину из карточки товара.   - `conv_tocart` — общая конверсия в корзину.   - `returns` — возвращено товаров.   - `cancellations` — отменено товаров.   - `delivered_units` — доставлено товаров.   - `position_category` — позиция в поиске и категории.  |
| `offset` | integer |  | Количество элементов, которое будет пропущено в ответе. Например, если `offset = 10`, то ответ начнётся с 11-го найденного элемента. |
| `sort` | array |  | Настройки сортировки отчёта. |

[Request example](examples/POST__v1_analytics_data_req.json)

## Responses

### `200` Данные аналитики


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | AnalyticsGetDataResponseResult |  | Результаты запроса. |
| `timestamp` | string |  | Время создания отчёта. |

[Response 200](../_shared/examples/POST__v1_analytics_data_200.json)

### `400` Неверный параметр


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 400](../_shared/examples/POST__v1_roles_default.json)

### `403` Доступ запрещён


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 403](../_shared/examples/POST__v1_roles_default.json)

### `404` Ответ не найден


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 404](../_shared/examples/POST__v1_roles_default.json)

### `409` Конфликт запроса


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 409](../_shared/examples/POST__v1_roles_default.json)

### `500` Внутренняя ошибка сервера


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 500](../_shared/examples/POST__v1_roles_default.json)
