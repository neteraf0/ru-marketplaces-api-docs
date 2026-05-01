# `POST` /api/v2/nm-report/downloads/retry

**Tag:** [Seller Analytics CSV](index.md)

**Server:** `https://seller-analytics-api.wildberries.ru`

**Regenerate the Report**

Описание метода

The method creates a [repeated generation task](./analytics#tag/Seller-Analytics-CSV/paths/~1api~1v2~1nm-report~1downloads/post) of report with advanced seller analytics. This is necessary if you [received the status](./analytics#tag/Seller-Analytics-CSV/paths/~1api~1v2~1nm-report~1downloads/get) `FAILED` when generating the report.


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 min | 3 requests | 20 s | 3 requests |
| Service | 1 min | 3 requests | 20 s | 3 requests |
| Base | 1 h | 1 request | 1 h | 1 request |


## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `downloadId` | string |  | Report ID *Example: `06eea887-9d9f-491f-b16a-bb1766fcb8d2`* |
## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | string | ✓ | Notification that report re-generation has started *Example: `Retry`* |

[Response 200](../_shared/examples/POST__api_v2_nm_report_downloads_retry_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `title` | string | ✓ | Error title |
| `detail` | string | ✓ | Error details |
| `requestId` | string | ✓ | Unique request ID |
| `origin` | string | ✓ | WB internal service ID |

[Response 400: errorExample](../_shared/examples/GET__api_v2_nm_report_downloads_400_errorExample.json)

- **401** Unauthorized
### `403` Access denied


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `title` | string |  | Error title |
| `detail` | string |  | Error details |
| `requestId` | string |  | Unique request ID |
| `origin` | string |  | WB internal service ID |

[Response 403: errorExample](../_shared/examples/POST__api_v2_nm_report_downloads_403_errorExample.json)

- **429** Too Many Requests
