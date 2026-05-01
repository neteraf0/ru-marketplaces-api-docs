# `GET` /adv/v3/fullstats

**Tag:** [Statistics](index.md)

**Server:** `https://advert-api.wildberries.ru`

**Campaigns Statistics**

Описание метода

The method generates statistics for campaigns, regardless of their type.

The maximum period in a request is 31 days.

For campaigns in statuses `7`, `9` and `11`.


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 min | 3 requests | 20 s | 1 request |
| Service | 1 min | 3 requests | 20 s | 1 request |
| Base | 1 h | 1 request | 1 h | 1 request |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `ids` | query | string | ✓ | Campaign IDs, maximum 50 values *Example: `22161678,28449281,28155229`* |
| `beginDate` | query | string | ✓ | Start date for the interval *Example: `2025-09-07`* |
| `endDate` | query | string | ✓ | End date for the interval *Example: `2025-09-08`* |

## Responses

### `200` Success

*Array of:*

  | Field | Type | Req | Description |
  |-------|------|-----|-------------|
  | `advertId` | integer | ✓ | Campaign ID |
  | `atbs` | integer | ✓ | Number of products added to the cart |
  | `boosterStats` | BoosterStatsV3 |  | Statistics on the average position (for campaigns with standard bid) |
  | `canceled` | integer | ✓ | Cancellations, pcs |
  | `clicks` | integer | ✓ | Number of clicks |
  | `cpc` | number | ✓ | Average cost per click, ₽ |
  | `cr` | number | ✓ | CR (conversion rate) — the ratio of the number of orders to the total number of clicks |
  | `ctr` | number | ✓ | CTR (click-through rate) — the ratio of clicks to displays, expressed as a percentage |
  | `days` | DaysV3 | ✓ | Statistics by days |
  | `orders` | integer | ✓ | Number of orders |
  | `shks` | integer | ✓ | Number of ordered products, pcs |
  | `sum` | number | ✓ | Costs, ₽ |
  | `sum_price` | number | ✓ | Orders amount, ₽ |
  | `views` | integer | ✓ | Number of views |

[Response 200](../_shared/examples/GET__adv_v3_fullstats_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `detail` | string | ✓ | Error details |
| `origin` | string | ✓ | WB internal service ID |
| `request_id` | string | ✓ | Request ID |
| `status` | integer | ✓ | HTTP status code |
| `title` | string | ✓ | Error title |

[Response 400](../_shared/examples/GET__adv_v3_fullstats_400.json)

- **401** Unauthorized
- **429** Too Many Requests
