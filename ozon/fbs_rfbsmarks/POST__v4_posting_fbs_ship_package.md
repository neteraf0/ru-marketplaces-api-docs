# `POST` /v4/posting/fbs/ship/package

**Tag:** [FBS&rFBSMarks](index.md)

**operationId:** `PostingAPI_ShipFbsPostingPackage`

**Частичная сборка отправления (версия 4)**


Ответ с кодом 200 не гарантирует успешную сборку отправления. Используйте метод /v3/posting/fbs/get, чтобы проверить, что отправление собрано. Если в ответе указан result.substatus = ship_failed, повторите сборку отправления.


Если в запросе передать часть товаров из отправления, метод разделит первичное отправление на две части.
В первичном несобранном отправлении останется часть товаров, которую не передали в запросе.

По умолчанию статус созданных отправлений `awaiting_packaging` — ожидает сборки.

Статус изначального отправления изменится только после изменения статуса отправлений, на которые он разделился.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `posting_number` | string | ✓ | Номер отправления. |
| `products` | array |  | Список товаров в отправлении. |
## Responses

### `200` Результат сборки отправления


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | string |  | Номера отправлений, сформированные после сборки. |

[Response 200](../_shared/examples/POST__v4_posting_fbs_ship_package_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
