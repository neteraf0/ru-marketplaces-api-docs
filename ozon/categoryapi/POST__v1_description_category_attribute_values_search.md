# `POST` /v1/description-category/attribute/values/search

**Tag:** [CategoryAPI](index.md)

**operationId:** `DescriptionCategoryAPI_SearchAttributeValues`

**Поиск по справочным значениям характеристики**

Возвращает справочные значения характеристики по заданному значению `value` в запросе.

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
| `limit` | integer | ✓ | Количество значений в ответе: - максимум — 100, - минимум — 1.  |
| `type_id` | integer | ✓ | Идентификатор типа товара. Можно получить с помощью метода [/v1/description-category/tree](#operation/DescriptionCategoryAPI_GetTree). |
| `value` | string | ✓ | Значение, по которому система будет искать справочные значения. Минимум — 2 символа. |

[Request example](examples/POST__v1_description_category_attribute_values_search_req.json)

## Responses

### `200` Справочные значения характеристики.


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | array |  | Значения характеристики. |

[Response 200](../_shared/examples/POST__v1_description_category_attribute_values_search_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
