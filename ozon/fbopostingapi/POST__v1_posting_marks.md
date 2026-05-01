# `POST` /v1/posting/marks

**Tag:** [FboPostingAPI](index.md)

**operationId:** `PostingAPI_PostingMarks`

**Получить маркировки экземпляров из отправления**

Возвращает статусы выдачи экземпляров и коды маркировки «Честный ЗНАК» для каждого отправления.

Укажите в чеке и выведите из оборота маркировки экземпляров из параметра `issued_exemplars` в ответе.

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `posting_numbers` | array |  | Идентификаторы отправлений. |
## Responses

### `200` Список экземпляров отправления с маркировками


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `invalid_postings` | array |  | Список неверных идентификаторов отправлений. |
| `issued_exemplars` | array |  | Список выданных покупателям экземпляров товаров. |
| `non_issued_exemplars` | array |  | Список не выданных покупателям экземпляров товаров. |

[Response 200](../_shared/examples/POST__v1_posting_marks_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
