# `GET` /api/v1/documents/list

**Tag:** [Documents](index.md)

**Server:** `https://documents-api.wildberries.ru`

**Documents List**

Описание метода

Returns seller's documents list


Request limit per one seller's account:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 10 s | 1 request | 10 s | 5 requests |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `locale` | query | string |  | `category` field language:   - `ru` — Russian   - `en` — English   - `zh` — Chinese  *Example: `ru`* |
| `beginTime` | query | string |  | Period start. Only with `endTime` *Example: `2024-07-09`* |
| `endTime` | query | string |  | Period end. Only with `beginTime` *Example: `2024-07-15`* |
| `sort` | query | string (enum: date, category) |  | Sorting:   - `date` — by the document creation date   - `category` — by category (only when `locale=ru`)  Only with `order`  *Example: `category`* |
| `order` | query | string (enum: desc, asc) |  | Data order:   - `desc` — descending   - `asc` — ascending  Only with `sort`  *Example: `asc`* |
| `category` | query | string |  | [Document category](./financial-reports-and-accounting#tag/Documents/paths/~1api~1v1~1documents~1categories/get) ID from the `name` field *Example: `redeem-notification`* |
| `serviceName` | query | string |  | Unique document ID *Example: `redeem-notification-44841941`* |
| `limit` | query | integer |  | The maximum number of response rows *Example: `10`* |
| `offset` | query | integer |  | From which row to start outputting data *Example: `90`* |

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object |  |  |

[Response 200](../_shared/examples/GET__api_v1_documents_list_200.json)

- **400** Bad Request
- **401** Unauthorized
- **402** Payment Required
- **429** Too Many Requests
