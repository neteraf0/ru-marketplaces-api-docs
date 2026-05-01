# `GET` /api/tariffs/v1/acceptance/coefficients

**Tag:** [Supply Tariffs](index.md)

**Server:** `https://common-api.wildberries.ru`

**Supply Tariffs**

Описание метода

The method returns the supply tariffs for specific warehouses for the next 14 days.


  Acceptance for delivery is only available with the following combination of field's values:  coefficient — 0 or 1  and allowUnload — true


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 min | 6 requests | 10 s | 6 requests |
| Service | 1 min | 6 requests | 10 s | 6 requests |
| Base | 1 h | 1 request | 1 h | 1 request |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `warehouseIDs` | query | string |  | Warehouse IDs.By default, data for all warehouses is returned *Example: `507,117501`* |

## Responses

### `200` Success

*Array of:*

  | Field | Type | Req | Description |
  |-------|------|-----|-------------|
  | `date` | string |  | Start date of the coefficient |
  | `coefficient` | number |  | Acceptance coefficient:   - `-1` — acceptance is not available, regardless of the value of the field `allowUnload`   - `0` — free acceptance   - from `1` — acceptance cost multiplier  |
  | `warehouseID` | integer |  | Warehouse ID. Use it to get [information about the warehouse](./orders-fbw#tag/Information-for-Forming-Supplies/paths/~1api~1v1~1warehouses/get) |
  | `warehouseName` | string |  | Warehouse name |
  | `allowUnload` | boolean |  | Availability of acceptance for deliveries of this type, see the value of the field `boxTypeID`:  - `true` — available  - `false` — not available  |
  | `boxTypeID` | integer |  | Supply type ID:   - `2` — Box   - `5` — Monopallets   - `6` — Super safe For the **QR-delivery with boxes** supply type the field is not returned  |
  | `storageCoef` | string |  | Storage coefficient |
  | `deliveryCoef` | string |  | Logistic coefficient |
  | `deliveryBaseLiter` | string |  | Cost of logistic for the first liter |
  | `deliveryAdditionalLiter` | string |  | Cost of logistic for each additional liter |
  | `storageBaseLiter` | string |  | Storage cost:   - for pallets — cost per pallet   - for boxes — storage cost for the first liter  |
  | `storageAdditionalLiter` | string |  | Storage cost for each additional liter:   - for pallets — will always be `null` since the storage cost per pallet is defined in `StorageBaseLiter`   - for boxes — storage cost for each additional liter  |
  | `isSortingCenter` | boolean |  | Warehouse type: - `true` — a sorting center (SC) - `false` — regular  |

[Response 200: ResponseCoefficients](../_shared/examples/GET__api_tariffs_v1_acceptance_coefficients_200_ResponseCoefficients.json)

### `400` Incorrect request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `status` | integer |  | HTTP status code |
| `title` | string |  | Error ID |
| `detail` | string |  | Error description |
| `requestId` | string |  | Request ID |
| `origin` | string |  | Service that returned the error |

[Response 400: BadWarehouseIDsParamNew](../_shared/examples/GET__api_tariffs_v1_acceptance_coefficients_400_BadWarehouseIDsParamNew.json)

- **401** Unauthorized
- **403** Access denied
- **404** Not found
- **429** Too Many Requests
