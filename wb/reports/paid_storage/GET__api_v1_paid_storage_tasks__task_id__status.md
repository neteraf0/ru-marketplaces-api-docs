# `GET` /api/v1/paid_storage/tasks/{task_id}/status

**Tag:** [Paid Storage](index.md)

**Server:** `https://seller-analytics-api.wildberries.ru`

**Check the Status**

Описание метода

Returns the status of task


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 5 s | 1 request | 5 s | 5 requests |
| Service | 5 s | 1 request | 5 s | 5 requests |
| Base | 1 h | 2 requests | 30 min | 2 requests |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `task_id` | path | string | ✓ | Task ID  *Example: `06e06887-9d9f-491f-b16a-bb1766fcb8d2`* |

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | GetTasksResponseData |  |  |

[Response 200: GetTasksResponseData](../_shared/examples/GET__api_v1_warehouse_remains_tasks__task_id__status_200_GetTasksResponseData.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `detail` | string |  | Error details |
| `origin` | string |  | WB internal service ID |
| `requestId` | string |  | Unique request ID |
| `title` | string |  | Error title |

[Response 400](../_shared/examples/GET__api_v1_warehouse_remains_tasks__task_id__status_400.json)

- **401** Unauthorized
### `404` Not found


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `detail` | string |  | Error details |
| `origin` | string |  | WB internal service ID |
| `requestId` | string |  | Unique request ID |
| `title` | string |  | Error title |

[Response 404](../_shared/examples/GET__api_v1_warehouse_remains_tasks__task_id__status_404.json)

- **429** Too Many Requests
