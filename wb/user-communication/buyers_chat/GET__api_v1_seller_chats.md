# `GET` /api/v1/seller/chats

**Tag:** [Buyers Chat](index.md)

**Chat List**

Описание метода

Returns a list of all seller's chats.


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 10 s | 10 requests | 1 s | 10 requests |
| Service | 10 s | 10 requests | 1 s | 10 requests |
| Base | 1 h | 1 request | 1 h | 1 request |


## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `result` | array |  |  |
| `errors` | array |  | Errors, if any |

[Response 200](../_shared/examples/GET__api_v1_seller_chats_200.json)

- **401** Unauthorized
- **402** Payment Required
- **429** Too Many Requests
