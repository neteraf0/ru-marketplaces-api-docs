# `GET` /content/v2/object/all

**Tag:** [Categories, Subjects, and Characteristics](index.md)

**Server:** `https://content-api.wildberries.ru`

**Subjects List**

Описание метода

Returns the list of all available subjects, subjects parent categories and their IDs


Request limit per one seller's account for all methods in the Content category:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 100 requests | 600 ms | 5 requests |

Exceptions are the methods:

    creating product cards
    creating product cards with merge
    editing product cards
    getting failed product cards with errors
    transfering product card to trash
    recovering product card from trash


## Parameters

| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| `locale` | query | string |  | Language for response of the `name` field:   - `ru` — Russian   - `en` — English   - `zh` — Chinese  Not used in the sandbox  *Example: `en`* |
| `name` | query | string |  | Search by item name (Socks), the search works by substring and can be conducted in any of the supported languages *Example: `Socks`* |
| `limit` | query | integer |  | Number of search results, maximum 1,000 *Example: `1000`* |
| `offset` | query | integer |  | How many results to skip. For example, with value `10`, the response will start with the 11 element *Example: `5000`* |
| `parentID` | query | integer |  | Subject parent category ID *Example: `1000`* |

## Responses

### `200` Success


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `data` | array |  | Categories and subjects |
| `error` | boolean |  | Error flag |
| `errorText` | string |  | Error text |
| `additionalErrors` | string |  | Additional errors |

[Response 200](../_shared/examples/GET__content_v2_object_all_200.json)

- **401** Unauthorized
- **429** Too Many Requests
