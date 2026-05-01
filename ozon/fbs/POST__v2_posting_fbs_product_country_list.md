# `POST` /v2/posting/fbs/product/country/list

**Tag:** [FBS](index.md)

**operationId:** `PostingAPI_ListCountryProductFbsPostingV2`

**Список доступных стран-изготовителей**

Метод для получения списка доступных стран-изготовителей и их ISO кодов.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `name_search` | string |  | Фильтрация по строке. |

[Request example](examples/POST__v2_posting_fbs_product_country_list_req.json)

## Responses

### `200` Список доступных стран-изготовителей


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | array |  | Список стран-изготовителей и ISO коды. |

[Response 200](../_shared/examples/POST__v2_posting_fbs_product_country_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
