# `GET` /api/v1/supplies/{ID}/package

**Tag:** [Supplies Information](index.md)

**Server:** `https://supplies-api.wildberries.ru`

**Supply Package**

Описание метода

The method returns information about the package of the supply.


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 min | 30 requests | 2 s | 10 requests |
| Service | 1 min | 30 requests | 2 s | 10 requests |
| Base | 1 h | 2 requests | 30 min | 1 request |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `ID` | path | integer | ✓ | Supply ID |

## Responses

### `200` Success

*Array of:*

  | Field | Type | Req | Description |
  |-------|------|-----|-------------|
  | `packageCode` | string |  | Package barcode |
  | `quantity` | integer |  | Total quantity of products in the package, pieces |
  | `barcodes` | array |  | List of packed products |

[Response 200](../_shared/examples/GET__api_v1_supplies__ID__package_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `status` | integer |  | HTTP status code |
| `title` | string |  | Error ID |
| `detail` | string |  | Error description |
| `requestId` | string |  | Request ID |
| `origin` | string |  | Service that returned the error |

[Response 400: BadPathParamFormat](../_shared/examples/GET__api_v1_supplies__ID_400_BadPathParamFormat.json)


[Response 400: BadSupplyIDPackage](../_shared/examples/GET__api_v1_supplies__ID__package_400_BadSupplyIDPackage.json)


[Response 400: BadID](../_shared/examples/GET__api_v1_supplies__ID_400_BadID.json)

- **401** Unauthorized
- **402** Payment Required
- **429** Too Many Requests
