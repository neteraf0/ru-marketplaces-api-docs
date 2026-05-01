# `POST` /api/feedbacks/v1/pins

**Tag:** [Pinned Feedback](index.md)

**Server:** `https://feedbacks-api.wildberries.ru`

**Pin Feedback**

Описание метода

The method allows to pin the feedback to a group of merged product cards or to a product card.
To get feedback ID, use the [List of pinned and unpinned feedback](./user-communication#tag/Pinned-Feedback/paths/~1api~1feedbacks~1v1~1pins/get) method.

The method is available for [Jam subscription](https://seller.wildberries.ru/monetization/jam) or **Pin a feedback** option in the [tariff constructor](https://seller.wildberries.ru/tariff-constructor).


Request limit per one seller's account for all methods in the Feedbacks and Questions category:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 s | 3 requests | 333 ms | 6 requests |
| Service | 1 s | 3 requests | 333 ms | 6 requests |
| Base | 1 h | 5 requests | 12 min | 1 request |


## Request Body

Content-Type: `application/json`

*Array of:*

  | Field | Type | Req | Description |
  |-------|------|-----|-------------|
  | `pinMethod` | string (enum: tariff, subscription) | ✓ | Pinning methods:   - `subscription` — Jam subscription   - `tariff` — tariff option  *Example: `subscription`* |
  | `pinOn` | string (enum: nm, imt) | ✓ | Feedback pinning placement:   - `nm` — product card   - `imt` — group of merged product cards  *Example: `imt`* |
  | `feedbackId` | string | ✓ | Feedback ID *Example: `DibuRAImknLyiqgzvGcU`* |
## Responses

### `200` Success


[Response 200](../_shared/examples/POST__api_feedbacks_v1_pins_200.json)

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
### `403` Access denied


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `detail` | string |  | Error detail |
| `origin` | string | ✓ | WB internal service ID |
| `requestId` | string | ✓ | Request ID |
| `status` | integer | ✓ | HTTP status code |
| `title` | string | ✓ | Error title |

[Response 403](../_shared/examples/POST__api_feedbacks_v1_pins_403.json)

- **429** Too Many Requests
