# `GET` /api/v3/supplies/{supplyId}/barcode

**Tag:** [FBS Supplies](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Get the Supply QR Code**

Описание метода

Returns the QR code in svg, zplv (vertical), zplh (horizontal), png.
Available only after the supply has been transferred to the delivery.
Available dimensions:
580x400 px


Request limit per one seller's account for FBS assembly orders, supplies and passes methods:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 300 requests | 200 ms | 20 requests |

One request with a response code of 409 is counted as 10 requests


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `supplyId` | path | string | ✓ | Supply ID *Example: `WB-GI-1234567`* |
| `type` | query | string (enum: svg, zplv, zplh, png) | ✓ | Sticker format |

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `barcode` | string |  | The encoded value of the sticker (supply id) *Example: `WB-GI-12345678`* |
| `file` | string |  | Base64 encoded sticker file in the requested format. *Example: `U3dhZ2dlciByb2Nrcw==`* |

[Response 200](../_shared/examples/GET__api_v3_supplies__supplyId__barcode_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data for the error |

[Response 400: IncorrectParameter](../_shared/examples/GET__api_v3_orders_400_IncorrectParameter.json)

- **401** Unauthorized
- **402** Payment Required
- **403** Forbidden
- **404** Not Found
### `409` Error requesting data


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data for the error |

[Response 409: SupplyNotClosed](../_shared/examples/GET__api_v3_supplies__supplyId__barcode_409_SupplyNotClosed.json)

- **429** Too Many Requests
