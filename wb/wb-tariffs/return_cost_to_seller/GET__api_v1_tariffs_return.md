# `GET` /api/v1/tariffs/return

**Tag:** [Return Cost to Seller](index.md)

**Server:** `https://common-api.wildberries.ru`

**Return Tariffs**

Описание метода

Returns [tariffs](https://seller.wildberries.ru/dynamic-product-categories/return-cost):
  - on transfer from Wildberries warehouse or sorting center to the seller
  - on transfer of returned products that were not picked up by seller


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 min | 60 requests | 1 s | 5 requests |
| Service | 1 min | 60 requests | 1 s | 5 requests |
| Base | 1 h | 1 request | 1 h | 1 request |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `date` | query | string | ✓ | Date, YYYY-MM-DD |

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `response` | models.ReturnTariffsResponse |  |  |

[Response 200](../_shared/examples/GET__api_v1_tariffs_return_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `detail` | string |  | Error details |
| `origin` | string |  | WB internal service ID |
| `requestId` | string |  | Unique request ID |
| `title` | string |  | Error title |

[Response 400](../_shared/examples/GET__api_v1_tariffs_return_400.json)

- **401** Unauthorized
- **402** Payment Required
- **429** Too Many Requests
