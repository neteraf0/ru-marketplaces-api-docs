# `POST` /v1/rating/index/fbs/posting/list

**Tag:** [SellerRating](index.md)

**operationId:** `RatingAPI_ListFBSRatingIndexPostingsV1`

**Список отправлений, которые повлияли на индекс ошибок FBS и rFBS**

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
| `filter` | ListFBSRatingIndexPostingsV1RequestFilter | ✓ | Фильтр. |
| `limit` | integer | ✓ | Количество значений в ответе. |
## Responses

### `200` Список отправлений


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `cursor` | string |  | Указатель для выборки следующих данных. |
| `errors` | array |  | Отправления, которые повлияли на индекс. |
| `has_next` | boolean |  | `true`, если в ответе вернулись не все отправления.  |

[Response 200](../_shared/examples/POST__v1_rating_index_fbs_posting_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
