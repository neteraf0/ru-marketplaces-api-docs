# `POST` /v1/posting/digital/list

**Tag:** [Digital](index.md)

**operationId:** `ListPostingCodes`

**Получить список отправлений**


Метод устаревает. Переключитесь на /v2/posting/digital/list.

Возвращает список отправлений, по которым нужно загрузить коды цифровых товаров. Метод доступен только продавцам, работающим с цифровыми товарами.

Чтобы получить список отправлений в любом статусе, воспользуйтесь методом [/v2/posting/fbo/list](#operation/PostingAPI_GetFboPostingList).

> ⚠️ **Deprecated**

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `dir` | DirEnum |  | Направление сортировки: - `ASC` — по возрастанию, - `DESC` — по убыванию.  |
| `filter` | ListPostingCodesRequestFilter |  | Фильтр для поиска отправлений. |
| `limit` | integer |  | Количество значений в ответе:  - максимум — 1000,  - минимум — 1.  |
| `offset` | integer |  | Количество элементов, которое будет пропущено в ответе. Например, если `offset = 10`, то ответ начнётся с 11-го найденного элемента. Максимальное значение — 20000. |
| `with` | ListPostingCodesRequestWithParams |  | Дополнительные поля, которые нужно добавить в ответ. |

[Request example](examples/POST__v1_posting_digital_list_req.json)

## Responses

### `200` Список отправлений


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | array |  | Список отправлений. |

[Response 200](../_shared/examples/POST__v1_posting_digital_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
