# `GET` /adv/v1/supplier/subjects

**Tag:** [Campaigns Creation](index.md)

**Server:** `https://advert-api.wildberries.ru`

**Subjects for Campaigns**

Описание метода

Returns subjects product cards from which are available for all campaigns


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 12 s | 1 request | 12 s | 5 requests |
| Service | 12 s | 1 request | 12 s | 5 requests |
| Base | 1 h | 2 requests | 30 min | 1 request |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `payment_type` | query | string |  | Payment type: - `cpm` — cost per mille - `cpc` — cost per click  |

## Responses

### `200` Success

*Array of:*

  | Field | Type | Req | Description |
  |-------|------|-----|-------------|
  | `id` | integer |  | Subject ID |
  | `name` | string |  | Subject |
  | `count` | integer |  | Number of WB articles (`nmId`) in this subject |

[Response 200: Array](../_shared/examples/GET__adv_v1_supplier_subjects_200_Array.json)


[Response 200: null](../_shared/examples/GET__adv_v1_supplier_subjects_200_null.json)

- **401** Unauthorized
- **404** Not found
- **429** Too Many Requests
