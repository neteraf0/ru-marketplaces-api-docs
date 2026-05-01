# `GET` /api/v1/transit-tariffs

**Tag:** [Information for Forming Supplies](index.md)

**Server:** `https://supplies-api.wildberries.ru`

**Transit Directions**

Описание метода

The method returns information about available transit directions.


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 min | 6 requests | 10 s | 10 requests |
| Service | 1 min | 6 requests | 10 s | 10 requests |
| Base | 12 h | 1 request | 12 h | 1 request |


## Responses

### `200` Success

*Array of:*

  | Field | Type | Req | Description |
  |-------|------|-----|-------------|
  | `transitWarehouseName` | string |  | Transit warehouse |
  | `destinationWarehouseName` | string |  | Destination warehouse |
  | `activeFrom` | string |  | From what date the transit direction is available |
  | `boxTariff` | array |  | Tariff for box transit. If `null`, transit for boxes is not available |
  | `palletTariff` | integer |  | Tariff per pallet, ₽ |

[Response 200: ResponseTariffs](../_shared/examples/GET__api_v1_transit_tariffs_200_ResponseTariffs.json)

- **401** Unauthorized
- **429** Too Many Requests
