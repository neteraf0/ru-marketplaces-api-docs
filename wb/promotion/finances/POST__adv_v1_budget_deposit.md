# `POST` /adv/v1/budget/deposit

**Tag:** [Finances](index.md)

**Server:** `https://advert-api.wildberries.ru`

**Top-up of the Campaign Budget**

Описание метода

The method tops up the campaign [budget](./promotion#tag/Finances/paths/~1adv~1v1~1budget/get).
To launch the campaign after topping up the budget, use the [Launch campaign](./promotion#tag/Campaigns-Management/paths/~1adv~1v0~1start/get) method.


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 s | 1 request | 1 s | 5 requests |
| Service | 1 s | 1 request | 1 s | 5 requests |
| Base | 1 h | 5 requests | 12 min | 1 request |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `id` | query | integer | ✓ | Campaign ID *Example: `1234567`* |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `sum` | integer |  | Budget top-up amount *Example: `5000`* |
| `cashback_sum` | integer |  | Top-up budget sum paid with promo bonuses.  You can top up only a certain percentage of the amount, indicated in the `percent` field of the response from the method for getting [balance](./promotion#tag/Finances/paths/~1adv~1v1~1balance/get).  Promo bonuses are only applicable to these top-up sources:   - `0` — account   - `1` — balance sheet  *Example: `1000`* |
| `cashback_percent` | integer |  | The percentage of the top-up amount that can be paid with promo bonuses. You need to specify the value of the `percent` field from the response for the method for getting [balance]  If you specified `cashback_sum`, the `cashback_percent` parameter becomes required  *Example: `50`* |
| `type` | integer |  | Type of top-up source: - `0` — Account - `1` — Balance - `3` — Bonuses  *Example: `1`* |
| `return` | boolean |  | Response return flag (`true` means updated campaign budget size will be returned in the response, `false` or empty means nothing will be returned). |
## Responses

### `200` Success


[Response 200: ResponseWithReturn](../_shared/examples/POST__adv_v1_budget_deposit_200_ResponseWithReturn.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `error` | string |  |  |

[Response 400: DepositAmountMultiple50](../_shared/examples/POST__adv_v1_budget_deposit_400_DepositAmountMultiple50.json)


[Response 400: MinimumDepositAmountIs500](../_shared/examples/POST__adv_v1_budget_deposit_400_MinimumDepositAmountIs500.json)


[Response 400: IncorrectType](../_shared/examples/POST__adv_v1_budget_deposit_400_IncorrectType.json)

- **401** Unauthorized
- **429** Too Many Requests
