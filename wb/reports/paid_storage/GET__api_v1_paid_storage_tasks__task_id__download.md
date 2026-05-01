# `GET` /api/v1/paid_storage/tasks/{task_id}/download

**Tag:** [Paid Storage](index.md)

**Server:** `https://seller-analytics-api.wildberries.ru`

**Get the Report**

Описание метода

Returns the report by task ID


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 min | 1 request | 1 min | 1 request |
| Service | 1 min | 1 request | 1 min | 1 request |
| Base | 1 h | 2 requests | 30 min | 1 request |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `task_id` | path | string | ✓ | Task ID  *Example: `06e06887-9d9f-491f-b16a-bb1766fcb8d2`* |

## Responses

### `200` Success

*Array of:*

  | Field | Type | Req | Description |
  |-------|------|-----|-------------|
  | `date` | string |  | Calculation or recalculation date |
  | `logWarehouseCoef` | number |  | Logistics and storage coefficient |
  | `officeId` | integer |  | Warehouse ID |
  | `warehouse` | string |  | Warehouse name |
  | `warehouseCoef` | number |  | Warehouse coefficient |
  | `giId` | integer |  | Shipment ID |
  | `chrtId` | integer |  | Size ID |
  | `size` | string |  | Size (`techSize` in product card) |
  | `barcode` | string |  | Barcode |
  | `subject` | string |  | Subject (subcategory) |
  | `brand` | string |  | Brand |
  | `vendorCode` | string |  | Seller's article |
  | `nmId` | integer |  | Wildberries article |
  | `volume` | number |  | Product volume |
  | `calcType` | string |  | Calculation type |
  | `warehousePrice` | number |  | Storage price |
  | `barcodesCount` | integer |  | Chargeable  product units in the warehouse, in the last 24 hours |
  | `palletPlaceCode` | integer |  | Pallet place code |
  | `palletCount` | number |  | Number of pallets |
  | `originalDate` | string |  | Calculation date, in case of recalculation. If there was not a recalculation, the same as `date` |
  | `loyaltyDiscount` | number |  | Loyalty program discount, ₽ |
  | `tariffFixDate` | string |  | Tariff fixing date |
  | `tariffLowerDate` | string |  | Tariff reduction date |

[Response 200](../_shared/examples/GET__api_v1_paid_storage_tasks__task_id__download_200.json)

- **204** No data
### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `detail` | string |  | Error details |
| `origin` | string |  | WB internal service ID |
| `requestId` | string |  | Unique request ID |
| `title` | string |  | Error title |

[Response 400](../_shared/examples/GET__api_v1_warehouse_remains_tasks__task_id__download_400.json)

- **401** Unauthorized
- **402** Payment Required
### `404` Not found


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `detail` | string |  | Error details |
| `origin` | string |  | WB internal service ID |
| `requestId` | string |  | Unique request ID |
| `title` | string |  | Error title |

[Response 404](../_shared/examples/GET__api_v1_warehouse_remains_tasks__task_id__status_404.json)

- **429** Too Many Requests
