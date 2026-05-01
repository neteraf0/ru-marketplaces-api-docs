# `GET` /api/advert/v0/bids/recommendations

**Tag:** [Campaigns Management](index.md)

**Server:** `https://advert-api.wildberries.ru`

**Recommended bids for items and search clusters**

Описание метода

The method returns recommended bids for items and search clusters of the campaign.
Only for campaigns with cpm payment type — cost per mille.


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 min | 5 requests | 12 s | 5 requests |
| Service | 1 min | 5 requests | 12 s | 5 requests |
| Base | 1 h | 20 requests | 3 min | 1 request |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `nmId` | query | integer | ✓ | WB article *Example: `123456789`* |
| `advertId` | query | integer | ✓ | Campaign ID *Example: `987654321`* |

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `advertId` | integer |  | Campaign ID |
| `base` | V0BidRecommendationBase |  | Recommended bids for items |
| `nmId` | integer |  | WB article ID |
| `normQueries` | array |  | Recommended bids for search clusters |

[Response 200](../_shared/examples/GET__api_advert_v0_bids_recommendations_200.json)

### `400` Bad request

`string`

[Response 400: IncorrectTypeAdv](../_shared/examples/GET__api_advert_v0_bids_recommendations_400_IncorrectTypeAdv.json)


[Response 400: IncorrectSupplierIdAdv](../_shared/examples/POST__adv_v0_rename_400_IncorrectSupplierIdAdv.json)


[Response 400: IncorrectUsingMethods](../_shared/examples/GET__api_advert_v0_bids_recommendations_400_IncorrectUsingMethods.json)

- **401** Unauthorized
- **429** Too Many Requests
