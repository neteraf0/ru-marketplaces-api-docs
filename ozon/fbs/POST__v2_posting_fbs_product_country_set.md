# `POST` /v2/posting/fbs/product/country/set

**Tag:** [FBS](index.md)

**operationId:** `PostingAPI_SetCountryProductFbsPostingV2`

**Добавить информацию о стране-изготовителе товара**

Метод для добавления на продукт атрибута «Страна-изготовитель», если он не был указан.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `posting_number` | string | ✓ | Номер отправления. |
| `product_id` | integer | ✓ | Идентификатор товара в системе Ozon — `product_id`. |
| `country_iso_code` | string | ✓ | Двухбуквенный код добавляемой страны по стандарту ISO_3166-1.  Список доступных стран-изготовителей и их ISO коды можно получить с помощью метода [/v2/posting/fbs/product/country/list](#operation/PostingAPI_ListCountryProductFbsPostingV2).  |

[Request example](examples/POST__v2_posting_fbs_product_country_set_req.json)

## Responses

### `200` Страна-изготовитель добавлена


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `product_id` | integer |  | Идентификатор товара в системе Ozon — `product_id`. |
| `is_gtd_needed` | boolean |  | Признак того, что необходимо передать номер грузовой таможенной декларации (ГТД) для продукта и отправления. |

[Response 200](../_shared/examples/POST__v2_posting_fbs_product_country_set_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
