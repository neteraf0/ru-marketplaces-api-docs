# `GET` /api/v3/click-collect/orders/{orderId}/meta

**Tag:** [In-Store Pickup Metadata](index.md)

**Get Assembly Order Metadata**

Описание метода

This method is deprecated. It will be removed on [May 19](https://dev.wildberries.ru/en/release-notes?id=474)


Request limit per one seller's account for all methods for adding In-Store Pickup metadata:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 min | 300 requests | 200 ms | 20 requests |
| Service | 1 min | 300 requests | 200 ms | 20 requests |
| Base | 1 h | 10 requests | 6 min | 1 request |

One request with a response code of 409 is counted as 10 requests


> ⚠️ **Deprecated**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `orderId` | path | integer | ✓ | Assembly order ID |

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `meta` | object |  | Assembly order metadata |

[Response 200](../_shared/examples/GET__api_v3_click_collect_orders__orderId__meta_200.json)

- **401** Unauthorized
- **402** Payment Required
- **403** Forbidden
- **404** Not Found
- **429** Too Many Requests
