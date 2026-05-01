# `POST` /adv/v2/seacat/save-ad

**Tag:** [Campaigns Creation](index.md)

**Server:** `https://advert-api.wildberries.ru`

**Create Campaign**

Описание метода

The method creates campaign:
  - with custom bid for promotion products in search and/or recommendations
  - with standard bid for promotion products both in search and recommendations


Request limit per one seller's account:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 5 requests | 12 s | 5 requests |


## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `name` | string |  | Campaign name |
| `nms` | array |  | Product card for this campaign. You can available product cards with [product cards for campaigns](./promotion#tag/Campaigns-Creation/paths/~1adv~1v2~1supplier~1nms/post) method. Maximum of 50 products (`nm`)  |
| `bid_type` | string (enum: manual, unified) |  | Bid type:   - `unified` — standard bid   - `manual` — custom bid  |
| `payment_type` | string (enum: cpm, cpc) |  | Payment type: - `cpm` — cost per mille - `cpc` — cost per click. When creating a campaign with this payment type, a minimum bid is automatically set  |
| `placement_types` | array |  | Placements:   - `search` — search   - `recommendations` — recommendations   Specify for campaign with custom bid only  |

[Request example](examples/POST__adv_v2_seacat_save_ad_req.json)

## Responses

### `200` Success

`integer` — example: `1234567` — Campaign ID

[Response 200](../_shared/examples/POST__adv_v2_seacat_save_ad_200.json)

### `400` Bad request

`string`

[Response 400](../_shared/examples/POST__adv_v2_seacat_save_ad_400.json)

- **401** Unauthorized
- **429** Too Many Requests
