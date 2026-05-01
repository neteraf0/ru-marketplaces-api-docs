# `DELETE` /api/v3/click-collect/orders/{orderId}/meta

**Tag:** [In-Store Pickup Metadata](index.md)

**Delete Assembly Order Metadata**

Описание метода

This method is deprecated. It will be removed on [May 19](https://dev.wildberries.ru/en/release-notes?id=474)

> ⚠️ **Deprecated**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `orderId` | path | integer | ✓ | Assembly order ID |
| `key` | query | string | ✓ | The name of the metadata to be deleted (`imei`, `uin`, `gtin`, `sgtin`). Only one value is passed.  |

## Responses

- **204** Deleted
- **401** Unauthorized
- **402** Payment Required
- **403** Forbidden
- **404** Not Found
- **429** Too Many Requests
