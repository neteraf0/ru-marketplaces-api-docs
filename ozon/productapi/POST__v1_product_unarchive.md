# `POST` /v1/product/unarchive

**Tag:** [ProductAPI](index.md)

**operationId:** `ProductAPI_ProductUnarchive`

**Вернуть товар из архива**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `product_id` | array | ✓ | Список идентификаторов товаров в системе Ozon — `product_id`.  Вы можете передать до 100 идентификаторов за раз.   В сутки можно восстановить из архива не больше 100 товаров, которые были архивированы автоматически.   Лимит обновляется в 03:00 по московскому времени. На разархивацию товаров, перенесённых в архив вручную, ограничений нет.  |

[Request example](examples/POST__v1_product_unarchive_req.json)

## Responses

### `200` Товар из архива возвращён


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | boolean |  | Результат обработки запроса. `true`, если запрос выполнен без ошибок. |

[Response 200](../_shared/examples/POST__v1_product_archive_200.json)

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
