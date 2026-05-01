# `GET` /api/v1/new-feedbacks-questions

**Tag:** [Questions](index.md)

**Server:** `https://feedbacks-api.wildberries.ru`

**Unseen Feedbacks and Questions**

Описание метода

The method displays information about the seller's unseen feedbacks and questions


Request limit per one seller's account for all methods in the Feedbacks and Questions category:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 s | 3 requests | 333 ms | 6 requests |
| Service | 1 s | 3 requests | 333 ms | 6 requests |
| Base | 1 h | 5 requests | 12 min | 1 request |


## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object |  |  |
| `error` | boolean |  | Error presence |
| `errorText` | string |  | Error description |
| `additionalErrors` | array |  | Additional errors |

[Response 200](../_shared/examples/GET__api_v1_new_feedbacks_questions_200.json)

- **401** Unauthorized
- **402** Payment Required
### `403` Access denied


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object |  |  |
| `error` | boolean |  | Error flag |
| `errorText` | string |  | Error description |
| `additionalErrors` | array |  | Additional errors |
| `requestId` | string |  |  |

[Response 403: FeedbackErr403](../_shared/examples/GET__api_v1_new_feedbacks_questions_403_FeedbackErr403.json)

- **429** Too Many Requests
