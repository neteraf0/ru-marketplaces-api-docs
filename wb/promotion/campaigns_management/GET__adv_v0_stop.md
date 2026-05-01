# `GET` /adv/v0/stop

**Tag:** [Campaigns Management](index.md)

**Server:** `https://advert-api.wildberries.ru`

**Stop Campaign**

Описание метода

The method allows to end campaigns in statuses:
- `4` — ready to launch
- `9` — active
- `11` — paused


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

- **401** Unauthorized
### `422` Status not changed

`string`

[Response 422: StatusNoChangeAdv](../_shared/examples/GET__adv_v0_start_422_StatusNoChangeAdv.json)

- **429** Too Many Requests
