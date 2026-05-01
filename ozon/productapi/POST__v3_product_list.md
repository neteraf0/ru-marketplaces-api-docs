# `POST` /v3/product/list

**Tag:** [ProductAPI](index.md)

**operationId:** `ProductAPI_GetProductList`

**Список товаров**

Метод для получения списка всех товаров.

Если вы используете фильтр по идентификатору `offer_id` или `product_id`, остальные параметры заполнять не обязательно.
За один раз вы можете использовать только одну группу идентификаторов, не больше 1000 товаров.

Если вы не используете для отображения идентификаторы, укажите `limit` и `last_id` в следующих запросах.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `filter` | productv3GetProductListRequestFilter |  | Фильтр по товарам. |
| `last_id` | string |  | Идентификатор последнего значения на странице. При первом запросе оставьте это поле пустым.  Чтобы получить следующие значения, укажите `last_id` из ответа предыдущего запроса.  |
| `limit` | integer |  | Количество значений на странице. Минимум — 1, максимум — 1000. |

[Request example](examples/POST__v3_product_list_req.json)

## Responses

### `200` Список товаров


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | productv3GetProductListResponseResult |  | Результат. |

[Response 200](../_shared/examples/POST__v3_product_list_200.json)

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
