# `POST` /v4/posting/fbs/list

**Tag:** [FBS](index.md)

**operationId:** `PostingFbsList`

**Получить список отправлений**

Возвращает список отправлений за указанный период времени — он должен быть не больше одного года.

 Чтобы получать актуальную дату отгрузки, регулярно обновляйте информацию об отправлениях или подключите [пуш-уведомления](#tag/push_start).

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
| `filter` | posting.v4.PostingFbsListRequest.Filter | ✓ | Фильтр. |
| `limit` | integer | ✓ | Количество значений в ответе. |
| `sort_dir` | posting.v4.PostingFbsListRequest.SortDir.Enum |  | Направление сортировки: - `ASC` — по возрастанию; - `DESC` — по убыванию.  |
| `translit` | boolean |  | `true`, чтобы включить транслитерацию адреса из кириллицы в латиницу.  |
| `with` | posting.v4.PostingFbsListRequest.With |  | Дополнительные поля, которые нужно добавить в ответ. |

[Request example](examples/POST__v4_posting_fbs_list_req.json)

## Responses

### `200` Список отправлений


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `cursor` | string |  | Указатель для выборки следующих данных. |
| `has_next` | boolean |  | `true`, если в ответе вернулись не все отправления.  |
| `postings` |  |  | Список отправлений. |

[Response 200](../_shared/examples/POST__v4_posting_fbs_list_200.json)

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
