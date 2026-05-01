# `POST` /v3/posting/fbo/list

**Tag:** [FBO](index.md)

**operationId:** `PostingFboList`

**Получить список отправлений**

Возвращает список отправлений за указанный период времени.
Если период больше года, вернётся ошибка `PERIOD_IS_TOO_LONG`.

Дополнительно можно отфильтровать отправления по их статусу.

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
| `filter` | posting.v3.PostingFboListRequest.Filter |  | Фильтр для поиска отправлений. |
| `limit` | integer |  | Количество значений в ответе. |
| `sort_dir` | posting.v3.PostingFboListRequest.SortDir.Enum |  | Направление сортировки: - `ASC` — по возрастанию; - `DESC` — по убыванию.  |
| `translit` | boolean |  | `true`, чтобы включить транслитерацию адреса из кириллицы в латиницу.  |
| `with` | posting.v3.PostingFboListRequest.With |  | Дополнительные поля, которые нужно добавить в ответ. |

[Request example](examples/POST__v3_posting_fbo_list_req.json)

## Responses

### `200` Список отправлений


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `cursor` | string |  | Указатель для выборки следующих данных. |
| `has_next` | boolean |  | `true`, если в ответе вернулись не все отправления.  |
| `postings` | array |  | Список отправлений. |

[Response 200](../_shared/examples/POST__v3_posting_fbo_list_200.json)

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
