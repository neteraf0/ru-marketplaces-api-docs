# `POST` /v2/reports/united-marketplace-services/generate

**Tag:** [fby](index.md)

**operationId:** `generateUnitedMarketplaceServicesReport`

**Отчет по стоимости услуг**

{% include notitle [access](../../_auto/method_scopes/generateUnitedMarketplaceServicesReport.md) %}

Запускает генерацию отчета по стоимости услуг за заданный период. [Что это за отчет](https://yandex.ru/support/marketplace/ru/accounting/transactions#reports)

Тип отчета зависит от того, какие поля заполнены в запросе:

|**Тип отчета**               |**Какие поля нужны**             |
|-----------------------------|---------------------------------|
|По дате начисления услуги    |`dateFrom` и `dateTo`            |
|По дате формирования акта    |`year` и `month`                 |

Заказать отчеты обоих типов одним запросом нельзя.

Узнать статус генерации и получить ссылку на готовый отчет можно с помощью запроса [GET v2/reports/info/{reportId}](../../reference/reports/getReportInfo.md).

{% include notitle [reports](../../_auto/reports/united/services/generator/united_marketplace_services.md) %}

{% include notitle [limit](../../_auto/method_limits/generateUnitedMarketplaceServicesReport.md) %}

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `format` | query | string (enum: FILE, CSV, JSON) |  | Формат отчета или документа. |
| `language` | query | string (enum: RU, EN) |  | Язык отчета или документа. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `businessId` | integer | ✓ | Идентификатор кабинета. {% if audience == "partner" %}Чтобы его узнать, воспользуйтесь запросом [GET v2/campaigns](../../reference/campaigns/getCampaigns.md).  ℹ️ [Что такое кабинет и магазин на Маркете](https://yandex.ru/support/marketplace/account/introduction.html) {% endif %}  |
| `dateTimeFrom` | string |  | Начало периода, включительно. |
| `dateTimeTo` | string |  | Конец периода, включительно. Максимальный период — 3 месяца. |
| `dateFrom` | string |  | Начало периода, включительно.  Формат даты: `ГГГГ-ММ-ДД`.  *Example: `2025-08-22`* |
| `dateTo` | string |  | Конец периода, включительно. Максимальный период — 3 месяца.  Формат даты: `ГГГГ-ММ-ДД`.  |
| `yearFrom` | integer |  | Год. *Example: `2025`* |
| `monthFrom` | integer |  | Номер месяца. *Example: `12`* |
| `yearTo` | integer |  | Год. *Example: `2025`* |
| `monthTo` | integer |  | Номер месяца. *Example: `12`* |
| `placementPrograms` | array |  | Список моделей, которые нужны в отчете.  |
| `inns` | array |  | Список ИНН, которые нужны в отчете. |
| `campaignIds` | array |  | Список идентификаторов кампании тех магазинов, которые нужны в отчете.  |
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
