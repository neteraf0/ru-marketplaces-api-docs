# `PUT` /api/v3/passes/{passId}

**Tag:** [FBS Passes](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Update Pass**

Описание метода

Updates the seller's pass detail


Request limit per one seller's account for FBS assembly orders, supplies and passes methods:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 300 requests | 200 ms | 20 requests |

One request with a response code of 409 is counted as 10 requests


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `passId` | path | integer | ✓ | Pass ID *Example: `45`* |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `firstName` | string | ✓ | First name *Example: `Alex`* |
| `lastName` | string | ✓ | Last name *Example: `Petrov`* |
| `carModel` | string | ✓ | Car model *Example: `Lamborghini`* |
| `carNumber` | string | ✓ | Car number *Example: `A456BC123`* |
| `officeId` | integer | ✓ | Office ID *Example: `15`* |
## Responses

- **204** Updated
### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data for the error |

[Response 400: IncorrectRequestBody](../_shared/examples/POST__api_v3_passes_400_IncorrectRequestBody.json)


[Response 400: WarehouseNameInvalid](../_shared/examples/PUT__api_v3_passes__passId_400_WarehouseNameInvalid.json)

- **401** Unauthorized
- **402** Payment Required
- **403** Forbidden
- **404** Not Found
- **429** Too Many Requests
