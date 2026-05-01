# `GET` /api/v3/dbw/warehouses/{warehouseId}/contacts

**Tag:** [Seller Warehouses](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Contacts List**

Описание метода

Returns a list of contacts linked to the seller's warehouse.

Only for warehouses with delivery type `3` — Delivery by WB courier (DBW).


Request limit  per one seller's account for DBW methods:

    for getting and updating contact lists
    for getting and deleting metadata
    assembly orders


| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 300 requests | 200 ms | 20 requests |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `warehouseId` | path | integer | ✓ | The seller's warehouse ID *Example: `2`* |

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `contacts` | array |  |  |

[Response 200](../_shared/examples/GET__api_v3_dbw_warehouses__warehouseId__contacts_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data enriching the error |

[Response 400: IncorrectParameter](../_shared/examples/PUT__api_v3_stocks__warehouseId_400_IncorrectParameter.json)

- **401** Unauthorized
- **402** Payment Required
- **403** Forbidden
- **429** Too Many Requests
