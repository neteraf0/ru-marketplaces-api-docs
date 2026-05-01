# `GET` /api/v2/nm-report/downloads

**Tag:** [Seller Analytics CSV](index.md)

**Server:** `https://seller-analytics-api.wildberries.ru`

**Get the Reports List**

Описание метода

The method provides a list of reports with advanced seller analytics. The response contains [report IDs](./analytics#tag/Seller-Analytics-CSV/paths/~1api~1v2~1nm-report~1downloads/post) and generation statuses.


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 min | 3 requests | 20 s | 3 requests |
| Service | 1 min | 3 requests | 20 s | 3 requests |
| Base | 1 h | 1 request | 1 h | 1 request |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `filter[downloadIds]` | query | array |  | Report ID |

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | array | ✓ |  |

[Response 200](../_shared/examples/GET__api_v2_nm_report_downloads_200.json)

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
