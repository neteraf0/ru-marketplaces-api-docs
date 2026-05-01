# `DELETE` /api/v3/warehouses/{warehouseId}

**Tag:** [Seller Warehouses](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Delete Warehouse**

Описание метода

Deletes the seller's warehouse.


Request limit per one seller's account for all seller warehouses methods:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 300 requests | 200 ms | 20 requests |

One request with a response code of 409 is counted as 10 requests


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `warehouseId` | path | integer | ✓ | The seller's warehouse ID *Example: `2`* |

## Responses

- **204** Deleted
- **401** Unauthorized
- **402** Payment Required
- **403** Forbidden
- **404** Not Found
- **429** Too Many Requests
