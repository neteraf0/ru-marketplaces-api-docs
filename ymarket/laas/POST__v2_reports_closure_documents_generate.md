# `POST` /v2/reports/closure-documents/generate

**Tag:** [laas](index.md)

**operationId:** `generateClosureDocumentsReport`

**Закрывающие документы**

{% include notitle [access](../../_auto/method_scopes/generateClosureDocumentsReport.md) %}

Возвращает ZIP-архив с закрывающими документами в формате PDF за указанный месяц.

{% cut "Состав документов в зависимости от типа договора" %}

* **Договор на размещение**

  * [акт об оказанных услугах](*acts-main-act)
  * [счет-фактура](*acts-main-invoice)
  * [сводный отчет по данным статистики](*acts-main-report)
  * [отчет об исполнении поручения и о зачете взаимных требований](*acts-main-agent) (отчет агента)

* **Договор на продвижение** (в России не заключается после 30 сентября 2024 года)

  * [акт об оказании услуг](*acts-discounts-act)
  * [счет-фактура](*acts-discounts-invoice), если этого требует схема налогообложения

* **Договор на маркетинг**

  * [акт об оказанных услугах](*acts-marketing-act)
  * [счет-фактура](*acts-main-invoice)
  * [счет-фактура на аванс](*acts-marketing-invoice)
  * [выписка по лицевому счету](*acts-marketing-account)
  * [детализация к акту](*acts-marketing-details)

{% endcut %}

Узнать статус генерации и получить ссылку на архив можно с помощью запроса [GET v2/reports/info/{reportId}](../../reference/reports/getReportInfo.md).

{% include notitle [limit](../../_auto/method_limits/generateClosureDocumentsReport.md) %}

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `campaignId` | integer | ✓ | Идентификатор кампании (магазина) — технический идентификатор, который представляет ваш магазин в системе Яндекс Маркета при работе через API. Он однозначно связывается с вашим магазином, но предназначен только для автоматизированного взаимодействия.  Его можно узнать с помощью запроса [GET v2/campaigns](../../reference/campaigns/getCampaigns.md) или найти в кабинете продавца на Маркете. Нажмите на иконку вашего аккаунта → **Настройки** и в меню слева выберите **API и модули**:  * блок **Идентификатор кампании**; * вкладка **Лог запросов** → выпадающий список в блоке **Показывать логи**.  ⚠️ Не путайте его с: - идентификатором магазина, который отображается в личном кабинете продавца; - рекламными кампаниями.  |
| `monthOfYear` | object | ✓ | Месяц и год.  |
| `contractTypes` | array |  | Типы договоров, по которым нужны закрывающие документы.  Если их не указать, вернется архив с документами по всем найденным договорам.  |
## Responses

### `200` ZIP-архив с закрывающими документами в формате :no-translate[PDF].


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
