# `GET` /adv/v1/balance

**Tag:** [Finances](index.md)

**Server:** `https://advert-api.wildberries.ru`

**Balance**

Описание метода

The method allows to get information about the seller's net, balance and bonuses


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 s | 1 request | 1 s | 5 requests |
| Service | 1 s | 1 request | 1 s | 5 requests |
| Base | 1 h | 2 requests | 30 min | 1 request |


## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `balance` | integer |  | Account, ₽ |
| `net` | integer |  | Balance, ₽ |
| `bonus` | integer |  | Bonuses, ₽ |
| `cashbacks` | array |  | Promo bonuses |

[Response 200](../_shared/examples/GET__adv_v1_balance_200.json)

### `400` Bad request

`string`

[Response 400: IncorrectSupplierIdAdv](../_shared/examples/POST__adv_v0_rename_400_IncorrectSupplierIdAdv.json)

- **401** Unauthorized
- **429** Too Many Requests
