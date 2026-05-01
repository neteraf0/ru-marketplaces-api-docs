# `POST` /v1/description-category/attribute/values

**Tag:** [CategoryAPI](index.md)

**operationId:** `DescriptionCategoryAPI_GetAttributeValues`

**Справочник значений характеристики**

Возвращает справочник значений характеристики.

Узнать, есть ли вложенный справочник, можно через метод [/v1/description-category/attribute](#operation/DescriptionCategoryAPI_GetAttributes).

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `attribute_id` | integer | ✓ | Идентификатор характеристики. Можно получить с помощью метода [/v1/description-category/attribute](#operation/DescriptionCategoryAPI_GetAttributes). |
| `description_category_id` | integer | ✓ | Идентификатор категории. Можно получить с помощью метода [/v1/description-category/tree](#operation/DescriptionCategoryAPI_GetTree). |
| `language` | languageLanguage |  | Язык в ответе: - `EN` — английский, - `RU` — русский, - `TR` — турецкий, - `ZH_HANS` — китайский.  По умолчанию используется русский язык.  |
| `last_value_id` | integer |  | Идентификатор справочника, с которого нужно начать ответ. Если `last_value_id` — 10, то в ответе будут справочники, начиная с одиннадцатого. |
| `limit` | integer | ✓ | Количество значений в ответе: - максимум — 2000, - минимум — 1.  |
| `type_id` | integer | ✓ | Идентификатор типа товара. Можно получить с помощью метода [/v1/description-category/tree](#operation/DescriptionCategoryAPI_GetTree). |

[Request example](examples/POST__v1_description_category_attribute_values_req.json)

## Responses

### `200` Справочник характеристик


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `has_next` | boolean |  | Признак, что в ответе вернулась только часть значений характеристики: - `true` — сделайте повторный запрос с новым параметром `last_value_id` для получения остальных значений; - `false` — ответ содержит все значения характеристики.  |
| `result` | array |  | Значения характеристики. |

[Response 200](../_shared/examples/POST__v1_description_category_attribute_values_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
