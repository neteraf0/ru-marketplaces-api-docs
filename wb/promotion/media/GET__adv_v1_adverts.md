# `GET` /adv/v1/adverts

**Tag:** [Media](index.md)

**Server:** `https://advert-media-api.wildberries.ru`

**List of Media Campaigns**

Описание метода

The method allows to get the list of media campaigns of the seller


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 s | 10 requests | 100 ms | 10 requests |
| Service | 1 s | 10 requests | 100 ms | 10 requests |
| Base | 1 h | 1 request | 1 h | 1 request |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `status` | query | integer |  | Media campaign status:   - `1` — template   - `2` — moderation   - `3` — rejected (with the possibility to resubmit for moderation)   - `4` — ready for launch   - `5` — scheduled   - `6` — running   - `7` — completed   - `8` — declined   - `9` — paused by seller   - `10` — paused due to daily limit   - `11` — paused  *Example: `1`* |
| `type` | query | integer |  | Media campaign type: - `1` — daily basis - `2` — views basis  *Example: `1`* |
| `limit` | query | integer |  | Number of campaigns in the response *Example: `1`* |
| `offset` | query | integer |  | Offset relative to the first media campaign *Example: `1`* |
| `order` | query | string |  | The order in which the response is displayed: - `create` — by time of media campaign creation - `id` — by ID of media campaign creation  *Example: `id`* |
| `direction` | query | string |  | Sorting order: - `desc` — upward - `asc` — smaller to larger  *Example: `desc`* |

## Responses

### `200` Success

*Array of:*

  | Field | Type | Req | Description |
  |-------|------|-----|-------------|
  | `advertId` | integer |  | Media campaign ID |
  | `name` | string |  | Media campaign name |
  | `brand` | string |  | Brand name |
  | `type` | integer |  | Media campaign type: - `1` — daily basis - `2` — views basis  |
  | `status` | integer |  | Media campaign status:   - `1` — template   - `2` — moderation   - `3` — rejected (with the possibility to resubmit for moderation)   - `4` — ready for launch   - `5` — scheduled   - `6` — running   - `7` — completed   - `8` — declined   - `9` — paused by seller   - `10` — paused due to daily limit   - `11` — paused  |
  | `createTime` | string |  | Time of media campaign creation |
  | `endTime` | string |  | Time of completion of the media campaign  |

[Response 200](../_shared/examples/GET__adv_v1_adverts_200.json)

- **204** Media campaigns not found
- **401** Unauthorized
- **429** Too Many Requests
