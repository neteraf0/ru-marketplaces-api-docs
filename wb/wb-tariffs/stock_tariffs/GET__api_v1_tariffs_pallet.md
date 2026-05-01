# `GET` /api/v1/tariffs/pallet

**Tag:** [Stock Tariffs](index.md)

**Server:** `https://common-api.wildberries.ru`

**Pallet Tariffs**

Описание метода

For items supplied to the WB warehouse on pallets, the method returns the [cost](https://seller.wildberries.ru/dynamic-product-categories):
  - of delivery from warehouse to the buyer
  - of delivery from the buyer to warehouse
  - of storage on WB warehouse


  The rates for pallets match the Piece pallet rates


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
| `response` | models.TariffsPalletResponse |  |  |

[Response 200](../_shared/examples/GET__api_v1_tariffs_pallet_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `detail` | string |  | Error details |
| `origin` | string |  | WB internal service ID |
| `requestId` | string |  | Unique request ID |
| `title` | string |  | Error title |

[Response 400](../_shared/examples/GET__api_v1_tariffs_pallet_400.json)

- **401** Unauthorized
- **402** Payment Required
- **429** Too Many Requests
