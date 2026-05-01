# `PUT` /api/v3/stocks/{warehouseId}

**Tag:** [Seller Warehouses Inventory](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Update Inventory**

Описание метода

Updates product inventory.


  The names of the query parameters are not validated. If invalid names are sent, the response will be successful(204), but the remaining amounts will not be updated.


Request limit per one seller's account for all inventory methods:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 300 requests | 200 ms | 20 requests |

One request with a response code of 409 is counted as 10 requests


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `warehouseId` | path | integer | ✓ | The seller's warehouse ID *Example: `2`* |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `stocks` | array | ✓ | Array of size IDs and amounts |
## Responses

- **204** Updated
### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data enriching the error |

[Response 400: IncorrectRequestBody](../_shared/examples/PUT__api_v3_stocks__warehouseId_400_IncorrectRequestBody.json)


[Response 400: IncorrectRequest](../_shared/examples/PUT__api_v3_stocks__warehouseId_400_IncorrectRequest.json)


[Response 400: IncorrectParameter](../_shared/examples/PUT__api_v3_stocks__warehouseId_400_IncorrectParameter.json)

- **401** Unauthorized
- **402** Payment Required
- **403** Forbidden
- **404** Not Found
- **406**
### `409` Error updating inventory

*Array of:*

  | Field | Type | Req | Description |
  |-------|------|-----|-------------|
  | `data` | array |  | Additional data enriching the error |
  | `code` | string |  | Error code |
  | `message` | string |  | Error description |

[Response 409: UploadDataLimit](../_shared/examples/PUT__api_v3_stocks__warehouseId_409_UploadDataLimit.json)


[Response 409: CargoWarehouseRestrictionMGT](../_shared/examples/PUT__api_v3_stocks__warehouseId_409_CargoWarehouseRestrictionMGT.json)


[Response 409: CargoWarehouseRestrictionSGT](../_shared/examples/PUT__api_v3_stocks__warehouseId_409_CargoWarehouseRestrictionSGT.json)


[Response 409: CargoWarehouseRestrictionSGTKGTPlus](../_shared/examples/PUT__api_v3_stocks__warehouseId_409_CargoWarehouseRestrictionSGTKGTPlus.json)


[Response 409: CargoWarehouseRestrictionKGTPlus](../_shared/examples/PUT__api_v3_stocks__warehouseId_409_CargoWarehouseRestrictionKGTPlus.json)


[Response 409: NotFound](../_shared/examples/PUT__api_v3_stocks__warehouseId_409_NotFound.json)


[Response 409: StoreIsProcessing](../_shared/examples/PUT__api_v3_stocks__warehouseId_409_StoreIsProcessing.json)


[Response 409: ProductPropertyConflict](../_shared/examples/PUT__api_v3_stocks__warehouseId_409_ProductPropertyConflict.json)


[Response 409: DeliveryTypeRestriction](../_shared/examples/PUT__api_v3_stocks__warehouseId_409_DeliveryTypeRestriction.json)

- **429** Too Many Requests
