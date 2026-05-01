# `POST` /v1/description-category/attribute

**Tag:** [CategoryAPI](index.md)

**operationId:** `DescriptionCategoryAPI_GetAttributes`

**Список характеристик категории**

Получение характеристик для указанных категории и типа товара.

Если у `dictionary_id` значение `0`, у атрибута нет вложенных справочников.
Если значение другое, то справочники есть. Запросите их методом [/v1/description-category/attribute/values](#operation/DescriptionCategoryAPI_GetAttributeValues).

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `description_category_id` | integer | ✓ | Идентификатор категории. Можно получить с помощью метода [/v1/description-category/tree](#operation/DescriptionCategoryAPI_GetTree). |
| `language` | languageLanguage |  | Язык в ответе: - `EN` — английский, - `RU` — русский, - `TR` — турецкий, - `ZH_HANS` — китайский.  По умолчанию используется русский язык.  |
| `type_id` | integer | ✓ | Идентификатор типа товара. Можно получить с помощью метода [/v1/description-category/tree](#operation/DescriptionCategoryAPI_GetTree). |

[Request example](examples/POST__v1_description_category_attribute_req.json)

## Responses

### `200` Характеристики категории


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | array |  | Результат запроса. |

[Response 200](../_shared/examples/POST__v1_description_category_attribute_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
