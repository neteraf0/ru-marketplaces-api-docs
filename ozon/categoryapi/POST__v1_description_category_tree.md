# `POST` /v1/description-category/tree

**Tag:** [CategoryAPI](index.md)

**operationId:** `DescriptionCategoryAPI_GetTree`

**Дерево категорий и типов товаров**

Возвращает категории и типы для товаров в виде дерева.

Создание товаров доступно только в категориях последнего уровня, сравните именно их с категориями на своей площадке.
Категории не создаются по запросу пользователя.


  Внимательно выбирайте категорию для товара: для разных категорий применяется разный размер комиссии.


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `language` | languageLanguage |  | Язык в ответе: - `EN` — английский, - `RU` — русский, - `TR` — турецкий, - `ZH_HANS` — китайский.  По умолчанию используется русский язык.  |

[Request example](examples/POST__v1_description_category_tree_req.json)

## Responses

### `200` Дерево категорий


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | array |  | Список категорий. |

[Response 200](../_shared/examples/POST__v1_description_category_tree_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
