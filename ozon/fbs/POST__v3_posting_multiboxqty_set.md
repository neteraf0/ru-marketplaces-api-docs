# `POST` /v3/posting/multiboxqty/set

**Tag:** [FBS](index.md)

**operationId:** `PostingAPI_PostingMultiBoxQtySetV3`

**Указать количество коробок для многокоробочных отправлений**

Метод для передачи количества коробок для отправлений, в которых есть многокоробочные товары.

Используйте метод при работе по схеме rFBS Агрегатор — c доставкой партнёрами Ozon.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `posting_number` | string | ✓ | Идентификатор многокоробочного отправления. |
| `multi_box_qty` | integer | ✓ | Количество коробок, в которые упакован товар. |

[Request example](examples/POST__v3_posting_multiboxqty_set_req.json)

## Responses

### `200` Количество коробок указано


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | postingv3PostingMultiBoxQtySetV3ResponseResult |  | Результат передачи количества коробок. |

[Response 200](../_shared/examples/POST__v3_posting_multiboxqty_set_200.json)

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
