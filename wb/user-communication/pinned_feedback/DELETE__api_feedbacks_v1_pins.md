# `DELETE` /api/feedbacks/v1/pins

**Tag:** [Pinned Feedback](index.md)

**Server:** `https://feedbacks-api.wildberries.ru`

**Unpin Feedback**

Описание метода

The method allows to unpin the feedback in a group of merged product cards or a product card.
To get `pinId` — feedback pinning operation ID, use the [List of pinned and unpinned feedback](./user-communication#tag/Pinned-Feedback/paths/~1api~1feedbacks~1v1~1pins/get) method.


Request limit per one seller's account for all methods in the Feedbacks and Questions category:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 s | 3 requests | 333 ms | 6 requests |
| Service | 1 s | 3 requests | 333 ms | 6 requests |
| Base | 1 h | 5 requests | 12 min | 1 request |


## Request Body

Content-Type: `application/json`

*Array of:*
  `integer`
## Responses

### `200` Success


[Response 200](../_shared/examples/DELETE__api_feedbacks_v1_pins_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `detail` | string |  | Error detail |
| `origin` | string | ✓ | WB internal service ID |
| `requestId` | string | ✓ | Request ID |
| `status` | integer | ✓ | HTTP status code |
| `title` | string | ✓ | Error title |

[Response 400](../_shared/examples/POST__api_feedbacks_v1_pins_400.json)

- **401** Unauthorized
- **429** Too Many Requests
