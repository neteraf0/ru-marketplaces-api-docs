# `GET` /api/v1/feedbacks/count

**Tag:** [Feedbacks](index.md)

**Server:** `https://feedbacks-api.wildberries.ru`

**Number of Feedbacks**

Описание метода

The method allows to get the number of feedbacks


Request limit per one seller's account for all methods in the Feedbacks and Questions category:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 s | 3 requests | 333 ms | 6 requests |
| Service | 1 s | 3 requests | 333 ms | 6 requests |
| Base | 1 h | 5 requests | 12 min | 1 request |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `dateFrom` | query | integer |  | The start date of the period in Unix timestamp format *Example: `1688465092`* |
| `dateTo` | query | integer |  | The end date of the period in Unix timestamp format *Example: `1688465092`* |
| `isAnswered` | query | boolean |  | If the feedback was answered:   - `true` — yes   - `false` — no  |

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | integer |  | Number of feedbacks *Example: `724583`* |
| `error` | boolean |  | Error presence |
| `errorText` | string |  | Error description |
| `additionalErrors` | array |  | Additional errors |

[Response 200](../_shared/examples/GET__api_v1_feedbacks_count_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object |  |  |
| `error` | boolean |  | Error flag |
| `errorText` | string |  | Error description |
| `additionalErrors` | array |  | Additional errors |
| `requestId` | string |  |  |

[Response 400: IsAnsweredErr400](../_shared/examples/GET__api_v1_questions_count_400_IsAnsweredErr400.json)


[Response 400: DateFromErr400](../_shared/examples/GET__api_v1_questions_count_400_DateFromErr400.json)


[Response 400: DateToErr400](../_shared/examples/GET__api_v1_questions_count_400_DateToErr400.json)

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
