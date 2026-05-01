# `GET` /adv/v0/delete

**Tag:** [Campaigns Management](index.md)

**Server:** `https://advert-api.wildberries.ru`

**Delete Campaign**

Описание метода

The method allows to delete campaigns in the status `4` — ready to launch.

After deleting, the campaign will be in `-1` status for a while.

It takes between 3 and 10 minutes to completely delete the campaign.


Request limit per one seller's account:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 s | 5 requests | 200 ms | 5 requests |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `id` | query | integer | ✓ | Campaign ID |

## Responses

- **200** Success
### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `error` | string |  |  |

[Response 400: ResponseInvalidCampaignID](../_shared/examples/GET__adv_v0_delete_400_ResponseInvalidCampaignID.json)

- **401** Unauthorized
- **429** Too Many Requests
