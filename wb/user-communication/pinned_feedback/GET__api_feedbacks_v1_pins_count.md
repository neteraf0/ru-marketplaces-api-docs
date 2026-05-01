# `GET` /api/feedbacks/v1/pins/count

**Tag:** [Pinned Feedback](index.md)

**Server:** `https://feedbacks-api.wildberries.ru`

**Pinned and Unpinned Feedback Number**

Описание метода

The method returns the number of pinned and unpinned feedback for the period.


Request limit per one seller's account for all methods in the Feedbacks and Questions category:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 s | 3 requests | 333 ms | 6 requests |
| Service | 1 s | 3 requests | 333 ms | 6 requests |
| Base | 1 h | 5 requests | 12 min | 1 request |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `state` | query | string (enum: pinned, unpinned) |  | If the feedback is pinned:   - `pinned` — yes   - `unpinned` — no  *Example: `pinned`* |
| `pinOn` | query | string (enum: nm, imt) |  | Feedback pinning placement:   - `nm` — product card   - `imt` — group of merged product cards  *Example: `nm`* |
| `imtId` | query | integer |  | Merged product cards ID. The same for all WB article of group of merged product cards. Every product card has `imtId`, even if is not merged with any other card  *Example: `256971531`* |
| `nmId` | query | integer |  | WB article *Example: `177974151`* |
| `feedbackId` | query | integer |  | Feedback ID *Example: `789`* |
| `dateFrom` | query | string |  | The date the first feedback in the list was pinned  *Example: `2020-01-01T15:04:05Z`* |
| `dateTo` | query | string |  | The date the last feedback in the list was pinned  *Example: `2020-02-01T15:04:05Z`* |

## Responses

### `200` Success


[Response 200](../_shared/examples/GET__api_feedbacks_v1_pins_count_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `detail` | string |  | Error detail |
| `origin` | string | ✓ | WB internal service ID |
| `requestId` | string | ✓ | Request ID |
| `status` | integer | ✓ | HTTP status code |
| `title` | string | ✓ | Error title |

[Response 400](../_shared/examples/GET__api_feedbacks_v1_pins_400.json)

- **401** Unauthorized
- **429** Too Many Requests
