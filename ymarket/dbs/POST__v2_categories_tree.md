# `POST` /v2/categories/tree

**Tag:** [dbs](index.md)

**operationId:** `getCategoriesTree`

**Дерево категорий**

{% include notitle [access](../../_auto/method_scopes/getCategoriesTree.md) %}

Возвращает дерево категорий Маркета.

{% include notitle [limit](../../_auto/method_limits/getCategoriesTree.md) %}

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `language` | string (enum: RU, EN) |  | Язык:  * `RU` — русский.  * `EN` — английский.  |
## Responses

### `200` Категории Маркета.


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 200](../_shared/examples/POST__v2_categories_tree_200.json)

### `400` Запрос содержит неправильные данные. [Подробнее об ошибке](../../concepts/error-codes.md#400)


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 400](../_shared/examples/POST__v2_businesses__businessId__settings_400.json)

### `401` В запросе не указаны данные для авторизации. [Подробнее об ошибке](../../concepts/error-codes.md#401)


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 401](../_shared/examples/POST__v2_businesses__businessId__settings_400.json)

### `403` Данные для авторизации неверны или доступ к ресурсу запрещен. [Подробнее об ошибке](../../concepts/error-codes.md#403)


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 403](../_shared/examples/POST__v2_businesses__businessId__settings_400.json)

### `404` Запрашиваемый ресурс не найден. [Подробнее об ошибке](../../concepts/error-codes.md#404)


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 404](../_shared/examples/POST__v2_businesses__businessId__settings_400.json)

### `420` Превышено ограничение на доступ к ресурсу. [Подробнее об ошибке](../../concepts/error-codes.md#420)


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 420](../_shared/examples/POST__v2_businesses__businessId__settings_400.json)

### `500` Внутренняя ошибка Маркета. [Подробнее об ошибке](../../concepts/error-codes.md#500)


| Field | Type | Req | Description |
|-------|------|-----|-------------|

[Response 500](../_shared/examples/POST__v2_businesses__businessId__settings_400.json)
