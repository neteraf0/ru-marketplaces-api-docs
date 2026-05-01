# `GET` /api/v1/supplier/stocks

**Tag:** [Main Reports](index.md)

**Server:** `https://statistics-api.wildberries.ru`

**Warehouse**

Описание метода

This method is deprecated. It will be removed on [June 23](https://dev.wildberries.ru/en/release-notes?id=494)


Request limit per one seller's account:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 1 request | 1 min | 10 requests |


> ⚠️ **Deprecated**

## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `dateFrom` | query | string | ✓ | Date and time of last change on the product. The earliest possible value should be entered to get the total leftover, e.g. `2019-06-20`. Date format: RFC3339. You may send date or date with time. Time could be specified in seconds or milliseconds. The time stands in Moscow time zone (UTC+3). Examples:   - `2019-06-20`   - `2019-06-20T23:59:59`   - `2019-06-20T00:00:00.12345`   - `2017-03-25T00:00:00`  |

## Responses

### `200` Success

*Array of:*

  | Field | Type | Req | Description |
  |-------|------|-----|-------------|
  | `lastChangeDate` | string |  | Date and time of refreshing info of service. This field corresponds to the `dateFrom` parameter in the request. If the time zone is not specified, then Moscow time UTC+3 is taken. |
  | `warehouseName` | string |  | Name of warehouse |
  | `supplierArticle` | string |  | Supplier article |
  | `nmId` | integer |  | WB article |
  | `barcode` | string |  | Barcode |
  | `quantity` | integer |  | Quantity available for sale (how many can be added to cart) |
  | `inWayToClient` | integer |  | On the way to the customer |
  | `inWayFromClient` | integer |  | On the way from the client |
  | `quantityFull` | integer |  | Total (unsold) quantity that is in stock (= `quantity` + on the way) |
  | `category` | string |  | Category |
  | `subject` | string |  | Subject |
  | `brand` | string |  | Brand |
  | `techSize` | string |  | Product size |
  | `Price` | number |  | Price |
  | `Discount` | number |  | Discount |
  | `isSupply` | boolean |  | Supply contract (internal process data) |
  | `isRealization` | boolean |  | Implementation contract (internal process data) |
  | `SCCode` | string |  | Contract code (internal process data) |

[Response 200](../_shared/examples/GET__api_v1_supplier_stocks_200.json)

### `400` Bad request


[Response 400: DateFromFieldRequired](../_shared/examples/GET__api_v1_supplier_stocks_400_DateFromFieldRequired.json)


[Response 400: DateFromValueNotValidated](../_shared/examples/GET__api_v1_supplier_stocks_400_DateFromValueNotValidated.json)

- **401** Unauthorized
- **402** Payment Required
- **429** Too Many Requests
