# `GET` /api/v1/tariffs/commission

**Tag:** [Commissions](index.md)

**Server:** `https://common-api.wildberries.ru`

**Product Category Commission**

Описание метода

WB commission by parent categories of products according to sales model.


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 min | 1 request | 1 min | 2 requests |
| Service | 1 min | 1 request | 1 min | 2 requests |
| Base | 1 h | 5 requests | 12 min | 1 request |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `locale` | query | string |  | Language of the `parentName` and `subjectName` response fields:   - `ru` — Russian   - `en` — English   - `zh` — Chinese  *Example: `ru`* |

## Responses

### `200` Success


[Response 200: Commission](../_shared/examples/GET__api_v1_tariffs_commission_200_Commission.json)


[Response 200: CommissionChina](../_shared/examples/GET__api_v1_tariffs_commission_200_CommissionChina.json)


[Response 200: CommissionTurkey](../_shared/examples/GET__api_v1_tariffs_commission_200_CommissionTurkey.json)


[Response 200: CommissionUzbekistan](../_shared/examples/GET__api_v1_tariffs_commission_200_CommissionUzbekistan.json)


[Response 200: CommissionUAE](../_shared/examples/GET__api_v1_tariffs_commission_200_CommissionUAE.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `detail` | string |  | Error details |
| `origin` | string |  | WB internal service ID |
| `requestId` | string |  | Unique request ID |
| `title` | string |  | Error title |

[Response 400](../_shared/examples/GET__api_v1_tariffs_commission_400.json)

- **401** Unauthorized
- **402** Payment Required
- **429** Too Many Requests
