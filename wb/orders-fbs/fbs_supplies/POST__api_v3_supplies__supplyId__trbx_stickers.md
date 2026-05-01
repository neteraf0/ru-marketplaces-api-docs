# `POST` /api/v3/supplies/{supplyId}/trbx/stickers

**Tag:** [FBS Supplies](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Get the Supply Shipping Unit QR Code Stickers**

Описание метода

Returns QR-code stickers in svg, zplv (vertical), zplh (horizontal), png.
Available only if there are assembly orders in the shipping unit.
Stickers dimensions: 580x400 px.


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

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `trbxIds` | array | ✓ | List of supply shipping unit IDs for the sticker generation |
## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `stickers` | array |  |  |

[Response 200](../_shared/examples/POST__api_v3_supplies__supplyId__trbx_stickers_200.json)

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
- **429** Too Many Requests
