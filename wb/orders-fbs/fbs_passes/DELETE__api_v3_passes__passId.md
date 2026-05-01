# `DELETE` /api/v3/passes/{passId}

**Tag:** [FBS Passes](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Delete the Pass**

Описание метода

Deletes the seller's pass


Request limit per one seller's account for FBS assembly orders, supplies and passes methods:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 300 requests | 200 ms | 20 requests |

One request with a response code of 409 is counted as 10 requests


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `passId` | path | integer | ✓ | Pass ID *Example: `45`* |

## Responses

- **204** Deleted
- **401** Unauthorized
- **402** Payment Required
- **403** Forbidden
- **404** Not Found
- **429** Too Many Requests
