# `PUT` /api/v3/dbw/warehouses/{warehouseId}/contacts

**Tag:** [Seller Warehouses](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Update Contacts List**

Описание метода

Updates the seller's warehouse contact list.


  The contact list is overwritten upon update. Therefore, you need to include all contact list parameters in the request, including those you do not intend to update.


Only for warehouses with delivery type `3` — WB courier (DBW).

A maximum of 5 contacts can be added to the warehouse.
To delete contacts, send an empty `contacts` array.


Request limit  per one seller's account for DBW methods:

    for getting and updating contact lists
    for getting and deleting metadata
    assembly orders


| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 300 requests | 200 ms | 20 requests |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `warehouseId` | path | integer | ✓ | The seller's warehouse ID *Example: `2`* |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `contacts` | array |  |  |
## Responses

- **204** Updated
### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data enriching the error |

[Response 400: IncorrectParameter](../_shared/examples/PUT__api_v3_stocks__warehouseId_400_IncorrectParameter.json)


[Response 400: IncorrectRequestBody](../_shared/examples/PUT__api_v3_stocks__warehouseId_400_IncorrectRequestBody.json)


[Response 400: UploadDataLimitDbw](../_shared/examples/PUT__api_v3_dbw_warehouses__warehouseId__contacts_400_UploadDataLimitDbw.json)


[Response 400: IncorrectRequest](../_shared/examples/PUT__api_v3_stocks__warehouseId_400_IncorrectRequest.json)

- **401** Unauthorized
- **402** Payment Required
- **403** Forbidden
- **429** Too Many Requests
