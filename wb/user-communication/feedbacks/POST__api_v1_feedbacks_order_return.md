# `POST` /api/v1/feedbacks/order/return

**Tag:** [Feedbacks](index.md)

**Server:** `https://feedbacks-api.wildberries.ru`

**Return Product by Feedback ID**

Описание метода

The method allows requesting a return for a product for which a feedback has been left.
Return is available for feedbacks with `"isAbleReturnProductOrders": true`


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
| `feedbackId` | string |  | Feedback ID |

[Request example](examples/POST__api_v1_feedbacks_order_return_req.json)

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object |  |  |
| `error` | boolean |  | Error presence |
| `errorText` | string |  | Error description |
| `additionalErrors` | array |  | Additional errors |

[Response 200](../_shared/examples/POST__api_v1_feedbacks_order_return_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object |  |  |
| `error` | boolean |  | Error flag |
| `errorText` | string |  | Error description |
| `additionalErrors` | array |  | Additional errors |
| `requestId` | string |  |  |

[Response 400: FeedbackErr400](../_shared/examples/POST__api_v1_feedbacks_order_return_400_FeedbackErr400.json)


[Response 400: RequestBodyErr400](../_shared/examples/POST__api_v1_feedbacks_order_return_400_RequestBodyErr400.json)


[Response 400: RequestIDErr400](../_shared/examples/POST__api_v1_feedbacks_order_return_400_RequestIDErr400.json)

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

[Response 422: responseInaccessibleBackGoodError422](../_shared/examples/POST__api_v1_feedbacks_order_return_422_responseInaccessibleBackGoodError422.json)


[Response 422: responseUnsuccessfullyBackGoodError422](../_shared/examples/POST__api_v1_feedbacks_order_return_422_responseUnsuccessfullyBackGoodError422.json)

- **429** Too Many Requests
