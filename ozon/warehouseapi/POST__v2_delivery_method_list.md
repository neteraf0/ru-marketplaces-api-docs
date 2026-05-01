# `POST` /v2/delivery-method/list

**Tag:** [WarehouseAPI](index.md)

**operationId:** `WarehouseAPI_DeliveryMethodListV2`

**Список методов доставки realFBS-склада**

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
| `filter` | DeliveryMethodListV2RequestFilter |  | Фильтр для поиска методов доставки. |
| `limit` | integer | ✓ | Количество значений в ответе. |
| `sort_dir` | DeliveryMethodListV2RequestSortDirEnum |  | Направление сортировки: - `ASC` — по возрастанию; - `DESC` — по убыванию.  |

[Request example](examples/POST__v2_delivery_method_list_req.json)

## Responses

### `200` Список методов склада


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `cursor` | string |  | Указатель для выборки следующих данных. |
| `has_next` | boolean |  | `true`, если в ответе вернули не все методы доставки.  |
| `delivery_methods` | array |  | Методы доставки. |

[Response 200](../_shared/examples/POST__v2_delivery_method_list_200.json)

### `400` Неверный параметр


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 400](../_shared/examples/POST__v1_roles_default.json)

### `403` Доступ запрещён


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 403](../_shared/examples/POST__v1_roles_default.json)

### `404` Ответ не найден


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 404](../_shared/examples/POST__v1_roles_default.json)

### `409` Конфликт запроса


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 409](../_shared/examples/POST__v1_roles_default.json)

### `500` Внутренняя ошибка сервера


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response 500](../_shared/examples/POST__v1_roles_default.json)
