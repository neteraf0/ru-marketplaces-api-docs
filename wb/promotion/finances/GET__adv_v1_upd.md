# `GET` /adv/v1/upd

**Tag:** [Finances](index.md)

**Server:** `https://advert-api.wildberries.ru`

**Receiving Costs History**

Описание метода

The method allows to get a costs history


Request limit per one seller's account:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 s | 1 request | 1 s | 5 requests |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `from` | query | string | ✓ | Beginning of the interval *Example: `2023-07-31`* |
| `to` | query | string | ✓ | End of interval.  (Minimum interval is 1 day, maximum is 31)  *Example: `2023-08-02`* |

## Responses

### `200` Success

*Array of:*

  | Field | Type | Req | Description |
  |-------|------|-----|-------------|
  | `updNum` | integer |  | Billing document number (if any) |
  | `updTime` | string |  | Time of charge-off |
  | `updSum` | integer |  | Amount invoiced |
  | `advertId` | integer |  | Campaign ID |
  | `campName` | string |  | Campaign name |
  | `advertType` | integer |  | Campaign type |
  | `paymentType` | string |  | Source of charge-off:  - `Баланс` — Balance  - `Бонусы` — Bonuses  - `Счёт` — Money account  - `Кэшбэк` — Debit card cashback  |
  | `advertStatus` | integer |  | Campaign status: - `-1` — deleted, the deletion process will be completed within 10 minutes - `4` — ready to be launched - `7` — completed - `8` — declined - `9` — active - `11` — paused  |

[Response 200](../_shared/examples/GET__adv_v1_upd_200.json)

### `400` Bad request

`string`

[Response 400: IncorrectSupplierIdAdv](../_shared/examples/POST__adv_v0_rename_400_IncorrectSupplierIdAdv.json)

- **401** Unauthorized
- **429** Too Many Requests
