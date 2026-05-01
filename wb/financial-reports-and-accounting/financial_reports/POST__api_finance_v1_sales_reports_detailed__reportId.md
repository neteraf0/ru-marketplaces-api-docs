# `POST` /api/finance/v1/sales-reports/detailed/{reportId}

**Tag:** [Financial Reports](index.md)

**operationId:** `postV1SalesReportsDetailedReportId`

**Server:** `https://finance-api.wildberries.ru`

**Details for the Sales Reports by Report ID**

Описание метода

Method is available by token types: Personal, Service

The method returns details for the [sales reports](https://seller.wildberries.ru/suppliers-mutual-settlements) by report IDs.

The data is available since January 1, 2025.For technical reasons, the method is currently unavailable for your registration country. For now, you can get this data on [request by period](./financial-reports-and-accounting#tag/Financial-Reports/operation/postV1AcquiringDetailed).


Request limit per one seller's account:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 1 request | 1 min | 1 request |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `reportId` | path | integer | ✓ | Report ID.For daily reports, we recommend using non-standard libraries with [BigInt](https://www.npmjs.com/package/json-bigint) support, instead of standard deserialization |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `limit` | integer |  | Number of rows in the response *Example: `21100`* |
| `rrdId` | integer |  | Response row ID. Required to get the report in parts.Start report uploading with `"rrdid":0`. In subsequent requests, specify the `rrdId` value from the last row of the previous response.Repeat the request until you get `204` response  |
| `fields` | array |  | List of fields that will be returned in response. If the parameter is not specified, all fields are returned *Example: `['rrdId', 'nmId', 'docTypeName', 'retailAmount', 'acquiringFee', 'srid']`* |
## Responses

### `200` Success

*Array of:*

  | Field | Type | Req | Description |
  |-------|------|-----|-------------|
  | `reportId` | integer | ✓ | Report ID *Example: `1234567`* |
  | `dateFrom` | string | ✓ | Reporting period start date *Example: `2026-03-16`* |
  | `dateTo` | string | ✓ | Reporting period end date *Example: `2026-03-22`* |
  | `createDate` | string | ✓ | Report date *Example: `2026-03-23`* |
  | `currency` | string | ✓ | Report currency *Example: `RUB`* |
  | `reportType` | integer (enum: 1, 2, 3) | ✓ | Report type:   - `1` — general   - `2` — purchase   - `3` — purchase for Georgia  *Example: `1`* |
  | `rrdId` | integer | ✓ | Row ID *Example: `1232610467`* |
  | `giId` | integer | ✓ | Shipment ID *Example: `123456`* |
  | `dlvPrc` | number | ✓ | Fixed warehouse multiplier for shipments *Example: `1.8`* |
  | `fixTariffDateFrom` | string | ✓ | Warehouse multiplier fixed on *Example: `2026-03-18`* |
  | `fixTariffDateTo` | string | ✓ | Warehouse multiplier fixed until *Example: `2026-03-19`* |
  | `subjectName` | string | ✓ | Subject *Example: `Mini ovens`* |
  | `nmId` | integer | ✓ | WB article *Example: `1234567`* |
  | `brandName` | string | ✓ | Brand *Example: `BlahBlah`* |
  | `vendorCode` | string | ✓ | Seller's article *Example: `MAB123`* |
  | `title` | string | ✓ | Item name *Example: `ДС тарелка`* |
  | `techSize` | string | ✓ | Size *Example: `0`* |
  | `sku` | string | ✓ | SKU *Example: `1231312352310`* |
  | `docTypeName` | string | ✓ | Purchased or returned *Example: `Продажа`* |
  | `quantity` | integer | ✓ | Number of purchases and returns *Example: `1`* |
  | `retailPrice` | string | ✓ | Retail price *Example: `1249`* |
  | `retailAmount` | string | ✓ | Sales on WB *Example: `367`* |
  | `salePercent` | integer | ✓ | Agreed seller discount (%) |
  | `commissionPercent` | number | ✓ | WB fee rate (%) *Example: `24`* |
  | `officeName` | string | ✓ | Warehouse *Example: `Коледино`* |
  | `sellerOperName` | string | ✓ | Deduction reason *Example: `Продажа`* |
  | `orderDt` | string | ✓ | Ordered on *Example: `2026-03-14T00:00:00Z`* |
  | `saleDt` | string | ✓ | Purchased on *Example: `2026-03-21T00:00:00Z`* |
  | `rrDate` | string | ✓ | Operation date *Example: `2025-10-20`* |
  | `shkId` | integer | ✓ | Item No. *Example: `1239159661`* |
  | `retailPriceWithDisc` | string | ✓ | Price with applied agreed discount *Example: `399.68`* |
  | `deliveryAmount` | integer | ✓ | Number of deliveries |
  | `returnAmount` | integer | ✓ | Number of returns |
  | `deliveryService` | string | ✓ | Delivery to user *Example: `0`* |
  | `giBoxTypeName` | string | ✓ | Type of boxes *Example: `Монопаллета`* |
  | `productDiscountForReport` | number | ✓ | Final agreed discount (%) |
  | `sellerPromo` | string | ✓ | Promo code (%) *Example: `0`* |
  | `spp` | number | ✓ | WB discount (%) *Example: `25.31`* |
  | `kvwBase` | number | ✓ | VAT-exempt WB fee rate (%) *Example: `24.15`* |
  | `kvw` | number | ✓ | Final VAT-exempt WB fee rate (%) *Example: `1.81`* |
  | `supRatingUp` | number | ✓ | WB fee rate reduction due to rating (%) |
  | `isKgvpV2` | number | ✓ | WB fee rate reduction due to promos (%) |
  | `ppvzSalesCommission` | string | ✓ | VAT-exempt WB fee excluding attorney service cost *Example: `23.74`* |
  | `forPay` | string | ✓ | Net revenue for sold items *Example: `376.99`* |
  | `ppvzReward` | string | ✓ | Pickup point handover and return fee *Example: `0`* |
  | `acquiringFee` | string | ✓ | Compensation for payment services/payment services integration fee *Example: `14.89`* |
  | `acquiringPercent` | number | ✓ | Compensation amount for payment services/payment services integration fee amount (%) *Example: `4.06`* |
  | `paymentProcessing` | string | ✓ | Payment type: Compensation for payment services/payment services integration fee *Example: `Комиссия за организацию платежа с НДС`* |
  | `acquiringBank` | string | ✓ | Acquiring bank *Example: `Тинькофф`* |
  | `vw` | string | ✓ | VAT-exempt WB fee *Example: `22.25`* |
  | `vwNds` | string | ✓ | VAT on WB fee *Example: `4.45`* |
  | `ppvzOfficeName` | string | ✓ | Pickup point details *Example: `Москва Москва Очаковское шоссе 6к2`* |
  | `ppvzOfficeId` | integer | ✓ | Pickup point ID *Example: `105383`* |
  | `ppvzSupplierName` | string | ✓ | Pickup point name *Example: `ИП Жасмин`* |
  | `ppvzSupplierInn` | string | ✓ | Pickup point TIN *Example: `010101010101`* |
  | `declarationNumber` | string | ✓ | Cargo Customs Declaration No. |
  | `bonusTypeName` | string |  | Deduction reason *Example: `Штраф МП. Невыполненный заказ (отмена клиентом после недовоза)`* |
  | `stickerId` | string | ✓ | FBS sticker *Example: `1964038895`* |
  | `country` | string | ✓ | Delivery country *Example: `Россия`* |
  | `srvDbs` | boolean | ✓ | Paid delivery *Example: `True`* |
  | `penalty` | string | ✓ | Total penalties *Example: `231.35`* |
  | `additionalPayment` | string | ✓ | WB fee adjustment *Example: `0`* |
  | `rebillLogisticCost` | string | ✓ | Delivery and warehouse fee *Example: `1.349`* |
  | `rebillLogisticOrg` | string |  | Carrier *Example: `ИП Иванов Иван Иванович(123456789012)`* |
  | `paidStorage` | string | ✓ | Storage *Example: `12647.29`* |
  | `deduction` | string | ✓ | Deductions and payments *Example: `6354`* |
  | `paidAcceptance` | string | ✓ | Acceptance expenses *Example: `865`* |
  | `orderId` | integer | ✓ | Assembly order ID *Example: `2816993144`* |
  | `kiz` | string |  | Labeling code [Chestny ZNAK](https://chestnyznak.ru/en) *Example: `0102900000376311210G2CIS?ehge)S
91002A
92F9Qof4FDo/31Icm14kmtuVYQzLypxm3HWkC1vQ/+pVVjm1dNAth1laFMoAGn7yEMWlTjxIe7lQnJqZ7TRZhlHQ==`* |
  | `isB2b` | boolean | ✓ | B2B sale |
  | `trbxId` | string | ✓ | Master case ID *Example: `WB-TRBX-1234567`* |
  | `installmentCofinancingAmount` | string | ✓ | Co-financing discount *Example: `0`* |
  | `wibesDiscountPercent` | number | ✓ | Wibes discount (%) *Example: `1`* |
  | `cashbackAmount` | string | ✓ | Amount deducted for Loyalty Program rewards *Example: `2`* |
  | `cashbackDiscount` | string | ✓ | Loyalty Program discount compensation *Example: `19`* |
  | `cashbackCommissionChange` | string | ✓ | Loyalty program participation cost *Example: `0.2`* |
  | `paymentSchedule` | string | ✓ | One-time payment period change *Example: `-1`* |
  | `deliveryMethod` | string | ✓ | Sales model and item type *Example: `FBS, (МГТ)`* |
  | `sellerPromoId` | integer | ✓ | Custom promo discount ID *Example: `14350`* |
  | `sellerPromoDiscount` | number | ✓ | Custom promo discount (%) *Example: `3`* |
  | `loyaltyId` | integer | ✓ | Loyalty discount ID |
  | `loyaltyDiscount` | number | ✓ | Loyalty discount (%) |
  | `uuidPromocode` | string | ✓ | Promo code ID |
  | `salePricePromocodeDiscountPrc` | number | ✓ | Promo code discount (%) |
  | `articleSubstitution` | string | ✓ | Promo item article ID |
  | `salePriceAffiliatedDiscountPrc` | number | ✓ | Promo item article discount (%) |
  | `agencyVat` | number |  | Tax agent VAT withholding (%).Only for sellers from Kyrgyzstan  |
  | `salePriceWholesaleDiscountPrc` | number | ✓ | Wholesale discount for businesses (%) |
  | `orderUid` | string | ✓ | Cart ID.Orders in the same buyer's cart will have the same `orderUid`  *Example: `id375f16c4bec295d9995393af803ff7b`* |
  | `srid` | string | ✓ | Order ID.In the responses of the [FBS](./orders-fbs#tag/FBS-Assembly-Orders), [DBW](./orders-dbw#tag/DBW-Assembly-Orders), [DBS](./orders-dbs#tag/DBS-Assembly-Orders), and [In-Store Pickup](./in-store-pickup#tag/In-Store-Pickup-Assembly-Orders) assembly order methods, `srid` is `rid`  *Example: `0f1c3999172603062979867564654dac5b702849`* |

[Response 200](../_shared/examples/POST__api_finance_v1_sales_reports_detailed__reportId_200.json)

- **204** No data
- **400** Bad Request
- **401** Unauthorized
- **429** Too Many Requests
