# `POST` /api/v1/seller/message

**Tag:** [Buyers Chat](index.md)

**Send Message**

Описание метода

Sends message to the buyer.


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 10 s | 10 requests | 1 s | 10 requests |
| Service | 10 s | 10 requests | 1 s | 10 requests |
| Base | 1 h | 1 request | 1 h | 1 request |


## Request Body

Content-Type: `multipart/form-data`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `replySign` | string | ✓ | Chat signature. Can be obtained from [chat information](./user-communication#tag/Buyers-Chat/paths/~1api~1v1~1seller~1chats/get) or [event data](./user-communication#tag/Buyers-Chat/paths/~1api~1v1~1seller~1events/get) if the event contains the `"isNewChat": true` field.  |
| `message` | string |  | Message text. Maximum of 1000 symbols. |
| `file` | array |  | Files, in JPEG, PDF, or PNG format, maximum size — 5 MB each. Maximum of total file size — 30 MB.  |
## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `errors` | array |  | File upload errors, if any |
| `result` | object |  |  |

[Response 200](../_shared/examples/POST__api_v1_seller_message_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `status` | number |  | HTTP status code |
| `title` | string |  | Error title |
| `origin` | string |  | WB internal service ID |
| `detail` | string |  | Error details |
| `requestId` | string |  | Unique request ID |
| `error` | string |  | Error text |

[Response 400: InvalidSignature](../_shared/examples/POST__api_v1_seller_message_400_InvalidSignature.json)


[Response 400: InvalidFileSize](../_shared/examples/POST__api_v1_seller_message_400_InvalidFileSize.json)


[Response 400: UnsupportedFilesType](../_shared/examples/POST__api_v1_seller_message_400_UnsupportedFilesType.json)


[Response 400: InvalidMessage](../_shared/examples/POST__api_v1_seller_message_400_InvalidMessage.json)

- **401** Unauthorized
- **402** Payment Required
- **429** Too Many Requests
