# `GET` /api/v1/supplies/{ID}

**Tag:** [Supplies Information](index.md)

**Server:** `https://supplies-api.wildberries.ru`

**Supply Details**

Описание метода

The method returns supply details by ID.


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 min | 30 requests | 2 s | 10 requests |
| Service | 1 min | 30 requests | 2 s | 10 requests |
| Base | 1 h | 2 requests | 30 min | 1 request |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `ID` | path | integer | ✓ | ID of the supply or the order |
| `isPreorderID` | query | boolean |  | Search by:   - `true` — order ID, if you pass the order ID in `ID`   - `false` — supply ID, if you pass the supply ID in `ID`  |

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `phone` | string |  | Phone number of the user that created the supply |
| `statusID` | integer (enum: 1, 2, 3, 4, 5, 6) |  | Supply status ID: - `1` — Not planned - `2` — Planned - `3` — Unloading allowed - `4` — Accepting - `5` — Accepted - `6` — Unloaded at the gate  |
| `virtualTypeID` | integer |  | ID of virtual supply type. Displayed only for supplies with `"boxTypeID":0`.   - `0` — Carryover of stock   - `1` — Depersonalization   - `4` — QR supply   - `5` — Additional acceptance   - `6` — Scan acceptance  |
| `boxTypeID` | integer |  | Supply type ID:   - `0` — Without boxes (virtual supply)   - `1` and `2` — Boxes   - `5` — Monopallets   - `6` — Supersafe  |
| `createDate` | string |  | Date and time the supply was created |
| `supplyDate` | string |  | Planned unloading date |
| `factDate` | string |  | Actual unloading date |
| `updatedDate` | string |  | Date of the supply update |
| `warehouseID` | integer |  | Warehouse ID for planned supply |
| `warehouseName` | string |  | Warehouse name for planned supply |
| `actualWarehouseID` | integer |  | Warehouse ID where the supply was delivered |
| `actualWarehouseName` | string |  | Warehouse name where the supply was delivered |
| `transitWarehouseID` | integer |  | Transit warehouse ID |
| `transitWarehouseName` | string |  | Transit warehouse name |
| `acceptanceCost` | number |  | Preliminary acceptance cost, ₽ |
| `paidAcceptanceCoefficient` | number |  | Acceptance coefficient |
| `rejectReason` | string |  | Reason why the supply cannot be accepted |
| `supplierAssignName` | string |  | Short seller's name |
| `storageCoef` | string |  | Storage coefficient |
| `deliveryCoef` | string |  | Logistics coefficient |
| `quantity` | integer |  | Added to the supply/order, pieces |
| `readyForSaleQuantity` | integer |  | Ready for sale, pieces |
| `acceptedQuantity` | integer |  | Accepted, pieces |
| `unloadingQuantity` | integer |  | Total items at putaway, pieces |
| `depersonalizedQuantity` | integer |  | Quantity of depersonalized products, pieces |
| `isBoxOnPallet` | boolean |  | **Pallet with Single Items** — supply type:   - `true` — yes   - `false` — no    The field is returned only when `"boxTypeID": 2`  |

[Response 200](../_shared/examples/GET__api_v1_supplies__ID_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `status` | integer |  | HTTP status code |
| `title` | string |  | Error ID |
| `detail` | string |  | Error description |
| `requestId` | string |  | Request ID |
| `origin` | string |  | Service that returned the error |

[Response 400: BadPathParamFormat](../_shared/examples/GET__api_v1_supplies__ID_400_BadPathParamFormat.json)


[Response 400: BadisPreorderIDFormat](../_shared/examples/GET__api_v1_supplies__ID_400_BadisPreorderIDFormat.json)


[Response 400: PreorderIdSearchError](../_shared/examples/GET__api_v1_supplies__ID_400_PreorderIdSearchError.json)


[Response 400: BadID](../_shared/examples/GET__api_v1_supplies__ID_400_BadID.json)

- **401** Unauthorized
- **402** Payment Required
### `404` Not found


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `status` | integer |  | HTTP status code |
| `title` | string |  | Error ID |
| `detail` | string |  | Error description |
| `requestId` | string |  | Request ID |
| `origin` | string |  | Service that returned the error |

[Response 404: SupplyNotFound](../_shared/examples/GET__api_v1_supplies__ID_404_SupplyNotFound.json)

- **429** Too Many Requests
