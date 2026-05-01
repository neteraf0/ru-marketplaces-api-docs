# `PATCH` /api/v1/feedbacks/answer

**Tag:** [Feedbacks](index.md)

**Server:** `https://feedbacks-api.wildberries.ru`

**Edit Response to Feedback**

Описание метода

Allows you to edit an already sent response to the feedback.

You can edit the response only once within 60 days.

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
| `text` | string | ✓ | Reply text *Example: `Спасибо за Ваш отзыв, он очень важен для нас!`* |
## Responses

- **204** Success
- **401** Unauthorized
- **402** Payment Required
- **429** Too Many Requests
