# `GET` /api/v1/seller/events

**Tag:** [Buyers Chat](index.md)

**Chat Events**

Описание метода

Returns an event list for all chats.

To retrieve all events:
  1. Make the first request without a `next` parameter.
  2. Repeat the request with the `next` parameter value from the previous response until `totalEvents` becomes `0`. This will indicate that you have received all events.


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 10 s | 10 requests | 1 s | 10 requests |
| Service | 10 s | 10 requests | 1 s | 10 requests |
| Base | 1 h | 1 request | 1 h | 1 request |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `next` | query | integer |  | Paginator. Retrieve the next data packet starting from this moment. Format: Unix timestamp **with milliseconds**  |

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | EventsResult |  |  |
| `errors` | array |  | Errors, if any |

[Response 200](../_shared/examples/GET__api_v1_seller_events_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `status` | number |  | HTTP status code |
| `title` | string |  | Error title |
| `origin` | string |  | WB internal service ID |
| `detail` | string |  | Error details |
| `requestId` | string |  | Unique request ID |
| `error` | string |  | Error text |

[Response 400: IncorrectNextParameter](../_shared/examples/GET__api_v1_seller_events_400_IncorrectNextParameter.json)


[Response 400: IncorrectNextParameter1](../_shared/examples/GET__api_v1_seller_events_400_IncorrectNextParameter1.json)

- **401** Unauthorized
- **402** Payment Required
- **429** Too Many Requests
