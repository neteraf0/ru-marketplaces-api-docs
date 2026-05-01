# `POST` /adv/v2/supplier/nms

**Tag:** [Campaigns Creation](index.md)

**Server:** `https://advert-api.wildberries.ru`

**Product Cards for Campaigns**

Описание метода

Returns product cards that are available for all campaigns.


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 min | 5 requests | 12 s | 5 requests |
| Service | 1 min | 5 requests | 12 s | 5 requests |
| Base | 1 h | 2 requests | 30 min | 1 request |


## Request Body

Content-Type: `application/json`

*Array of:*
  `integer`

[Request example](examples/POST__adv_v2_supplier_nms_req.json)

## Responses

### `200` Success

*Array of:*

  | Field | Type | Req | Description |
  |-------|------|-----|-------------|
  | `title` | string |  | Product name *Example: `Плед`* |
  | `nm` | integer |  | WB article *Example: `146168367`* |
  | `subjectId` | integer |  | Subject ID *Example: `765`* |

[Response 200](../_shared/examples/POST__adv_v2_supplier_nms_200.json)

### `400` Bad request

`string`

[Response 400](../_shared/examples/POST__adv_v2_supplier_nms_400.json)

- **401** Unauthorized
- **429** Too Many Requests
