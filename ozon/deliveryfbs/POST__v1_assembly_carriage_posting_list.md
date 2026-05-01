# `POST` /v1/assembly/carriage/posting/list

**Tag:** [DeliveryFBS](index.md)

**operationId:** `AssemblyCarriagePostingList`

**Получить список отправлений в отгрузке**

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
| `filter` | v1AssemblyCarriagePostingListRequestFilter | ✓ | Фильтр. |
| `limit` | integer | ✓ | Количество значений на странице. |
## Responses

### `200` Список отправлений


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `can_print_mass_label` | boolean |  | `true`, если можно распечатать этикетки массово.  |
| `cursor` | string |  | Указатель для выборки следующих данных. Если параметр пустой, данных больше нет. |
| `postings` | array |  | Список отправлений. |

[Response 200](../_shared/examples/POST__v1_assembly_carriage_posting_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
