# `POST` /content/v2/cards/error/list

**Tag:** [Product Cards](index.md)

**Server:** `https://content-api.wildberries.ru`

**List of Failed Product Cards with Errors**

Описание метода

Returns the list of product cards ([drafts](https://seller.wildberries.ru/new-goods/error-cards)) and the list of errors encountered during product card creation or editing.

The data is returned in batches. One batch contains:
  - all errors for one `variants` array in one request during product cards [creation](./work-with-products#tag/Creating-Product-Cards/paths/~1content~1v2~1cards~1upload/post)
  - all errors in one request during product cards [creation with merge](./work-with-products#tag/Creating-Product-Cards/paths/~1content~1v2~1cards~1upload~1add/post) or [editing](./work-with-products#tag/Product-Cards/paths/~1content~1v2~1cards~1update/post).

To get more than 100 batches, use pagination:

  1. Make first request:

        {
          "cursor": {
            "limit": 100
          },
          "order": {
            "ascending": true
          }
        }
  2. Copy `"updatedAt":"***","batchUUID":"***"` from the response `cursor` and paste into the request `cursor`.
  3. Repeat the request.
  4. Repeat 2 and 3, until you receive in the response `"next":false`. This will mean that you have received all the batches.


  To delete product card from the errors list, repeat the request for creating or creating with merge and updating request with fixed errors


Request limit per one seller's account:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 10 requests | 6 s | 5 requests |


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `locale` | query | string |  | Language of subject names:   - `ru` — Russian   - `en` — English   - `zh` — Chinese  *Example: `en`* |

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `cursor` | swagger.PublicErrorsCursorInput |  | Paginator |
| `order` | swagger.PublicErrorsOrderV2 |  | The order of return of batches |

[Request example](examples/POST__content_v2_cards_error_list_req.json)

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | models.ErrorTableListPublicRespV2 | ✓ | Response data |
| `error` | boolean | ✓ | Error flag |
| `errorText` | string | ✓ | Error text |
| `additionalErrors` | object | ✓ | Additional errors |

[Response 200](../_shared/examples/POST__content_v2_cards_error_list_200.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object |  | Error data |
| `error` | boolean |  | Error flag |
| `errorText` | string |  | Error text |
| `additionalErrors` | object |  | Additional errors |

[Response 400](../_shared/examples/GET__content_v2_object_parent_all_400.json)

- **401** Unauthorized
### `403` Access denied


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | object |  | Error data |
| `error` | boolean |  | Error flag |
| `errorText` | string |  | Error text |
| `additionalErrors` | string |  | Additional errors |

[Response 403](../_shared/examples/GET__content_v2_object_parent_all_403.json)

- **429** Too Many Requests
