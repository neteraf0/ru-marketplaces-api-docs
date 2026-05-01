# `GET` /api/v1/warehouse_remains/tasks/{task_id}/download

**Tag:** [Warehouses Inventory Report](index.md)

**Server:** `https://seller-analytics-api.wildberries.ru`

**Get the Report**

Описание метода

Returns the report by task ID


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 min | 1 request | 1 min | 1 request |
| Service | 1 min | 1 request | 1 min | 1 request |
| Base | 1 h | 4 requests | 15 min | 1 request |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `task_id` | path | string | ✓ | Generation task ID  *Example: `06e06887-9d9f-491f-b16a-bb1766fcb8d2`* |

## Responses

### `200` Success

*Array of:*

  | Field | Type | Req | Description |
  |-------|------|-----|-------------|
  | `brand` | string |  | Brand *Example: `Wonderful`* |
  | `subjectName` | string |  | Subject name *Example: `Фотоальбомы`* |
  | `vendorCode` | string |  | Seller's article *Example: `41058/прозрачный`* |
  | `nmId` | integer |  | WB article *Example: `183804172`* |
  | `barcode` | string |  | Barcode *Example: `2037031652319`* |
  | `techSize` | string |  | Size *Example: `0`* |
  | `volume` | number |  | Volume, L *Example: `1.33`* |
  | `warehouses` | array |  | Inventory and to and from the client. It will be included in the response only if `quantity` is non-zero |

[Response 200](../_shared/examples/GET__api_v1_warehouse_remains_tasks__task_id__download_200.json)

- **204** No data
### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `detail` | string |  | Error details |
| `origin` | string |  | WB internal service ID |
| `requestId` | string |  | Unique request ID |
| `title` | string |  | Error title |

[Response 400](../_shared/examples/GET__api_v1_warehouse_remains_tasks__task_id__download_400.json)

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
