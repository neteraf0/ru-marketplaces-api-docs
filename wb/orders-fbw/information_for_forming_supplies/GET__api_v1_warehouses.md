# `GET` /api/v1/warehouses

**Tag:** [Information for Forming Supplies](index.md)

**Server:** `https://supplies-api.wildberries.ru`

**Warehouses List**

Описание метода

The method returns Wildberries warehouses list.


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 min | 6 requests | 10 s | 6 requests |
| Service | 1 min | 6 requests | 10 s | 6 requests |
| Base | 12 h | 1 request | 12 h | 1 request |


## Responses

### `200` Success

*Array of:*

  | Field | Type | Req | Description |
  |-------|------|-----|-------------|
  | `ID` | integer |  | Warehouse ID |
  | `name` | string |  | Warehouse name |
  | `address` | string |  | Warehouse address |
  | `workTime` | string |  | Warehouse operating hours |
  | `isActive` | boolean |  | Is it available as a destination warehouse: - `true` — yes - `false` — no  |
  | `isTransitActive` | boolean |  | Is it available as a transit warehouse: - `true` — yes - `false` — no  |

[Response 200](../_shared/examples/GET__api_v1_warehouses_200.json)

- **401** Unauthorized
- **403** Access denied
- **404** Not found
- **429** Too Many Requests
