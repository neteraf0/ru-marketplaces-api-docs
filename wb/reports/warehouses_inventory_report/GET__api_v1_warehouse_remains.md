# `GET` /api/v1/warehouse_remains

**Tag:** [Warehouses Inventory Report](index.md)

**Server:** `https://seller-analytics-api.wildberries.ru`

**Create the Report**

Описание метода

Creates a task for report generation. The parameters `groupBy` and `filter` can be set in any combination — similar to the [version](https://seller.wildberries.ru/analytics-reports/warehouse-remains) in the personal account.


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 min | 1 request | 1 min | 5 requests |
| Service | 1 min | 1 request | 1 min | 5 requests |
| Base | 1 h | 4 requests | 15 min | 1 request |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `locale` | query | string |  | Language of the `subjectName` and `warehouseName` response fields:   - `ru` — Russian   - `en` — English   - `zh` — Chinese. Values of the `warehouseName` are in English  *Example: `ru`* |
| `groupByBrand` | query | boolean |  | Group by brand *Example: `True`* |
| `groupBySubject` | query | boolean |  | Group by subject *Example: `True`* |
| `groupBySa` | query | boolean |  | Group by seller's article *Example: `True`* |
| `groupByNm` | query | boolean |  | Group by WB article. If `groupByNm=true`, there will be `volume` field in the response *Example: `True`* |
| `groupByBarcode` | query | boolean |  | Group by barcode *Example: `True`* |
| `groupBySize` | query | boolean |  | Group by size *Example: `True`* |
| `filterPics` | query | integer |  | Photo filter:   - `-1` — without photo   - `0` — do not apply filter   - `1` — with photo  *Example: `1`* |
| `filterVolume` | query | integer |  | Volume filter:   - `-1` — without dimensions   - `0` — do not apply filter   - `3` — over three liters  *Example: `3`* |

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | CreateTaskResponseData |  |  |

[Response 200: CreateResponseData](../_shared/examples/GET__api_v1_warehouse_remains_200_CreateResponseData.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `detail` | string |  | Error details |
| `origin` | string |  | WB internal service ID |
| `requestId` | string |  | Unique request ID |
| `title` | string |  | Error title |

[Response 400](../_shared/examples/GET__api_v1_warehouse_remains_400.json)

- **401** Unauthorized
- **402** Payment Required
- **429** Too Many Requests
