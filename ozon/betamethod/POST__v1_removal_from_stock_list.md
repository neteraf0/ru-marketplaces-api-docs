# `POST` /v1/removal/from-stock/list

**Tag:** [BetaMethod](index.md)

**operationId:** `GetSupplierReturnsSummaryReport`

**Отчёт по вывозу и утилизации со стока FBO**

Метод соответствует разделу [**FBO → Вывоз и утилизация**](https://seller.ozon.ru/app/fbo-operations/returns) в личном кабинете.

Вы можете оставить обратную связь по этому методу в комментариях к [обсуждению](https://dev.ozon.ru/community/1608-Novye-metody-po-vyvozu-i-utilizatsii) в сообществе разработчиков Ozon for dev.

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
| `date_to` | string | ✓ | Дата окончания отчётного периода в формате `YYYY-MM-DD`. |
| `last_id` | string |  | Идентификатор последнего значения на странице. Чтобы получить следующие значения, укажите `last_id` из ответа предыдущего запроса. |
| `limit` | integer | ✓ | Количество элементов в ответе. |

[Request example](examples/POST__v1_removal_from_stock_list_req.json)

## Responses

### `200` Отчёт по вывозу и утилизации со стока FBO


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `last_id` | string |  | Идентификатор последнего значения на странице. |
| `returns_summary_report_rows` | array |  | Информация о товарах. |

[Response 200](../_shared/examples/POST__v1_removal_from_supply_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
