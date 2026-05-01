# `POST` /api/finance/v1/sales-reports/list

**Tag:** [Financial Reports](index.md)

**operationId:** `postV1SalesReportsList`

**Server:** `https://finance-api.wildberries.ru`

**Sales Report List**

Описание метода

Method is available by token types: Personal, Service

The method returns sales report list in the [report table](https://seller.wildberries.ru/suppliers-mutual-settlements) format.

The list contains data since January 1, 2025.For technical reasons, the method is currently unavailable for your registration country.


Request limit per one seller's account:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 1 request | 1 min | 1 request |


## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `dateFrom` | string | ✓ | Report start date.Date in the [RFC3339](https://datatracker.ietf.org/doc/html/rfc3339) format. You may send date or date with time. Time could be specified in seconds or milliseconds. The time stands in Moscow time zone `UTC+3`.Examples:   - `2025-06-20`   - `2025-06-20T23:59:59`   - `2025-06-20T00:00:00.12345`   - `2025-06-25T00:00:00`  *Example: `2026-03-17`* |
| `dateTo` | string | ✓ | Report end date.Date in the [RFC3339](https://datatracker.ietf.org/doc/html/rfc3339) format. You may send date or date with time. Time could be specified in seconds or milliseconds. The time stands in Moscow time zone `UTC+3`.Examples:   - `2025-06-20`   - `2025-06-20T23:59:59`   - `2025-06-20T00:00:00.12345`   - `2025-06-20T00:00:00`  *Example: `2026-03-20`* |
| `limit` | integer |  | Number of reports in the response *Example: `211`* |
| `offset` | integer |  | How many results to skip. For example, with value `10`, the response will start with the 11 element *Example: `345`* |
| `period` | string (enum: daily, weekly) |  | Report periodicity:   - `weekly`   - `daily`  *Example: `daily`* |
## Responses

### `200` Success

*Array of:*

  | Field | Type | Req | Description |
  |-------|------|-----|-------------|
  | `reportId` | integer | ✓ | Report ID *Example: `307401554`* |
  | `sellerFinanceName` | string | ✓ | Seller name *Example: `ИП Кружинин В. Р.`* |
  | `dateFrom` | string | ✓ | Reporting period start date *Example: `2026-03-16`* |
  | `dateTo` | string | ✓ | Reporting period end date *Example: `2026-03-22`* |
  | `createDate` | string | ✓ | Report date *Example: `2026-03-23`* |
  | `currency` | string | ✓ | Report currency *Example: `RUB`* |
  | `reportType` | integer (enum: 1, 2, 3) | ✓ | Report type:   - `1` — general   - `2` — by purchase   - `3` — by purchase for Georgia  *Example: `1`* |
  | `retailAmountSum` | string | ✓ | Sales *Example: `258`* |
  | `forPaySum` | string | ✓ | Net revenue *Example: `183.79`* |
  | `avgSalePercent` | number | ✓ | Agreed discount (%) |
  | `deliveryServiceSum` | string | ✓ | Logistics cost *Example: `2558.47`* |
  | `paidStorageSum` | string | ✓ | Storage cost *Example: `626.84`* |
  | `paidAcceptanceSum` | string | ✓ | Acceptance cost *Example: `243.81`* |
  | `deductionSum` | string | ✓ | Other deductions and payments *Example: `150`* |
  | `penaltySum` | string | ✓ | Total penalties *Example: `1457.61`* |
  | `additionalPaymentSum` | string | ✓ | WB fee adjustment *Example: `9509.71`* |
  | `cashbackAmountSum` | string | ✓ | Amount deducted for Loyalty Program rewards *Example: `2`* |
  | `cashbackDiscountSum` | string | ✓ | Loyalty Program discount compensation *Example: `19`* |
  | `cashbackCommissionChangeSum` | string | ✓ | Loyalty Program participation cost *Example: `0.2`* |
  | `paymentSchedule` | string | ✓ | One-time payment period change *Example: `-1`* |
  | `bankPaymentSum` | string | ✓ | Total *Example: `5172.94`* |

[Response 200](../_shared/examples/POST__api_finance_v1_sales_reports_list_200.json)

- **204** No data
- **400** Bad Request
- **401** Unauthorized
- **429** Too Many Requests
