# `POST` /v1/pass/list

**Tag:** [Pass](index.md)

**operationId:** `PassList`

**Список пропусков**

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `cursor` | string |  | Указатель для выборки следующих данных. |
| `filter` | ArrivalPassListRequestFilter |  | Фильтры. |
| `limit` | integer | ✓ | Ограничение по количеству записей в ответе. По умолчанию — 1000. Максимум — 1000.  |

[Request example](examples/POST__v1_pass_list_req.json)

## Responses

### `200` Список пропусков


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `arrival_passes` | array |  | Список пропусков для перевозки. |
| `cursor` | string |  | Указатель для выборки следующих данных. Если параметр пустой, данных больше нет.  |

[Response 200](../_shared/examples/POST__v1_pass_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
