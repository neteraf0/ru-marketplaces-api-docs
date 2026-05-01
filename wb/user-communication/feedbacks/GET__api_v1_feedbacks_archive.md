# `GET` /api/v1/feedbacks/archive

**Tag:** [Feedbacks](index.md)

**Server:** `https://feedbacks-api.wildberries.ru`

**List of Archived Feedbacks**

Описание метода

The method allows you to get a list of archived feedbacks.
The feedback becomes archived if:
  - A response to the feedback is received.
  - No response to the feedback is received within 30 days.
  - The feedback contains no text or photos.


Request limit per one seller's account for all methods in the Feedbacks and Questions category:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 s | 3 requests | 333 ms | 6 requests |
| Service | 1 s | 3 requests | 333 ms | 6 requests |
| Base | 1 h | 5 requests | 12 min | 1 request |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `nmId` | query | integer |  | WB article *Example: `14917842`* |
| `take` | query | integer | ✓ | Number of feedbacks (max. 5 000) *Example: `1`* |
| `skip` | query | integer | ✓ | Number of feedbacks for skip |
| `order` | query | string (enum: dateAsc, dateDesc) |  | Sorting of feedbacks by date (dateAsc/dateDesc) |

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object |  |  |
| `error` | boolean |  | Error presence |
| `errorText` | string |  | Error description |
| `additionalErrors` | array |  | Additional errors |

[Response 200](../_shared/examples/GET__api_v1_feedbacks_archive_200.json)

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
