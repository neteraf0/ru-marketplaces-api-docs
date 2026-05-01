# `POST` /v4/product/info/attributes

**Tag:** [ProductAPI](index.md)

**operationId:** `ProductAPI_GetProductAttributesV4`

**Получить описание характеристик товара**

Возвращает описание характеристик товаров по идентификатору и видимости. Товар можно искать по `offer_id`, `product_id` или `sku`.

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `filter` | productv4Filter |  | Фильтр по товарам. |
| `last_id` | string |  | Идентификатор последнего значения на странице. Оставьте это поле пустым при выполнении первого запроса.  Чтобы получить следующие значения, укажите `last_id` из ответа предыдущего запроса.  |
| `limit` | integer |  | Количество значений на странице. |
| `sort_by` | string |  | Параметр, по которому товары будут отсортированы: - `sku` — сортировка по идентификатору товара в системе Ozon; - `offer_id` — сортировка по артикулу товара; - `id` — сортировка по идентификатору товара; - `title` — сортировка по названию товара.  |
| `sort_dir` | string |  | Направление сортировки: - `asc` — по возрастанию, - `desc` — по убыванию.  |

[Request example](examples/POST__v4_product_info_attributes_req.json)

## Responses

### `200` Описание характеристик товара


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | array |  | Результаты запроса. |
| `last_id` | string |  | Идентификатор последнего значения на странице.  Чтобы получить следующие значения, укажите полученное значение в следующем запросе в параметре `last_id`.  |
| `total` | string |  | Количество товаров в списке. |

[Response 200](../_shared/examples/POST__v4_product_info_attributes_200.json)

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
