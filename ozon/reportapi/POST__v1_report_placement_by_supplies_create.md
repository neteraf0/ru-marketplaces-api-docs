# `POST` /v1/report/placement/by-supplies/create

**Tag:** [ReportAPI](index.md)

**operationId:** `CreatePlacementBySuppliesReport`

**Получить отчёт о стоимости размещения по поставкам**

Соответствует разделу **FBO → Стоимость размещения** в личном кабинете.

Отчёт можно получить не больше 5 раз в день.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `date_from` | string | ✓ | Дата начала отчётного периода в формате `YYYY-MM-DD`. |
| `date_to` | string | ✓ | Дата окончания отчётного периода в формате `YYYY-MM-DD`.  Максимальный период — 31 день.  |
## Responses

### `200` Отчёт о стоимости размещения


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Уникальный идентификатор отчёта. Чтобы получить отчёт, передайте это значение в метод [/v1/report/info](#operation/ReportAPI_ReportInfo). |

[Response 200](../_shared/examples/POST__v1_report_placement_by_products_create_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
