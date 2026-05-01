# `GET` /api/v1/supplier/orders

**Tag:** [Main Reports](index.md)

**Server:** `https://statistics-api.wildberries.ru`

**Orders**

Описание метода

The method returns order information.The data updated every 30 minutes.

1 line means 1 order and means 1 item.The `srid` field should be used to identify the order.

Data storage is guaranteed for no more than 90 days from the date of sale.

The responses do not include orders for which payment was not confirmed. For example, it could be orders with delayed payments or installment payments. However, if there are sales for such orders, you can get it using [details for the realization reports](./financial-reports-and-accounting#tag/Financial-Reports/paths/~1api~1v5~1supplier~1reportDetailByPeriod/get).
To receive all completed orders, use [Order Feed](https://seller.wildberries.ru/content-analytics/order-feed) in your personal account.


  The data in this report is preliminary and is used for operational monitoring


For a single response to a request with `flag=0` or without `flag`, a conditional limit of 80,000 rows is set. Therefore, more than one request may be necessary to retrieve all orders. In the second and subsequent requests, use the full value of the `lastChangeDate` field of the last row from the response of the previous request in the `dateFrom` parameter. If the response returns an empty array `[]`, all orders have already been retrieved.


Request limit per one seller's account:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 1 request | 1 min | 10 requests |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `dateFrom` | query | string | ✓ | Date and time of last change on the order. Date format: RFC3339. You may send date or date with time. Time could be specified in seconds or milliseconds. The time stands in Moscow time zone (UTC+3). Examples:   - `2019-06-20`   - `2019-06-20T23:59:59`   - `2019-06-20T00:00:00.12345`   - `2017-03-25T00:00:00`  |
| `flag` | query | integer |  | If parameter `flag=0` (or it doesn't exist in requests string), then call of API methods returns data, which value of field `lastChangeDate` (date and time of refreshing info of service) is greater or equal to the given parameter value  `dateFrom`. In this case the number of returned rows of data varies from 0 to approximately 80,000.  If parameter `flag=1`, then information about all orders or sales with the date will be uploaded, that equals to the passed parameter `dateFrom` (in this case the time in the date doesn't matter). Also the number of returned rows of data will be equal to the number of all orders or sales that were made on the specified date, passed in the `dateFrom` parameter.  |

## Responses

### `200` Success

*Array of:*

  | Field | Type | Req | Description |
  |-------|------|-----|-------------|
  | `date` | string |  | Date and time of order. This field equals to `dateFrom` in request if `flag=1`. If the time zone is not specified, then Moscow time UTC+3 is taken. |
  | `lastChangeDate` | string |  | Date and time of refreshing info of service. This field corresponds to the `dateFrom` parameter in the request if the `flag=0` parameter exist or not specified. If the time zone is not specified, then Moscow time UTC+3 is taken. |
  | `warehouseName` | string |  | Shipping warehouse name |
  | `warehouseType` | string (enum: Склад WB, Склад продавца) |  | Type of products storage warehouse:   - `Склад WB` —  WB warehouse   - `Склад продавца` — seller's warehouse  |
  | `countryName` | string |  | Country |
  | `oblastOkrugName` | string |  | Area |
  | `regionName` | string |  | Region |
  | `supplierArticle` | string |  | Supplier article |
  | `nmId` | integer |  | WB article |
  | `barcode` | string |  | Barcode |
  | `category` | string |  | Category |
  | `subject` | string |  | Subject |
  | `brand` | string |  | Brand |
  | `techSize` | string |  | Product size |
  | `incomeID` | integer |  | Supply number |
  | `isSupply` | boolean |  | Supply contract |
  | `isRealization` | boolean |  | Implementation contract |
  | `totalPrice` | number |  | Price without discounts |
  | `discountPercent` | integer |  | Seller's discount, % |
  | `spp` | number |  | WB discount, % |
  | `finishedPrice` | number |  | Price with all discounts, except WB Wallet sum |
  | `priceWithDisc` | number |  | Price with seller's discount, including WB Club discount |
  | `isCancel` | boolean |  | Order cancel:  - `true` — the order is cancelled  |
  | `cancelDate` | string |  | Date and time for order canceling. If order wasn't canceled, then `"0001-01-01T00:00:00"`. If the time zone is not specified, then Moscow time UTC+3 is taken. |
  | `sticker` | string |  | sticker ID |
  | `gNumber` | string |  | Buyer's cart ID. Orders within a single transaction will have the same `gNumber` |
  | `srid` | string |  | Unique order ID.  Note for those working with Marketplace API: `srid` equals `rid` in response of orders methods  |

[Response 200](../_shared/examples/GET__api_v1_supplier_orders_200.json)

### `400` Bad request


[Response 400: DateFromFieldRequired](../_shared/examples/GET__api_v1_supplier_stocks_400_DateFromFieldRequired.json)


[Response 400: DateFromValueNotValidated](../_shared/examples/GET__api_v1_supplier_stocks_400_DateFromValueNotValidated.json)

- **401** Unauthorized
- **402** Payment Required
- **429** Too Many Requests
