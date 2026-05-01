# `GET` /api/v1/seller/download/{id}

**Tag:** [Buyers Chat](index.md)

**Get File from the Message**

Описание метода

The method provides a file or image from the message by its ID.


Request limit per one seller's account:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 10 s | 10 requests | 1 s | 10 requests |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `id` | path | string | ✓ | File ID from the `downloadID` field in the [chat events](./user-communication#tag/Buyers-Chat/paths/~1api~1v1~1seller~1events/get) method |

## Responses

### `200` Success

`string`

[Response 200](../_shared/examples/GET__api_v1_seller_download__id_200.json)

`string`

[Response 200](../_shared/examples/GET__api_v1_seller_download__id_200.json)

`string`

[Response 200](../_shared/examples/GET__api_v1_seller_download__id_200.json)

### `202` The file is under moderation


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `moderationState` | string | ✓ | Moderation status *Example: `pending`* |
| `retrySeconds` | integer | ✓ | Seconds until retry to request a file *Example: `30`* |

[Response 202](../_shared/examples/GET__api_v1_seller_download__id_202.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `status` | number |  | HTTP status code |
| `title` | string |  | Error title |
| `origin` | string |  | WB internal service ID |
| `detail` | string |  | Error details |
| `requestId` | string |  | Unique request ID |
| `error` | string |  | Error text |

[Response 400: IncorrectNextParameter](../_shared/examples/GET__api_v1_seller_download__id_400_IncorrectNextParameter.json)

- **401** Unauthorized
- **402** Payment Required
- **429** Too Many Requests
### `451` Moderation failed


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `status` | integer |  | HTTP status code *Example: `451`* |
| `title` | string |  | Error title *Example: `Unavailable for Legal Reasons`* |
| `origin` | string |  | WB internal service ID *Example: `proxy-chats`* |
| `detail` | string |  | Error detail *Example: `moderation error`* |
| `requestId` | string |  | Request ID *Example: `62f59a4ce21064f20b1bbc28c85f38d8`* |

[Response 451](../_shared/examples/GET__api_v1_seller_download__id_451.json)
