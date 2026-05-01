# `GET` /api/v1/supplies/{ID}/goods

**Tag:** [Supplies Information](index.md)

**Server:** `https://supplies-api.wildberries.ru`

**Supply Products**

Описание метода

The method returns information about the products in the supply.


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 min | 30 requests | 2 s | 10 requests |
| Service | 1 min | 30 requests | 2 s | 10 requests |
| Base | 1 h | 2 requests | 30 min | 1 request |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `limit` | query | integer |  | Number of objects in the response |
| `offset` | query | integer |  | From which element to start outputting data |
| `isPreorderID` | query | boolean |  | Search by:   - `true` — order ID, if you pass the order ID in `ID`   - `false` — supply ID, if you pass the supply ID in `ID`  |
| `ID` | path | integer | ✓ | ID of the supply or the order |

## Responses

### `200` Success

*Array of:*

  | Field | Type | Req | Description |
  |-------|------|-----|-------------|
  | `barcode` | string |  | Product barcode |
  | `vendorCode` | string |  | Seller's article |
  | `nmID` | integer |  | WB article |
  | `needKiz` | boolean |  | Is a labeling code [Chestny ZNAK](https://chestnyznak.ru/en) required for this product:   - `false` — not required   - `true` — required  |
  | `tnved` | string |  | HS-code.  If `"needKiz":true` and `"tnved":null`, it is required to specify the **HS-codes** in the [personal account](https://seller.wildberries.ru/new-goods) or through [API](./work-with-products#tag/Kartochki-tovarov/paths/~1content~1v2~1cards~1update/post)  |
  | `techSize` | string |  | Product size specified by the seller |
  | `color` | string |  | Product color |
  | `supplierBoxAmount` | integer |  | Specified in the package, pieces |
  | `quantity` | integer |  | Specified in the supply/order, pieces |
  | `readyForSaleQuantity` | integer |  | Ready for sale, pieces |
  | `acceptedQuantity` | integer |  | Accepted, pieces |
  | `unloadingQuantity` | integer |  | Total items at putaway, pieces |

[Response 200](../_shared/examples/GET__api_v1_supplies__ID__goods_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `status` | integer |  | HTTP status code |
| `title` | string |  | Error ID |
| `detail` | string |  | Error description |
| `requestId` | string |  | Request ID |
| `origin` | string |  | Service that returned the error |

[Response 400: BadOffsetFormat](../_shared/examples/POST__api_v1_supplies_400_BadOffsetFormat.json)


[Response 400: BadisPreorderIDFormat](../_shared/examples/GET__api_v1_supplies__ID_400_BadisPreorderIDFormat.json)


[Response 400: BadPathParamFormat](../_shared/examples/GET__api_v1_supplies__ID_400_BadPathParamFormat.json)


[Response 400: BadLimitFormat](../_shared/examples/POST__api_v1_supplies_400_BadLimitFormat.json)


[Response 400: BadSupplyIDGoods](../_shared/examples/GET__api_v1_supplies__ID__goods_400_BadSupplyIDGoods.json)


[Response 400: BadID](../_shared/examples/GET__api_v1_supplies__ID_400_BadID.json)

- **401** Unauthorized
- **402** Payment Required
- **429** Too Many Requests
