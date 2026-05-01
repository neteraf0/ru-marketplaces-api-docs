# `POST` /v2/posting/fbs/product/cancel

**Tag:** [FBS](index.md)

**operationId:** `PostingAPI_CancelFbsPostingProduct`

**Отменить отправку некоторых товаров в отправлении**

Используйте метод, если вы не можете отправить часть продуктов из отправления.

Чтобы получить идентификаторы причин отмены `cancel_reason_id` при работе по схемам FBS или rFBS, используйте метод [/v2/posting/fbs/cancel-reason/list](#operation/PostingAPI_GetPostingFbsCancelReasonList).

Условно-доставленные отправления отменить нельзя.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `cancel_reason_id` | integer | ✓ | Идентификатор причины отмены отправления товара. |
| `cancel_reason_message` | string | ✓ | Обязательное поле. Дополнительная информация по отмене. |
| `items` | array | ✓ | Информация о товарах. |
| `posting_number` | string | ✓ | Идентификатор отправления. |

[Request example](examples/POST__v2_posting_fbs_product_cancel_req.json)

## Responses

### `200` Отправка отменена


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | string |  | Номер отправления. |

[Response 200](../_shared/examples/POST__v2_posting_fbs_product_cancel_200.json)

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
