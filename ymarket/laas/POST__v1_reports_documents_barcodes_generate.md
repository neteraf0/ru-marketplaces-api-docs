# `POST` /v1/reports/documents/barcodes/generate

**Tag:** [laas](index.md)

**operationId:** `generateBarcodesReport`

**Получение файла со штрихкодами**

{% include notitle [access](../../_auto/method_scopes/generateBarcodesReport.md) %}

Запускает генерацию PDF-файла со штрихкодами переданных товаров или товаров в указанной заявке на поставку.

Файл не получится сгенерировать, если в нем будет более 1 500 штрихкодов.

Узнать статус генерации и получить ссылку на готовый файл можно с помощью запроса [GET v2/reports/info/{reportId}](../../reference/reports/getReportInfo.md).

{% include notitle [limit](../../_auto/method_limits/generateBarcodesReport.md) %}

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `campaignId` | integer | ✓ | Идентификатор кампании (магазина) — технический идентификатор, который представляет ваш магазин в системе Яндекс Маркета при работе через API. Он однозначно связывается с вашим магазином, но предназначен только для автоматизированного взаимодействия.  Его можно узнать с помощью запроса [GET v2/campaigns](../../reference/campaigns/getCampaigns.md) или найти в кабинете продавца на Маркете. Нажмите на иконку вашего аккаунта → **Настройки** и в меню слева выберите **API и модули**:  * блок **Идентификатор кампании**; * вкладка **Лог запросов** → выпадающий список в блоке **Показывать логи**.  ⚠️ Не путайте его с: - идентификатором магазина, который отображается в личном кабинете продавца; - рекламными кампаниями.  |
| `barcodeFormat` | string (enum: F_30_20, F_43_25, F_58_40, F_43_25_SINGLE) | ✓ | Формат страницы и размер штрихкодов:  * `F_30_20` — А4, штрихкоды размера 30 × 20 мм. * `F_43_25` — А4, штрихкоды размера 43 × 25 мм. * `F_58_40` — А4, штрихкоды размера 58 × 40 мм. * `F_43_25_SINGLE` — для печати этикеток.  |
| `barcodeOfferInfos` | array |  | Список товаров.  Передайте этот параметр и уникальные `offerId`, чтобы вернуть файл со штрихкодами конкретных товаров.  В запросе обязательно должен быть либо `barcodeOfferInfos`, либо `supplyRequestId`, но не оба сразу.  Если передается информация о товаре, у которого несколько штрихкодов, все штрихкоды будут добавлены в файл, их количество будет задано параметром `barcodeCount`.  |
| `supplyRequestId` | integer |  | Идентификатор заявки.  {% note warning "Используется только в API" %}  По нему не получится найти заявки в кабинете продавца на Маркете. Для этого используйте `marketplaceRequestId` или `warehouseRequestId`.  {% endnote %}  |
## Responses

### `200` В ответ приходит идентификатор, который позволяет узнавать статус генерации и скачать готовый файл.


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
