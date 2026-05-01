# `POST` /api/v1/supplies

**Tag:** [Supplies Information](index.md)

**Server:** `https://supplies-api.wildberries.ru`

**Supplies List**

Описание метода

The method returns a list of supplies, the last 1000 supplies by default.


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

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `dates` | array |  | Filter by dates |
| `statusIDs` | array |  | Filter the supply by statuses. Possible values:   - `1` — Not planned   - `2` — Planned   - `3` — Unloading allowed   - `4` — Accepting   - `5` — Accepted   - `6` — Unloaded at the gate  |

[Request example](examples/POST__api_v1_supplies_req.json)

## Responses

### `200` Success

*Array of:*

  | Field | Type | Req | Description |
  |-------|------|-----|-------------|
  | `phone` | string |  | Phone number of the user that created the supply |
  | `supplyID` | integer |  | Supply ID. If `null`, it's an order, so use the value of the `preorderID` field |
  | `preorderID` | integer |  | Order ID (unplanned supply). Will be `0` for all virtual supplies |
  | `createDate` | string |  | Date and time the supply was created |
  | `supplyDate` | string |  | Planned unloading date |
  | `factDate` | string |  | Actual unloading date |
  | `updatedDate` | string |  | Date of the supply update |
  | `statusID` | integer (enum: 1, 2, 3, 4, 5, 6) |  | Supply status ID: - `1` — Not planned - `2` — Planned - `3` — Unloading allowed - `4` — Accepting - `5` — Accepted - `6` — Unloaded at the gate  |
  | `boxTypeID` |  |  | Supply type ID:   - `0` — Without boxes (virtual supply)   - `1` and `2` — Boxes   - `5` — Monopallets   - `6` — Supersafe  |
  | `isBoxOnPallet` | boolean |  | **Pallet with Single Items** — supply type:   - `true` — yes   - `false` — no    The field is returned only when `"boxTypeID": 2`  |

[Response 200](../_shared/examples/POST__api_v1_supplies_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `status` | integer |  | HTTP status code |
| `title` | string |  | Error ID |
| `detail` | string |  | Error description |
| `requestId` | string |  | Request ID |
| `origin` | string |  | Service that returned the error |

[Response 400: BadTypeFormat](../_shared/examples/POST__api_v1_supplies_400_BadTypeFormat.json)


[Response 400: BadLimitFormat](../_shared/examples/POST__api_v1_supplies_400_BadLimitFormat.json)


[Response 400: BadOffsetFormat](../_shared/examples/POST__api_v1_supplies_400_BadOffsetFormat.json)


[Response 400: BadFromOrTill](../_shared/examples/POST__api_v1_supplies_400_BadFromOrTill.json)


[Response 400: BadStatusIDs](../_shared/examples/POST__api_v1_supplies_400_BadStatusIDs.json)

- **401** Unauthorized
- **402** Payment Required
- **429** Too Many Requests
