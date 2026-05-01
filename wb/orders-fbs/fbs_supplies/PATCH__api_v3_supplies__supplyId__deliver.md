# `PATCH` /api/v3/supplies/{supplyId}/deliver

**Tag:** [FBS Supplies](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Move the Supply to the Delivery**

Описание метода

Closes the supply and moves all assembly orders to `complete` (`In Delivery`) status. You cannot add any assembly orders to the supply after it is closed.

If the supply wasn't handed over for delivery, than scanning its QR code or accepting the first product will automatically close the supply.

You can transfer the supply to delivery only if:
  - there is at least one assembly order
  - required labeling is specified for all assembly orders
  - labeling of all assembly orders passed validation

If the supply contains assembly orders with required UIN, make sure that you have created and uploaded the Delivery Contract Specification in advance. The [GIIS DMDK](https://minfin.gov.ru/ru/perfomance/jewels/dmdk) takes about 30 minutes to process changes in UIN statuses.


Request limit per one seller's account for FBS assembly orders, supplies and passes methods:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 300 requests | 200 ms | 20 requests |

One request with a response code of 409 is counted as 10 requests


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `supplyId` | path | string | ✓ | Supply ID *Example: `WB-GI-1234567`* |

## Responses

- **204** The supply moved to the delivery
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
### `409` Error closing supply


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data for the error |

[Response 409: SupplyHasZeroOrders](../_shared/examples/PATCH__api_v3_supplies__supplyId__deliver_409_SupplyHasZeroOrders.json)


[Response 409: MetaValidationFail](../_shared/examples/PATCH__api_v3_supplies__supplyId__deliver_409_MetaValidationFail.json)

- **429** Too Many Requests
