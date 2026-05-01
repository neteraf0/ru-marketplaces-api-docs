# `GET` /api/v5/supplier/reportDetailByPeriod

**Tag:** [Financial Reports](index.md)

**Server:** `https://statistics-api.wildberries.ru`

**Realization Sales Report**

Описание метода

This method is deprecated. It will be removed on [July 15](https://dev.wildberries.ru/en/release-notes?id=498).


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 min | 1 request | 1 min | 10 requests |
| Service | 1 min | 1 request | 1 min | 10 requests |
| Base | 24 h | 2 requests | 12 h | 1 request |


> ⚠️ **Deprecated**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `dateFrom` | query | string | ✓ | Report start date. Date format: RFC3339. You may send date or date with time. Time could be specified in seconds or milliseconds. The time stands in Moscow time zone (UTC+3). Examples:   - `2019-06-20`   - `2019-06-20T23:59:59`   - `2019-06-20T00:00:00.12345`   - `2017-03-25T00:00:00`  |
| `dateTo` | query | string | ✓ | Report end date |
| `limit` | query | integer |  | Number of strings in the response |
| `rrdid` | query | integer |  | The unique ID of the report line. Required to receive the report in parts.  Report loading must start with `rrdid = 0` and on subsequent API calls, pass the `rrd_id` value in the request from the row line received as a result of the previous call.  Thus, to load a single report, you may need to call the API until a 204 response is returned.  |
| `period` | query | string (enum: weekly, daily) |  | Report periodicity:   - `weekly`   - `daily`  |

## Responses

### `200` Success

*Array of:*

  | Field | Type | Req | Description |
  |-------|------|-----|-------------|
  | `realizationreport_id` | integer |  | Report no *Example: `1234567`* |
  | `date_from` | string |  | Reporting period start date *Example: `2022-10-17`* |
  | `date_to` | string |  | Reporting period end date *Example: `2022-10-23`* |
  | `create_dt` | string |  | Report formation date *Example: `2022-10-24`* |
  | `currency_name` | string |  | Currency of report *Example: `руб`* |
  | `suppliercontract_code` | object |  | Contract |
  | `rrd_id` | integer |  | Row number *Example: `1232610467`* |
  | `gi_id` | integer |  | Supply number *Example: `123456`* |
  | `dlv_prc` | number |  | Fixed warehouse supply ratio *Example: `1.8`* |
  | `fix_tariff_date_from` | string |  | Commitment start date *Example: `2024-10-23`* |
  | `fix_tariff_date_to` | string |  | Commit expiration date *Example: `2024-11-18`* |
  | `subject_name` | string |  | Subject *Example: `Mini ovens`* |
  | `nm_id` | integer |  | WB article *Example: `1234567`* |
  | `brand_name` | string |  | Brand *Example: `BlahBlah`* |
  | `sa_name` | string |  | Seller's article *Example: `MAB123`* |
  | `ts_name` | string |  | Size *Example: `0`* |
  | `barcode` | string |  | Barcode *Example: `1231312352310`* |
  | `doc_type_name` | string |  | Type of document *Example: `Продажа`* |
  | `quantity` | integer |  | Quantity *Example: `1`* |
  | `retail_price` | number |  | Retail price *Example: `1249`* |
  | `retail_amount` | number |  | Wildberries sold the Product (Sales) *Example: `367`* |
  | `sale_percent` | integer |  | Harmonized product discount, % |
  | `commission_percent` | number |  | The size of the Wildberries remuneration coefficient (cWR), % *Example: `24`* |
  | `office_name` | string |  | Warehouse *Example: `Коледино`* |
  | `supplier_oper_name` | string |  | Justification for payment *Example: `Продажа`* |
  | `order_dt` | string |  | Date of order.  Sent with an explicit indication of the time zone *Example: `2022-10-13T00:00:00Z`* |
  | `sale_dt` | string |  | Date of sale.  Sent with an explicit indication of the time zone *Example: `2022-10-20T00:00:00Z`* |
  | `rr_dt` | string |  | Operation date *Example: `2022-10-20`* |
  | `shk_id` | integer |  | Barcode of the product unit *Example: `1239159661`* |
  | `retail_price_withdisc_rub` | number |  | Retail price based on agreed discount *Example: `399.68`* |
  | `delivery_amount` | integer |  | Number of deliveries |
  | `return_amount` | integer |  | Number of returns |
  | `delivery_rub` | number |  | Delivery services to buyer |
  | `gi_box_type_name` | string |  | Type of boxes *Example: `Монопаллета`* |
  | `product_discount_for_report` | number |  | Final agreed discount, % |
  | `supplier_promo` | number |  | Promo code, % |
  | `ppvz_spp_prc` | number |  | Regular Customer Discount (RCD), % *Example: `25.31`* |
  | `ppvz_kvw_prc_base` | number |  | The amount of the Wildberries remuneration coefficient (cWR) without VAT, % Basic *Example: `24.15`* |
  | `ppvz_kvw_prc` | number |  | The final Wildberries remuneration coefficient (cWR) without VAT, % Basic *Example: `1.81`* |
  | `sup_rating_prc_up` | number |  | The amount of reduction in the Wildberries remuneration coefficient (cWR) due to the rating, % |
  | `is_kgvp_v2` | number |  | The amount of reduction in the Wildberries remuneration coefficient (cWR) due to the promotion, % |
  | `ppvz_sales_commission` | number |  | Remuneration from sale to deduction of the services of the attorney without VAT *Example: `23.74`* |
  | `ppvz_for_pay` | number |  | To transfer to the seller for the sold products *Example: `376.99`* |
  | `ppvz_reward` | number |  | Refund for the delivery and return of goods to the point of delivery of orders (PDO) |
  | `acquiring_fee` | number |  | Compensation for payment services/payment services integration fee *Example: `14.89`* |
  | `acquiring_percent` | number |  | Compensation amount for payment services/payment services integration fee amount, % *Example: `4.06`* |
  | `payment_processing` | string |  | Payment type: Compensation for payment services/payment services integration fee *Example: `Комиссия за организацию платежа с НДС`* |
  | `acquiring_bank` | string |  | Name of the acquiring bank *Example: `Тинькофф`* |
  | `ppvz_vw` | number |  | Wildberries Remuneration (WR) without VAT *Example: `22.25`* |
  | `ppvz_vw_nds` | number |  | VAT on Wildberries Remuneration *Example: `4.45`* |
  | `ppvz_office_name` | string |  | Name of delivery office *Example: `Пункт самовывоза (ПВЗ)`* |
  | `ppvz_office_id` | integer |  | Office number *Example: `105383`* |
  | `ppvz_supplier_id` | integer |  | Partner number *Example: `186465`* |
  | `ppvz_supplier_name` | string |  | Partner *Example: `ИП Жасмин`* |
  | `ppvz_inn` | string |  | Taxpayer identification number (TIN) of the partner *Example: `010101010101`* |
  | `declaration_number` | string |  | Customs declaration number |
  | `bonus_type_name` | string |  | Types of Logistics, Penalties, and Wildberries Reward Adjustments. The field will be in the response if a value exists  *Example: `Штраф МП. Невыполненный заказ (отмена клиентом после недовоза)`* |
  | `sticker_id` | string |  | The digital value of the sticker that is attached to the product during the order assembly process using the Marketplace scheme *Example: `1964038895`* |
  | `site_country` | string |  | Country of sale *Example: `RU`* |
  | `srv_dbs` | boolean |  | A sign of a paid delivery service *Example: `True`* |
  | `penalty` | number |  | Total fines *Example: `231.35`* |
  | `additional_payment` | number |  | Wildberries Reward Adjustment |
  | `rebill_logistic_cost` | number |  | Reimbursement of freight costs/warehouse operations with goods *Example: `1.349`* |
  | `rebill_logistic_org` | string |  | Organizer of transport. The field will be in the response if there is a value  *Example: `ИП Иванов Иван Иванович(123456789012)`* |
  | `storage_fee` | number |  | Storage *Example: `12647.29`* |
  | `deduction` | number |  | Deductions *Example: `6354`* |
  | `acceptance` | number |  | Acceptance expenses *Example: `865`* |
  | `assembly_id` | integer |  | Assembly task number *Example: `2816993144`* |
  | `kiz` | string |  | Labeling code [Chestny ZNAK](https://chestnyznak.ru/en). The field will be in the response if value exists  *Example: `0102900000376311210G2CIS?ehge)S
91002A
92F9Qof4FDo/31Icm14kmtuVYQzLypxm3HWkC1vQ/+pVVjm1dNAth1laFMoAGn7yEMWlTjxIe7lQnJqZ7TRZhlHQ==`* |
  | `srid` | string |  | The unique identifier for the order.  Note for those using the Marketplace API: `srid` is equal to `rid` in assembly tasks methods responses  *Example: `0f1c3999172603062979867564654dac5b702849`* |
  | `report_type` | integer (enum: 1, 2, 3) |  | Report type:   - `1` — general   - `2` — by purchase   - `3` — by purchase for Georgia  *Example: `1`* |
  | `is_legal_entity` | boolean |  | B2B sale attribute |
  | `trbx_id` | string |  | Item processing master case No. *Example: `WB-TRBX-1234567`* |
  | `installment_cofinancing_amount` | number |  | Discount on the co-financing programme |
  | `wibes_wb_discount_percent` | number |  | Wibes discount, % *Example: `1`* |
  | `cashback_amount` | number |  | Amount withheld for accured loyalty program points |
  | `cashback_discount` | number |  | Reimbursement of the Loyalty Program |
  | `cashback_commission_change` | number |  | Loyalty program participation cost |
  | `order_uid` | string |  | Transaction ID. Orders in the same buyer's cart will have the same `order_uid` *Example: `id375f16c4bec295d9995393af803ff7b`* |
  | `payment_schedule` | number |  | One-time instant money withdrawal rate |
  | `delivery_method` | string |  | Sale method and cargo type *Example: `FBS, (МГТ)`* |
  | `seller_promo_id` | integer |  | Seller own promo ID with additional discount *Example: `14350`* |
  | `seller_promo_discount` | number |  | Additional discount from seller promo, % *Example: `3`* |
  | `loyalty_id` | integer |  | Seller loyalty program discount ID |
  | `loyalty_discount` | number |  | Seller loyalty program discount, % |
  | `uuid_promocode` | string |  | Promo code ID |
  | `sale_price_promocode_discount_prc` | number |  | Promo code discount, % |
  | `article_substitution` | string |  | Promo item article ID |
  | `sale_price_affiliated_discount_prc` | number |  | Promo item article discount, % |
  | `agency_vat` | number |  | Tax agent VAT withholding, %. Only for sellers from Kyrgyzstan. The field will be in the response if value exists  |
  | `sale_price_wholesale_discount_prc` | number |  | Wholesale discount for businesses, % |

[Response 200](../_shared/examples/GET__api_v5_supplier_reportDetailByPeriod_200.json)

- **204** No data
- **400** Bad Request
- **401** Unauthorized
- **402** Payment Required
- **429** Too Many Requests
