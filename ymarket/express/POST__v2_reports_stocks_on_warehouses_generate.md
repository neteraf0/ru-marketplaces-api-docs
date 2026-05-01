# `POST` /v2/reports/stocks-on-warehouses/generate

**Tag:** [express](index.md)

**operationId:** `generateStocksOnWarehousesReport`

**Отчет по остаткам на складах**

{% include notitle [access](../../_auto/method_scopes/generateStocksOnWarehousesReport.md) %}

Запускает генерацию отчета по остаткам на складах. [Что это за отчет](https://yandex.ru/support/marketplace/ru/storage/logistics#remains-history)

**Какая информация вернется:**

* Для моделей FBY и LaaS, если указать `campaignId`, — об остатках на складах Маркета.
* Для остальных моделей, если указать `campaignId`, — об остатках на соответствующем складе магазина.
* Для остальных моделей, если указать `businessId`, — об остатках на всех складах магазинов в кабинете, кроме FBY и LaaS. Используйте фильтр `campaignIds`, чтобы указать определенные магазины.

⚠️ Не передавайте одновременно `campaignId` и `businessId`.

Узнать статус генерации и получить ссылку на готовый отчет можно с помощью запроса [GET v2/reports/info/{reportId}](../../reference/reports/getReportInfo.md).

{% list tabs %}

- Склад Маркета

  {% include notitle [reports](../../_auto/reports/stocks/stocks_on_warehouses.md) %}

- Склад магазина

  {% include notitle [reports](../../_auto/reports/offers/mass/mass_shared_stocks_business_csv_config.md) %}

- Все склады магазинов в кабинете, кроме FBY и LaaS

  {% include notitle [reports](../../_auto/reports/offers/stocks_business_config.md) %}

{% endlist %}

{% include notitle [limit](../../_auto/method_limits/generateStocksOnWarehousesReport.md) %}

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `format` | query | string (enum: FILE, CSV, JSON) |  | Формат отчета или документа. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `campaignId` | integer |  | Идентификатор кампании (магазина) — технический идентификатор, который представляет ваш магазин в системе Яндекс Маркета при работе через API. Он однозначно связывается с вашим магазином, но предназначен только для автоматизированного взаимодействия.  Его можно узнать с помощью запроса [GET v2/campaigns](../../reference/campaigns/getCampaigns.md) или найти в кабинете продавца на Маркете. Нажмите на иконку вашего аккаунта → **Настройки** и в меню слева выберите **API и модули**:  * блок **Идентификатор кампании**; * вкладка **Лог запросов** → выпадающий список в блоке **Показывать логи**.  ⚠️ Не путайте его с: - идентификатором магазина, который отображается в личном кабинете продавца; - рекламными кампаниями.  |
| `businessId` | integer |  | Идентификатор кабинета. {% if audience == "partner" %}Чтобы его узнать, воспользуйтесь запросом [GET v2/campaigns](../../reference/campaigns/getCampaigns.md).  ℹ️ [Что такое кабинет и магазин на Маркете](https://yandex.ru/support/marketplace/account/introduction.html) {% endif %}  |
| `warehouseIds` | array |  | Фильтр по идентификаторам складов (только модели FBY и LaaS). Чтобы узнать идентификатор, воспользуйтесь запросом [GET v2/warehouses](../../reference/warehouses/getFulfillmentWarehouses.md). |
| `reportDate` | string |  | Фильтр по дате (для моделей FBY и LaaS). В отчет попадут данные за **предшествующий** дате день.  Формат даты: `ГГГГ-ММ-ДД`.  |
| `categoryIds` | array |  | Фильтр по категориям на Маркете (кроме моделей FBY и LaaS). |
| `hasStocks` | boolean |  | Фильтр по наличию остатков (кроме моделей FBY и LaaS). |
| `campaignIds` | array |  | Фильтр по магазинам для отчета по кабинету (кроме моделей FBY и LaaS).  Передавайте вместе с `businessId`.  |
## Responses

### `200` В ответ приходит идентификатор, который позволяет узнавать статус генерации и скачать готовый отчет.


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 200](../_shared/examples/POST__v2_reports_united_netting_generate_200.json)

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
