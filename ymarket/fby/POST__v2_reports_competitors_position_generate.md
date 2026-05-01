# `POST` /v2/reports/competitors-position/generate

**Tag:** [fby](index.md)

**operationId:** `generateCompetitorsPositionReport`

**Отчет «Конкурентная позиция»**

{% include notitle [access](../../_auto/method_scopes/generateCompetitorsPositionReport.md) %}

Запускает генерацию отчета «Конкурентная позиция» за заданный период. [Что это за отчет](https://yandex.ru/support2/marketplace/ru/analytics/competitors.html)

Узнать статус генерации и получить ссылку на готовый отчет можно с помощью запроса [GET v2/reports/info/{reportId}](../../reference/reports/getReportInfo.md).

{% note info "Значение -1 в отчете" %}

Если в CSV-файле в столбце :no-translate[**POSITION**] стоит -1, в этот день не было заказов с товарами в указанной категории.

{% endnote %}

{% include notitle [reports](../../_auto/reports/masterstat/competitors_position.md) %}

{% include notitle [tariff-period](../../_includes/common/report-data-period-400-days.md) %}

{% include notitle [limit](../../_auto/method_limits/generateCompetitorsPositionReport.md) %}

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `format` | query | string (enum: FILE, CSV, JSON) |  | Формат отчета или документа. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `businessId` | integer | ✓ | Идентификатор кабинета. {% if audience == "partner" %}Чтобы его узнать, воспользуйтесь запросом [GET v2/campaigns](../../reference/campaigns/getCampaigns.md).  ℹ️ [Что такое кабинет и магазин на Маркете](https://yandex.ru/support/marketplace/account/introduction.html) {% endif %}  |
| `categoryId` | integer | ✓ | Идентификатор категории. |
| `dateFrom` | string | ✓ | Начало периода, включительно.  Формат даты: `ГГГГ-ММ-ДД`.  *Example: `2025-08-22`* |
| `dateTo` | string | ✓ | Конец периода, включительно.  Формат даты: `ГГГГ-ММ-ДД`.  *Example: `2025-09-22`* |
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

### `420` Превышено ограничение на доступ к ресурсу. [Подробнее об ошибке](../../concepts/error-codes.md#420)


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 420](../_shared/examples/POST__v2_businesses__businessId__settings_400.json)

### `500` Внутренняя ошибка Маркета. [Подробнее об ошибке](../../concepts/error-codes.md#500)


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 500](../_shared/examples/POST__v2_businesses__businessId__settings_400.json)
