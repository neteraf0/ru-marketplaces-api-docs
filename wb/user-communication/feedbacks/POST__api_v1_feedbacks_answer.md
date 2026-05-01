# `POST` /api/v1/feedbacks/answer

**Tag:** [Feedbacks](index.md)

**Server:** `https://feedbacks-api.wildberries.ru`

**Reply to Feedback**

Описание метода

Allows you to respond to the feedback.

 There is no validation by `feedback ID`: if an incorrect value is provided in the request, you will not receive an error.


Request limit per one seller's account for all methods in the Feedbacks and Questions category:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 s | 3 requests | 333 ms | 6 requests |
| Service | 1 s | 3 requests | 333 ms | 6 requests |
| Base | 1 h | 5 requests | 12 min | 1 request |


## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `id` | string | ✓ | Feedback ID *Example: `J2FMRjUj6hwvwCElqssz`* |
| `text` | string | ✓ | Reply text *Example: `Спасибо за Ваш отзыв!`* |
## Responses

- **204** Success
### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `title` | string |  | Error title |
| `requestId` | string |  | Unique request ID |
| `origin` | string |  | WB internal service ID |
| `detail` | string |  | Error details |

[Response 400: contentTypeHeaderNotSpecified](../_shared/examples/POST__api_v1_feedbacks_answer_400_contentTypeHeaderNotSpecified.json)


[Response 400: incorrectContentTypeHeader](../_shared/examples/POST__api_v1_feedbacks_answer_400_incorrectContentTypeHeader.json)


[Response 400: incorrectContentType](../_shared/examples/POST__api_v1_feedbacks_answer_400_incorrectContentType.json)


[Response 400: invalidJsonSyntax](../_shared/examples/POST__api_v1_feedbacks_answer_400_invalidJsonSyntax.json)

- **401** Unauthorized
- **402** Payment Required
- **429** Too Many Requests
