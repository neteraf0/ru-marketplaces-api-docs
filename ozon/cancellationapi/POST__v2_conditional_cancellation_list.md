# `POST` /v2/conditional-cancellation/list

**Tag:** [CancellationAPI](index.md)

**operationId:** `CancellationAPI_GetConditionalCancellationListV2`

**Получить список заявок на отмену rFBS**

Метод для получения списка заявок на отмену rFBS-заказов.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `filters` | GetConditionalCancellationListV2RequestFilters |  | Фильтры. |
| `last_id` | integer |  | Идентификатор последнего значения на странице. Оставьте это поле пустым при выполнении первого запроса.  Чтобы получить следующие значения, укажите `last_id` из ответа предыдущего запроса.  |
| `limit` | integer | ✓ | Количество заявок в ответе. |
| `with` | GetConditionalCancellationListV2RequestWith |  | Дополнительная информация. |

[Request example](examples/POST__v2_conditional_cancellation_list_req.json)

## Responses

### `200` Список заявок на отмену


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `counter` | integer |  | Cчётчик заявок в статусе `ON_APPROVAL`. |
| `last_id` | integer |  | Идентификатор последнего значения на странице.  Чтобы получить следующие значения, передайте полученное значение в следующем запросе в параметре `last_id`.  |
| `result` | array |  | Информация о заявках на отмену. |

[Response 200](../_shared/examples/POST__v2_conditional_cancellation_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
