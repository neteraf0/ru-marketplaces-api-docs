# `GET` /api/v3/warehouses

**Tag:** [Seller Warehouses](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Get Warehouses**

Описание метода

Returns a list of all seller's warehouses.


Request limit per one seller's account for all seller warehouses methods:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 300 requests | 200 ms | 20 requests |

One request with a response code of 409 is counted as 10 requests


## Responses

### `200` Success

*Array of:*

  | Field | Type | Req | Description |
  |-------|------|-----|-------------|
  | `name` | string |  | Name *Example: `Kosmonavtov 14`* |
  | `officeId` | integer |  | Office ID *Example: `15`* |
  | `id` | integer |  | ID *Example: `1`* |
  | `cargoType` | integer (enum: 1, 2, 3) |  | The type of goods:   - `1` — small-sized goods   - `2` — over dimensional cargo (ODC)   - `3` — dimensional cargo+ (CD+)  *Example: `1`* |
  | `deliveryType` | integer (enum: 1, 2, 3, 5, 6) |  | The type of deliveries:   - `1` — Fulfillment By Wildberries (FBS)   - `2` — Delivery By Supplier (DBS)   - `3` — Delivery by WB courier (DBW)   - `5` — In-Store Pickup (C&C)   - `6` — Express Delivery By Supplier (EDBS)  *Example: `1`* |
  | `isDeleting` | boolean |  | Warehouse is being deleted:   - `false` — no   - `true` — yes  After deletion, the warehouse will disappear from the list  |
  | `isProcessing` | boolean |  | Warehouse is being updated:   - `false` — no   - `true` — yes, update and deletion of inventory is not available  Data update may take several minutes  *Example: `True`* |

[Response 200](../_shared/examples/GET__api_v3_warehouses_200.json)

- **401** Unauthorized
- **403** Forbidden
- **429** Too Many Requests
