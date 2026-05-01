# `POST` /v1/assembly/carriage/product/list

**Tag:** [DeliveryFBS](index.md)

**operationId:** `AssemblyCarriageProductList`

**Получить список товаров в отгрузке**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `cursor` | string |  | Указатель для выборки следующих данных. |
| `filter` | v1AssemblyCarriageProductListRequestFilter | ✓ | Фильтр. |
| `limit` | integer | ✓ | Количество значений на странице. |
## Responses

### `200` Список товаров


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `cursor` | string |  | Указатель для выборки следующих данных. Если параметр пустой, данных больше нет. |
| `products` | array |  | Список товаров. |

[Response 200](../_shared/examples/POST__v1_assembly_carriage_product_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
