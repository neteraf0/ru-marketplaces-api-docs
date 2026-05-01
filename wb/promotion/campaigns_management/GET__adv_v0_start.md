# `GET` /adv/v0/start

**Tag:** [Campaigns Management](index.md)

**Server:** `https://advert-api.wildberries.ru`

**Launch Campaign**

Описание метода

The method allows to run campaigns that are in statuses `4` — ready to launch or `11` — paused campaign.
To run a campaign, check its budget. If the budget is insufficient, replenish it.


Request limit per one seller's account:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 s | 5 requests | 200 ms | 5 requests |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `id` | query | integer | ✓ | Campaign ID *Example: `1234`* |

## Responses

- **200** Success
### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `error` | string |  |  |

[Response 400: IncorrectId](../_shared/examples/GET__adv_v0_start_400_IncorrectId.json)


[Response 400: AdvertNotFound](../_shared/examples/GET__adv_v0_start_400_AdvertNotFound.json)


[Response 400: LowBudget](../_shared/examples/GET__adv_v0_start_400_LowBudget.json)

- **401** Unauthorized
### `422` Status not changed

`string`

[Response 422: StatusNoChangeAdv](../_shared/examples/GET__adv_v0_start_422_StatusNoChangeAdv.json)

- **429** Too Many Requests
