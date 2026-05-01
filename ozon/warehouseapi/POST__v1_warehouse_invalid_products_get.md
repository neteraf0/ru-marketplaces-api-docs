# `POST` /v1/warehouse/invalid-products/get

**Tag:** [WarehouseAPI](index.md)

**operationId:** `WarehouseInvalidProductsGet`

**Получить список товаров с ограничениями по доставке**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `Client-Id` | header | string | ✓ | Идентификатор клиента. |
| `Api-Key` | header | string | ✓ | API-ключ. |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `last_id` | integer |  | Идентификатор последнего значения на странице. При первом запросе оставьте это поле пустым.   Чтобы получить следующие значения, укажите `last_id` из ответа предыдущего запроса.  |
| `warehouse_id` | integer | ✓ | Идентификатор склада. Получите значение параметра методом [/v1/warehouse/warehouses-with-invalid-products](#operation/WarehouseWithInvalidProducts). |
## Responses

### `200` Список товаров с ограничениями


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `has_next` | boolean |  | `true`, если в ответе вернулись не все товары.  |
| `last_id` | integer |  | Идентификатор последнего значения на странице. Чтобы получить следующие значения, передайте полученное значение в следующем запросе в параметре `last_id`. |
| `validation_results` | array |  | Результат проверки. |
| `warehouse_id` | integer |  | Идентификатор склада. |

[Response 200](../_shared/examples/POST__v1_warehouse_invalid_products_get_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
