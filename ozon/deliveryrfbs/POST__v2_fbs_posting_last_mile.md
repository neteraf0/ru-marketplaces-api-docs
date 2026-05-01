# `POST` /v2/fbs/posting/last-mile

**Tag:** [DeliveryrFBS](index.md)

**operationId:** `PostingAPI_FbsPostingLastMile`

**Изменить статус на «Последняя миля»**

Перед изменением статуса проверьте текущий статус отправления методом /v3/posting/fbs/get. Изменение статуса происходит асинхронно.

Перевести отправление в статус «Последняя миля», если используется сторонняя служба доставки.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `posting_number` | array | ✓ | Идентификатор отправления. |

[Request example](examples/POST__v2_fbs_posting_last_mile_req.json)

## Responses

### `200` Статус изменён


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | array |  | Результат работы метода. |

[Response 200](../_shared/examples/POST__v2_fbs_posting_last_mile_200.json)

### `400` Invalid parameter


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 400](../_shared/examples/POST__v1_roles_default.json)

### `403` Access denied


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 403](../_shared/examples/POST__v1_roles_default.json)

### `404` Response not found


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 404](../_shared/examples/POST__v1_roles_default.json)

### `409` Request conflict


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 409](../_shared/examples/POST__v1_roles_default.json)

### `500` Internal server error


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 500](../_shared/examples/POST__v1_roles_default.json)
