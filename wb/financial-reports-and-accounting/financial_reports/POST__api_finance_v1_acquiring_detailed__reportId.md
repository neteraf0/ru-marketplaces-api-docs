# `POST` /api/finance/v1/acquiring/detailed/{reportId}

**Tag:** [Financial Reports](index.md)

**operationId:** `postV1AcquiringDetailedReportId`

**Server:** `https://finance-api.wildberries.ru`

**Details for the Acquiring Expenses Reports by Report ID**

Описание метода

Method is available by token types: Personal, Service

The method returns details for the [acquiring expenses reports](https://seller.wildberries.ru/suppliers-mutual-settlements/reports-implementations/acquiring-reports) by report IDs.


Request limit per one seller's account:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 1 request | 1 min | 1 request |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `reportId` | path | integer | ✓ | Report ID |

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
  | `rrdId` | integer | ✓ | Row ID *Example: `1232610467`* |
  | `reportId` | integer | ✓ | Report ID *Example: `1234567`* |
  | `acqDate` | string | ✓ | Operation date *Example: `2026-03-21`* |
  | `acquiringBank` | string | ✓ | Acquiring bank *Example: `Тинькофф`* |
  | `tin` | string | ✓ | Taxpayer identification number *Example: `010101010101`* |
  | `taxRegistrationReasonCode` | string | ✓ | Tax registration reason code *Example: `7701123301`* |
  | `saleDate` | string | ✓ | Purchased on *Example: `2026-03-21`* |
  | `srid` | string | ✓ | Order ID.In the responses of the [FBS](./orders-fbs#tag/FBS-Assembly-Orders), [DBW](./orders-dbw#tag/DBW-Assembly-Orders), [DBS](./orders-dbs#tag/DBS-Assembly-Orders), and [In-Store Pickup](./in-store-pickup#tag/In-Store-Pickup-Assembly-Orders) assembly order methods, `srid` is `rid`  *Example: `D0.r3f80c3eec6f845c6840128b4c19986f9.0.0`* |
  | `docTypeName` | string | ✓ | Purchased or returned *Example: `Продажа`* |
  | `nmId` | integer | ✓ | WB article *Example: `1234567`* |
  | `retailAmount` | string | ✓ | Sales on WB *Example: `367`* |
  | `acquiringFee` | string | ✓ | Acquiring fee including VAT *Example: `14.89`* |
  | `acquiringFeeVat` | string | ✓ | VAT amount *Example: `4.06`* |
  | `invoiceNumber` | string | ✓ | Invoice No. *Example: `С/Ф 123`* |
  | `invoiceDate` | string | ✓ | Invoice date *Example: `2026-03-20`* |
  | `shkId` | integer | ✓ | Item No. *Example: `1239159661`* |
  | `currency` | string | ✓ | Report currency *Example: `RUB`* |

[Response 200](../_shared/examples/POST__api_finance_v1_acquiring_detailed__reportId_200.json)

- **204** No data
- **400** Bad Request
- **401** Unauthorized
- **429** Too Many Requests
