# `POST` /v1/assembly/fbs/posting/list

**Tag:** [DeliveryFBS](index.md)

**operationId:** `AssemblyFbsPostingList`

**Получить список отправлений**

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
| `filter` | v1AssemblyFbsPostingListRequestFilter | ✓ | Фильтр. |
| `limit` | integer | ✓ | Количество значений на странице. |
| `sort_dir` | v1AssemblyFbsPostingListRequestSortDirEnum | ✓ | Направление сортировки:  - `ASC` — по возрастанию,  - `DESC` — по убыванию.  |
## Responses

### `200` Список отправлений


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `cursor` | string |  | Указатель для выборки следующих данных. Если параметр пустой, данных больше нет. |
| `cutoff` | string |  | Время, до которого продавцу нужно собрать заказ. |
| `postings` | array |  | Список отправлений. |

[Response 200](../_shared/examples/POST__v1_assembly_fbs_posting_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
