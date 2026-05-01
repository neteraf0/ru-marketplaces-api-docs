# `GET` /adv/v1/payments

**Tag:** [Finances](index.md)

**Server:** `https://advert-api.wildberries.ru`

**Receiving the History of Account Top-ups**

Описание метода

The method allows you to get a history of top-ups.


Request limit per one seller's account:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 s | 1 request | 1 s | 5 requests |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `from` | query | string |  | Beginning of the interval *Example: `2023-07-31`* |
| `to` | query | string |  | End of interval.  (Minimum interval is 1 day, maximum is 31)  *Example: `2023-08-02`* |

## Responses

### `200` Success

*Array of:*

  | Field | Type | Req | Description |
  |-------|------|-----|-------------|
  | `id` | integer |  | Payment ID |
  | `date` | string |  | Payment date |
  | `sum` | integer |  | Payment amount |
  | `type` | integer |  | Type of charge-off source: - `0` — Account - `1` — Balance - `3` — Card  |
  | `statusId` | integer |  | Status: - `0` — error - `1` — processed  |
  | `cardStatus` | string |  | Transaction status (when paying by card): - `success` — success - `fail` — not success - `pending` — waiting for response - `unknown` — unknown  |

[Response 200](../_shared/examples/GET__adv_v1_payments_200.json)

- **204** Transaction history not found
### `400` Bad request

`string`

[Response 400: IncorrectSupplierIdAdv](../_shared/examples/POST__adv_v0_rename_400_IncorrectSupplierIdAdv.json)

- **401** Unauthorized
- **429** Too Many Requests
