# `GET` /api/v1/feedback

**Tag:** [Feedbacks](index.md)

**Server:** `https://feedbacks-api.wildberries.ru`

**Get the Feedback by ID**

Описание метода

The method allows you to get a feedback by its ID


Request limit per one seller's account for all methods in the Feedbacks and Questions category:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 s | 3 requests | 333 ms | 6 requests |
| Service | 1 s | 3 requests | 333 ms | 6 requests |
| Base | 1 h | 5 requests | 12 min | 1 request |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `id` | query | string | ✓ | Feedback ID *Example: `G7Y9Y1kBAtKOitoBT_lV`* |

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object |  |  |
| `error` | boolean |  | Error presence |
| `errorText` | string |  | Error description |
| `additionalErrors` | array |  | Additional errors |

[Response 200](../_shared/examples/GET__api_v1_feedback_200.json)

- **401** Unauthorized
- **402** Payment Required
### `422` Error processing request parameters


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object |  |  |
| `error` | boolean |  | Error flag |
| `errorText` | string |  | Error description |
| `additionalErrors` | array |  | Additional errors |
| `requestId` | string |  |  |

[Response 422: ResponseGetFeedbackByIdErrEx](../_shared/examples/GET__api_v1_feedback_422_ResponseGetFeedbackByIdErrEx.json)

- **429** Too Many Requests
