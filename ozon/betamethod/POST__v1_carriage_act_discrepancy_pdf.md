# `POST` /v1/carriage/act-discrepancy/pdf

**Tag:** [BetaMethod](index.md)

**operationId:** `CarriageActDiscrepancyPDF`

**Получить акт о расхождениях по отгрузке FBS**

Акт о расхождениях доступен только для отгрузок в статусе `closed` и только для продавцов из СНГ.

Вы можете оставить обратную связь о работе метода в [комментариях](https://dev.ozon.ru/community/1876-Novyi-metod-dlia-polucheniia-akta-o-raskhozhdeniiakh-FBS/) в сообществе разработчиков Ozon for dev.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `carriage_id` | integer | ✓ | Идентификатор отгрузки. |
## Responses

### `200` Акт о расхождениях


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `content` | string |  | Содержание файла в бинарном виде. |
| `name` | string |  | Название файла. |
| `type` | string |  | Тип файла. |

[Response 200](../_shared/examples/POST__v1_carriage_act_discrepancy_pdf_200.json)

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
