# `POST` /v1/assembly/fbs/product/list

**Tag:** [DeliveryFBS](index.md)

**operationId:** `AssemblyFbsProductList`

**Получить список товаров в отправлениях**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `filter` | v1AssemblyFbsProductListRequestFilter | ✓ | Фильтр. |
| `limit` | integer | ✓ | Количество значений на странице. |
| `offset` | integer |  | Количество элементов, которое будет пропущено в ответе. Например, если `offset = 10`, ответ начнётся с 11 найденного элемента. |
| `sort_dir` | v1AssemblyFbsProductListRequestSortDirEnum |  | Направление сортировки:  - `ASC` — по возрастанию,  - `DESC` — по убыванию.  |
## Responses

### `200` Список товаров в отправлениях


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `has_next` | boolean |  | Признак, что в ответе вернули не все товары:  - `true` — сделайте повторный запрос с другим значением `offset`, чтобы получить остальные значения; - `false` — ответ содержит все значения.  |
| `products` | array |  | Список товаров. |
| `products_count` | integer |  | Количество товаров. |

[Response 200](../_shared/examples/POST__v1_assembly_fbs_product_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
