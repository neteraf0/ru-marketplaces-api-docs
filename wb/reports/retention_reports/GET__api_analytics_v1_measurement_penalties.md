# `GET` /api/analytics/v1/measurement-penalties

**Tag:** [Retention Reports](index.md)

**operationId:** `getMeasurementPenalties`

**Server:** `https://seller-analytics-api.wildberries.ru`

**Logistics and Storage Costs Multiplier**

Описание метода

The method returns a report with [logistics and storage costs multiplier](https://seller.wildberries.ru/analytics-reports/dimensions-penalties)


Request limit per one seller's account:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 1 request | 1 min | 1 request |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `dateFrom` | query | string |  | Report period start. By default the date when data for the report was first received is used *Example: `2025-02-01T15:00:00Z`* |
| `dateTo` | query | string | ✓ | Report period end *Example: `2025-10-11T18:00:00Z`* |
| `limit` | query | integer | ✓ | Number of retentions in the response *Example: `330`* |
| `offset` | query | integer |  | How many results to skip. For example, with value `10`, the response will start with the 11 element *Example: `220`* |

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object | ✓ | Response data |

[Response 200: MeasurementPenalties](../_shared/examples/GET__api_analytics_v1_measurement_penalties_200_MeasurementPenalties.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `title` | string |  | Error title *Example: `bad request`* |
| `status` | integer |  | HTTP status code *Example: `400`* |
| `detail` | string |  | Error details *Example: `invalid parameter: dateTo`* |
| `requestId` | string |  | Unique request ID *Example: `31db50b5-14c0-4f4e-965e-6e1f9607ee78`* |
| `origin` | string |  | WB internal service ID *Example: `dimension-penalty`* |

[Response 400](../_shared/examples/GET__api_analytics_v1_measurement_penalties_400.json)

- **401** Unauthorized
### `403` Access denied


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `title` | string |  | Error title *Example: `access denied`* |
| `status` | integer |  | HTTP status code *Example: `403`* |
| `detail` | string |  | Error details *Example: `abac: access denied`* |
| `requestId` | string |  | Unique request ID *Example: `31db50b5-14c0-4f4e-965e-6e1f9607ee78`* |
| `origin` | string |  | WB internal service ID *Example: `dimension-penalty`* |

[Response 403](../_shared/examples/GET__api_analytics_v1_measurement_penalties_403.json)

- **429** Too Many Requests
