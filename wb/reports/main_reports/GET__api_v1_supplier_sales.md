# `GET` /api/v1/supplier/sales

**Tag:** [Main Reports](index.md)

**Server:** `https://statistics-api.wildberries.ru`

**Sales**

Описание метода

The method returns sale and return information.The data updated every 30 minutes.

1 line means 1 sale/return and means 1 item.The `srid` field should be used to identify the order.

Data storage is guaranteed for no more than 90 days from the date of sale.


  The data in this report is preliminary and is used for operational monitoring


  - The responses do not include orders for which payment was not confirmed, even if these orders are in details for the realization reports. For example, it could be orders with delayed payments or installment payments
  - The values of the `priceWithDisc` and `forPay` fields are calculated using a simplified logic and may differ from `retail_price_withdisc_rub` and `ppvz_for_pay`, respectively, in details for the realization reports
  - The fields `finishedPrice`, `priceWithDisc`, and `forPay` may temporarily have the value `0`: data is filled in asynchronously and updated within 24 hours
  - For orders that are paid in a currency other than the seller's currency, prices may be rounded due to currency conversion

Use [details for the realization reports](./financial-reports-and-accounting#tag/Financial-Reports/paths/~1api~1v5~1supplier~1reportDetailByPeriod/get) for accurate financial calculations, reconciliation, and reporting.

For a single response to a request with `flag=0` or without `flag`, a conditional limit of 80,000 rows is set. Therefore, more than one request may be necessary to retrieve all sales and returns. In the second and subsequent requests, use the full value of the `lastChangeDate` field of the last row from the response of the previous request in the `dateFrom` parameter. If the response returns an empty array `[]`, all sales and returns have already been retrieved.


Request limit per one seller's account:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 1 request | 1 min | 1 request |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `dateFrom` | query | string | ✓ | Date and time of last change on the sale/return. Date format: RFC3339. You may send date or date with time. Time could be specified in seconds or milliseconds. The time stands in Moscow time zone (UTC+3). Examples:   - `2019-06-20`   - `2019-06-20T23:59:59`   - `2019-06-20T00:00:00.12345`   - `2017-03-25T00:00:00`  |
| `flag` | query | integer |  | If parameter `flag=0` (or it doesn't exist in requests string), then call of API methods returns data, which value of field `lastChangeDate` (date and time of refreshing info of service) is greater or equal to the given parameter value  `dateFrom`. In this case the number of returned rows of data varies from 0 to approximately 80,000.  If parameter `flag=1`, then information about all orders or sales with the date will be uploaded, that equals to the passed parameter `dateFrom` (in this case the time in the date doesn't matter). Also the number of returned rows of data will be equal to the number of all orders or sales that were made on the specified date, passed in the `dateFrom` parameter.  |

## Responses

### `200` Success

*Array of:*

  | Field | Type | Req | Description |
  |-------|------|-----|-------------|
  | `date` | string |  | Date and time of sale. This field equals to `dateFrom` in request if `flag`=1. If the time zone is not specified, then Moscow time (UTC+3) is taken |
  | `lastChangeDate` | string |  | Date and time of refreshing info of service. This field corresponds to the `dateFrom` parameter in the request if the `flag`=0 parameter exist or not specified. If the time zone is not specified, then Moscow time (UTC+3) is taken |
  | `warehouseName` | string |  | Shipping warehouse |
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
  | `paymentSaleAmount` | integer |  | Discount for payment with WB Wallet, ₽ |
  | `forPay` | number |  | To transfer to the seller.Data synchronization takes up to 24 hours, during which time the value `0` can be displayed in the field |
  | `finishedPrice` | number |  | Price with all discounts.Data synchronization takes up to 24 hours, during which time the value `0` can be displayed in the field |
  | `priceWithDisc` | number |  | Price with seller's discount, including WB Club discount, from which the amount to be transferred to the seller `forPay` is calculated.Data synchronization takes up to 24 hours, during which time the value `0` can be displayed in the field |
  | `saleID` | string |  | The unique ID of the sale/return.  - `S**********` — sale - `R**********` — return (to WB warehouse)  |
  | `sticker` | string |  | sticker ID |
  | `gNumber` | string |  | Buyer's cart ID. Orders within a single transaction will have the same `gNumber` |
  | `srid` | string |  | Unique order ID.  Note for those working with Marketplace API: `srid` equals `rid` in response of orders methods  |

[Response 200](../_shared/examples/GET__api_v1_supplier_sales_200.json)

### `400` Bad request


[Response 400: DateFromFieldRequired](../_shared/examples/GET__api_v1_supplier_stocks_400_DateFromFieldRequired.json)


[Response 400: DateFromValueNotValidated](../_shared/examples/GET__api_v1_supplier_stocks_400_DateFromValueNotValidated.json)

- **401** Unauthorized
- **402** Payment Required
- **429** Too Many Requests
