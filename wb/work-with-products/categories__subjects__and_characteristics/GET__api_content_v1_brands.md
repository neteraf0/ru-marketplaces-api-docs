# `GET` /api/content/v1/brands

**Tag:** [Categories, Subjects, and Characteristics](index.md)

**Server:** `https://content-api.wildberries.ru`

**Brands**

Описание метода

The method returns list of brands by subject ID.


Request limit per one seller's account:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 s | 1 request | 1 s | 5 requests |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `subjectId` | query | integer | ✓ | Subject ID *Example: `1234`* |
| `next` | query | integer |  | Pagination parameter. Use the `next` value from the response to get the next data batch *Example: `1234`* |

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `brands` | array | ✓ |  |
| `next` | integer |  | Pagination parameter. Specify this value in the request to get the next batch. If the field is missing, you received all the data *Example: `1212`* |
| `total` | integer | ✓ | Total number of brands of the subject *Example: `344534`* |

[Response 200](../_shared/examples/GET__api_content_v1_brands_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `title` | string | ✓ | Error title |
| `detail` | string | ✓ | Error details |
| `origin` | string | ✓ | WB internal service ID |
| `requestId` | string | ✓ | Unique request ID |
| `errors` | array |  |  |

[Response 400: BrandsResponseBadRequest1](../_shared/examples/GET__api_content_v1_brands_400_BrandsResponseBadRequest1.json)


[Response 400: BrandsResponseBadRequest2](../_shared/examples/GET__api_content_v1_brands_400_BrandsResponseBadRequest2.json)

- **401** Unauthorized
### `404` Not found


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `title` | string | ✓ | Error title |
| `detail` | string | ✓ | Error details |
| `origin` | string | ✓ | WB internal service ID |
| `requestId` | string | ✓ | Unique request ID |
| `errors` | array |  |  |

[Response 404: BrandsResponseNotFound](../_shared/examples/GET__api_content_v1_brands_404_BrandsResponseNotFound.json)

- **429** Too Many Requests
