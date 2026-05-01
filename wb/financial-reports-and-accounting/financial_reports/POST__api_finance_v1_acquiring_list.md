# `POST` /api/finance/v1/acquiring/list

**Tag:** [Financial Reports](index.md)

**operationId:** `postV1AcquiringList`

**Server:** `https://finance-api.wildberries.ru`

**Acquiring Expenses Report List**

Описание метода

Method is available by token types: Personal, Service

The method returns acquiring expenses report list in the [the report table](https://seller.wildberries.ru/suppliers-mutual-settlements/reports-implementations/acquiring-reports) format.


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
## Responses

### `200` Success

*Array of:*

  | Field | Type | Req | Description |
  |-------|------|-----|-------------|
  | `reportId` | integer | ✓ | Report ID *Example: `307401554`* |
  | `sellerFinanceName` | string | ✓ | Seller name *Example: `ИП Кружинин В. Р.`* |
  | `dateFrom` | string | ✓ | Reporting period start date *Example: `2026-03-16`* |
  | `dateTo` | string | ✓ | Reporting period end date *Example: `2026-03-22`* |
  | `createDate` | string | ✓ | Report date *Example: `2026-03-31`* |
  | `currency` | string | ✓ | Report currency *Example: `RUB`* |
  | `acquiringFeeSum` | string | ✓ | Acquiring expenses *Example: `258`* |
  | `acquiringFeeVatSum` | string | ✓ | VAT included *Example: `83.79`* |

[Response 200](../_shared/examples/POST__api_finance_v1_acquiring_list_200.json)

- **204** No data
- **400** Bad Request
- **401** Unauthorized
- **429** Too Many Requests
