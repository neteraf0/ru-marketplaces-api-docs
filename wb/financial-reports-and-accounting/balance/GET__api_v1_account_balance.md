# `GET` /api/v1/account/balance

**Tag:** [Balance](index.md)

**Server:** `https://finance-api.wildberries.ru`

**Get Seller's Balance**

Описание метода

Balance widget data on [the main page](https://seller.wildberries.ru) of the sellers portal.


Request limit per one seller's account:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 1 request | 1 min | 1 request |


## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `currency` | string |  | Currency *Example: `RUB`* |
| `current` | number |  | Current seller's balance *Example: `10196.21`* |
| `for_withdraw` | number |  | The money that can be withdrawn now *Example: `6395.8`* |

[Response 200](../_shared/examples/GET__api_v1_account_balance_200.json)

- **401** Unauthorized
- **402** Payment Required
- **429** Too Many Requests
