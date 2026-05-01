# `POST` /v2/reports/united-returns/generate

**Tag:** [reports](index.md)

**operationId:** `generateUnitedReturnsReport`

**Отчет по невыкупам и возвратам**

{% include notitle [access](../../_auto/method_scopes/generateUnitedReturnsReport.md) %}

Запускает генерацию сводного отчета по невыкупам и возвратам за заданный период. [Что это за отчет](https://yandex.ru/support/marketplace/ru/orders/returns/logistic#rejected-orders)

Отчет содержит информацию о невыкупах и возвратах за указанный период, а также о тех, которые готовы к выдаче.

Узнать статус генерации и получить ссылку на готовый отчет можно с помощью запроса [GET v2/reports/info/{reportId}](../../reference/reports/getReportInfo.md).

{% include notitle [reports](../../_auto/reports/united/returns/generator/united_returns.md) %}

{% include notitle [tariff-period](../../_includes/common/report-data-period-unchanged.md) %}

{% include notitle [limit](../../_auto/method_limits/generateUnitedReturnsReport.md) %}

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `format` | query | string (enum: FILE, CSV, JSON) |  | Формат отчета или документа. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `businessId` | integer | ✓ | Идентификатор кабинета. {% if audience == "partner" %}Чтобы его узнать, воспользуйтесь запросом [GET v2/campaigns](../../reference/campaigns/getCampaigns.md).  ℹ️ [Что такое кабинет и магазин на Маркете](https://yandex.ru/support/marketplace/account/introduction.html) {% endif %}  |
| `dateFrom` | string | ✓ | Начало периода, включительно.  Формат даты: `ГГГГ-ММ-ДД`.  *Example: `2025-08-22`* |
| `dateTo` | string | ✓ | Конец периода, включительно.  Формат даты: `ГГГГ-ММ-ДД`.  *Example: `2025-09-22`* |
| `campaignIds` | array |  | Список идентификаторов кампании тех магазинов, которые нужны в отчете.  |
| `returnType` | string (enum: UNREDEEMED, RETURN) |  | Тип фильтрации:  * `UNREDEEMED` — невыкупы.  * `RETURN` — возвраты.  Если не указывать, в ответе будут и невыкупы, и возвраты.  |
| `returnStatusTypes` | array |  | Статусы передачи возвратов, которые нужны в отчете.  Если их не указать, вернется информация по всем возвратам.  |
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
