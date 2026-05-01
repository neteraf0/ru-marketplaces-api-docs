# `POST` /v1/posting/fbs/split

**Tag:** [DeliveryFBS](index.md)

**operationId:** `FbsSplit`

**Разделить заказ на отправления без сборки**

## Request Body

## Responses

### `200` Заказ разделён


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `parent_posting` | v1PostingFbsSplitResponsePostingParent |  | Информация об изначальном отправлении. |
| `postings` | array |  | Список отправлений, на которые разделился заказ. |

[Response 200](../_shared/examples/POST__v1_posting_fbs_split_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
