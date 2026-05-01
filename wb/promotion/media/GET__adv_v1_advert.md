# `GET` /adv/v1/advert

**Tag:** [Media](index.md)

**Server:** `https://advert-media-api.wildberries.ru`

**Information About Media Campaign**

Описание метода

The method allows to get information about a media campaign


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 s | 10 requests | 100 ms | 10 requests |
| Service | 1 s | 10 requests | 100 ms | 10 requests |
| Base | 1 h | 5 requests | 12 min | 1 request |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `id` | query | integer | ✓ | Media campaign ID *Example: `23569`* |

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `advertId` | integer |  | Media campaign ID |
| `name` | string |  | Media campaign name |
| `brand` | string |  | Brand name |
| `type` | integer |  | Media campaign type: - `1` — daily basis - `2` — views basis  |
| `status` | integer |  | Media campaign status:   - `1` — template   - `2` — moderation   - `3` — rejected (with the possibility to resubmit for moderation)   - `4` — ready for launch   - `5` — scheduled   - `6` — running   - `7` — completed   - `8` — declined   - `9` — paused by seller   - `10` — paused due to daily limit   - `11` — paused  |
| `createTime` | string |  | Time of media campaign creation |
| `extended` | object |  |  |
| `items` | array |  | Banner information.  The response may not contain all fields, it depends on your media campaign configuration.  |

[Response 200](../_shared/examples/GET__adv_v1_advert_200.json)

- **204** Media campaign not found
- **401** Unauthorized
- **429** Too Many Requests
