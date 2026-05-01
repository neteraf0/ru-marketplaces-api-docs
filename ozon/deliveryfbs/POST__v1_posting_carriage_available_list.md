# `POST` /v1/posting/carriage-available/list

**Tag:** [DeliveryFBS](index.md)

**operationId:** `PostingAPI_GetCarriageAvailableList`

**Список доступных перевозок**


  20 марта 2026 года отключим метод. Переключитесь на /v2/carriage/delivery/list.


Метод для получения перевозок, по которым нужно распечатать штрихкод для отгрузки и документы:
- для продацов из России — лист отгрузки и транспортную накладную;
- для продавцов из СНГ — акт и транспортную накладную.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `delivery_method_id` | integer | ✓ | Фильтр по методу доставки. Можно получить с помощью метода [/v2/delivery-method/list](#operation/WarehouseAPI_DeliveryMethodListV2). |
| `departure_date` | string |  | Дата отгрузки. По умолчанию — текущая дата. |
## Responses

### `200` Список перевозок


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` |  |  | Результат работы метода. |

[Response 200](../_shared/examples/POST__v1_posting_carriage_available_list_200.json)

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
