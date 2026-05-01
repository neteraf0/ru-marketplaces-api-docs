# `GET` /api/v3/offices

**Tag:** [Seller Warehouses](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Get Offices**

Описание метода

Returns a list of all offices to link to seller warehouse.


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
  | `address` | string |  | Address *Example: `ул. Троицкая, Подольск, Московская обл.`* |
  | `name` | string |  | Name *Example: `Коледино`* |
  | `city` | string |  | City *Example: `Москва`* |
  | `id` | integer |  | ID *Example: `15`* |
  | `longitude` | number |  | Longitude *Example: `55.386871`* |
  | `latitude` | number |  | Latitude *Example: `37.588898`* |
  | `cargoType` | integer (enum: 1, 2, 3) |  | The type of goods a warehouse can accept:   - `1` — small-sized goods   - `2` — over dimensional cargo (ODC)   - `3` — dimensional cargo+ (CD+)  *Example: `1`* |
  | `deliveryType` | integer (enum: 1, 2, 3, 5, 6) |  | The type of deliveries:   - `1` — Fulfillment By Wildberries (FBS)   - `2` — Delivery By Supplier (DBS)   - `3` — Delivery by WB courier (DBW)   - `5` — In-Store Pickup (C&C)   - `6` — Express Delivery By Supplier (EDBS)  *Example: `1`* |
  | `federalDistrict` | string |  | Federal district of the WB office. If `null`, the office is located outside the Russian Federation or the federal district is not specified *Example: `Центральный`* |
  | `selected` | boolean |  | The flag indicating that the office has already been selected by the supplier |

[Response 200](../_shared/examples/GET__api_v3_offices_200.json)

- **401** Unauthorized
- **403** Forbidden
- **429** Too Many Requests
