# `GET` /api/v3/dbw/orders/{orderId}/meta

**Tag:** [DBW Metadata](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Get Order Metadata**

Описание метода

This method is deprecated. It will be removed on [July 27](https://dev.wildberries.ru/en/release-notes?id=508)


Request limit  per one seller's account for DBW methods:

    for getting and updating contact lists
    for getting and deleting metadata
    assembly orders


| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 300 requests | 200 ms | 20 requests |


> ⚠️ **Deprecated**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `orderId` | path | integer | ✓ | Assembly order ID *Example: `5632423`* |

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `meta` | Meta |  | Assembly order metadata |

[Response 200](../_shared/examples/GET__api_v3_dbw_orders__orderId__meta_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data for the error |

[Response 400: IncorrectParameter](../_shared/examples/GET__api_v3_dbw_orders_400_IncorrectParameter.json)

- **401** Unauthorized
- **402** Payment Required
- **403** Forbidden
- **404** Not Found
- **429** Too Many Requests
