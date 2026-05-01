# `GET` /api/v1/questions

**Tag:** [Questions](index.md)

**Server:** `https://feedbacks-api.wildberries.ru`

**Question List**

Описание метода

The method allows you to get a list of questions by the specified parameters with pagination and sorting. It is possible to get a maximum of 10,000 questions per query


Request limit per one seller's account for all methods in the Feedbacks and Questions category:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 s | 3 requests | 333 ms | 6 requests |
| Service | 1 s | 3 requests | 333 ms | 6 requests |
| Base | 1 h | 5 requests | 12 min | 1 request |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `isAnswered` | query | boolean | ✓ | The question is answered:   - `true` — yes   - `false` — no  |
| `nmId` | query | integer |  | WB article |
| `take` | query | integer | ✓ | Number of requested questions (the maximum possible value for the parameter is 10,000, and the total amount of `take` and `skip` parameters must not exceed 10,000)  |
| `skip` | query | integer | ✓ | Number of questions to skip (maximum possible value for the parameter is 10,000, and the total amount of `take` and `skip` parameters must not exceed 10,000)  |
| `order` | query | string |  | Sorting questions by date (`dateAsc`/`dateDesc`) |
| `dateFrom` | query | integer |  | The start date of the period in Unix timestamp format *Example: `1688465092`* |
| `dateTo` | query | integer |  | The end date of the period in Unix timestamp format *Example: `1688465092`* |

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object |  |  |
| `error` | boolean |  | Error presence |
| `errorText` | string |  | Error description |
| `additionalErrors` | array |  | Additional errors |

[Response 200](../_shared/examples/GET__api_v1_questions_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object |  |  |
| `error` | boolean |  | Error flag |
| `errorText` | string |  | Error description |
| `additionalErrors` | array |  | Additional errors |
| `requestId` | string |  |  |

[Response 400: FeedbackErr400](../_shared/examples/GET__api_v1_questions_400_FeedbackErr400.json)

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
