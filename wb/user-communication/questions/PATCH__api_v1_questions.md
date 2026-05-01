# `PATCH` /api/v1/questions

**Tag:** [Questions](index.md)

**Server:** `https://feedbacks-api.wildberries.ru`

**Working with Questions**

Описание метода

Depending on the request body, you can:
- View question.
- Reject question.
- Answer question or edit the answer.

It is possible to edit a response to a question within 2 months (60 days), after the response has been submitted and only once.


Request limit per one seller's account for all methods in the Feedbacks and Questions category:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 s | 3 requests | 333 ms | 6 requests |
| Service | 1 s | 3 requests | 333 ms | 6 requests |
| Base | 1 h | 5 requests | 12 min | 1 request |


## Request Body

Content-Type: `application/json`


[Request: ViewQuestion](examples/PATCH__api_v1_questions_req_ViewQuestion.json)


[Request: RejectQuestion](examples/PATCH__api_v1_questions_req_RejectQuestion.json)


[Request: AnswerQuestionOrEditAnswer](examples/PATCH__api_v1_questions_req_AnswerQuestionOrEditAnswer.json)

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object |  |  |
| `error` | boolean |  | Error flag |
| `errorText` | string |  | Error description |
| `additionalErrors` | array |  | Additional errors |

[Response 200](../_shared/examples/PATCH__api_v1_questions_200.json)

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

### `404` Not found


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object |  |  |
| `error` | boolean |  | Error flag |
| `errorText` | string |  | Error description |
| `additionalErrors` | array |  | Additional errors |
| `requestId` | string |  |  |

[Response 404: FeedbackErr404](../_shared/examples/PATCH__api_v1_questions_404_FeedbackErr404.json)

- **429** Too Many Requests
