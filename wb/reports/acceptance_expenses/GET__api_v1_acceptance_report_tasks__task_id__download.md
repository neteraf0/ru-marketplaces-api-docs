# `GET` /api/v1/acceptance_report/tasks/{task_id}/download

**Tag:** [Acceptance Expenses](index.md)

**Server:** `https://seller-analytics-api.wildberries.ru`

**Get the Report**

Описание метода

Returns the report by task ID


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 min | 1 request | 1 min | 1 request |
| Service | 1 min | 1 request | 1 min | 1 request |
| Base | 1 h | 2 requests | 30 min | 1 request |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `task_id` | path | string | ✓ | Generation task ID  *Example: `06e06887-9d9f-491f-b16a-bb1766fcb8d2`* |

## Responses

### `200` Success

*Array of:*

  | Field | Type | Req | Description |
  |-------|------|-----|-------------|
  | `count` | integer |  | Number of products *Example: `40`* |
  | `giCreateDate` | string |  | Shipment creation date *Example: `2025-03-04`* |
  | `incomeId` | integer |  | Shipment number *Example: `11834106`* |
  | `nmID` | integer |  | Wildberries article *Example: `123456789`* |
  | `shkCreateDate` | string |  | Receiving date *Example: `2025-03-14`* |
  | `subjectName` | string |  | Subject *Example: `Добавки пищевые`* |
  | `total` | number |  | Receiving cost, ₽ with kopecks *Example: `873.04`* |

[Response 200](../_shared/examples/GET__api_v1_acceptance_report_tasks__task_id__download_200.json)

- **204** No data
### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `detail` | string |  | Error details |
| `origin` | string |  | WB internal service ID |
| `requestId` | string |  | Unique request ID |
| `title` | string |  | Error title |

[Response 400](../_shared/examples/GET__api_v1_warehouse_remains_tasks__task_id__status_400.json)

- **401** Unauthorized
- **402** Payment Required
### `404` Not found


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `detail` | string |  | Error details |
| `origin` | string |  | WB internal service ID |
| `requestId` | string |  | Unique request ID |
| `title` | string |  | Error title |

[Response 404](../_shared/examples/GET__api_v1_warehouse_remains_tasks__task_id__status_404.json)

- **429** Too Many Requests
