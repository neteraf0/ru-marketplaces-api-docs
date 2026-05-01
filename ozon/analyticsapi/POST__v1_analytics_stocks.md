# `POST` /v1/analytics/stocks

**Tag:** [AnalyticsAPI](index.md)

**operationId:** `AnalyticsAPI_AnalyticsStocks`

**Получить аналитику по остаткам**

Используйте метод, чтобы получить аналитику по остаткам товаров на складах. Метод соответствует разделу [**FBO → Управление остатками**](https://seller.ozon.ru/app/fbo-stocks/stocks-management/) в личном кабинете. Аналитика обновляется два раза в день: примерно в 07:00 и 16:00 по UTC.

В запросе используйте только одно из полей: `cluster_ids` или `macrolocal_cluster_ids`, иначе вернётся ошибка.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `cluster_ids` | array |  | Фильтр по идентификаторам кластеров. Получить идентификаторы можно через метод [/v1/cluster/list](#operation/SupplyDraftAPI_DraftClusterList). |
| `item_tags` | array |  | Фильтр по тегам товара:       - `ITEM_ATTRIBUTE_NONE` — без тега; - `ECONOM` — эконом-товар; - `NOVEL` — новинка; - `DISCOUNT` — уценённый товар; - `FBS_RETURN` — товар из возврата FBS; - `SUPER` — Super-товар.  |
| `macrolocal_cluster_ids` | array |  | Фильтр по идентификаторам макролокальных кластеров. Получить идентификаторы можно в параметре `macrolocal_cluster_ids` метода [/v1/cluster/list](#operation/SupplyDraftAPI_DraftClusterList) или через метод [/v2/cluster/list](#operation/DraftClusterList). |
| `skus` | array | ✓ | Фильтр по идентификаторам товаров в системе Ozon — SKU. |
| `turnover_grades` | array |  | Фильтр по статусу ликвидности товаров:       - `TURNOVER_GRADE_NONE` — нет статуса ликвидности.       - `DEFICIT` — дефицитный. Остатков товара хватит до 28 дней. - `POPULAR` — очень популярный. Остатков товара хватит на 28–56 дней. - `ACTUAL` — популярный. Остатков товара хватит на 56–120 дней. - `SURPLUS` — избыточный. Товар продаётся медленно, остатков хватит более чем на 120 дней. - `NO_SALES` — без продаж. У товара нет продаж последние 28 дней. - `WAS_NO_SALES` — был без продаж. У товара не было продаж и остатков последние 28 дней. - `RESTRICTED_NO_SALES` — без продаж, ограничен. У товара не было продаж более 120 дней. Такой товар [нельзя добавить в поставку](https://seller-edu.ozon.ru/fbo/rabota-so-stokom/nehodovye-tovary). - `COLLECTING_DATA` — сбор данных. Для расчёта ликвидности нового товара собираем данные в течение 60 дней после поставки. - `WAITING_FOR_SUPPLY` — ожидаем поставки. На складе нет остатков, доступных к продаже. Сделайте поставку для начала сбора данных. - `WAS_DEFICIT` — был дефицитным. Товар был дефицитным последние 56 дней. Сейчас у него нет остатков. - `WAS_POPULAR` — был очень популярным. Товар был очень популярным последние 56 дней. Сейчас у него нет остатков. - `WAS_ACTUAL` — был популярным. Товар был популярным последние 56 дней. Сейчас у него нет остатков. - `WAS_SURPLUS` — был избыточным. Товар был избыточным последние 56 дней. Сейчас у него нет остатков.  |
| `warehouse_ids` | array |  | Фильтр по идентификаторам складов. Получить идентификаторы можно через метод [/v1/warehouse/list](#operation/WarehouseAPI_WarehouseList). |
## Responses

### `200` Аналитика по остаткам на складах


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `items` | array |  | Информация о товарах. |

[Response 200](../_shared/examples/POST__v1_analytics_stocks_200.json)

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
