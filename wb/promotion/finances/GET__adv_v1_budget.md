# `GET` /adv/v1/budget

**Tag:** [Finances](index.md)

**Server:** `https://advert-api.wildberries.ru`

**Campaign Budget**

Описание метода

The method allows to get information about the budget of a campaign.


Request limit per one seller's account:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 s | 4 requests | 250 ms | 4 requests |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `id` | query | integer | ✓ | Campaign ID *Example: `1`* |

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `cash` | integer |  | The field is not used. The value is always equal to 0. |
| `netting` | integer |  | The field is not used. The value is always equal to 0. |
| `total` | integer |  | Campaign budget, ₽ |

[Response 200](../_shared/examples/GET__adv_v1_budget_200.json)

### `400` Bad request

`string`

[Response 400: CampaignNotBelongSeller](../_shared/examples/GET__adv_v1_budget_400_CampaignNotBelongSeller.json)

- **401** Unauthorized
- **429** Too Many Requests
