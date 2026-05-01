# `POST` /api/v3/passes

**Tag:** [FBS Passes](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Create Pass**

Описание метода

Creates a supplier pass.  The pass is valid for 48 hours from the time of creation.

  Maximum of 1 request per 10 minutes per one seller's account


## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `firstName` | string | ✓ | First name *Example: `Alex`* |
| `lastName` | string | ✓ | Last name *Example: `Petrov`* |
| `carModel` | string | ✓ | Car model *Example: `Lamborghini`* |
| `carNumber` | string | ✓ | Car number *Example: `A456BC123`* |
| `officeId` | integer | ✓ | Office ID *Example: `15`* |
## Responses

### `201` Created


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `id` | integer |  | Pass ID *Example: `2`* |

[Response 201](../_shared/examples/POST__api_v3_passes_201.json)

### `400` Bad request


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | string |  | Error code |
| `message` | string |  | Error description |
| `data` | object |  | Additional data for the error |

[Response 400: IncorrectRequestBody](../_shared/examples/POST__api_v3_passes_400_IncorrectRequestBody.json)

- **401** Unauthorized
- **402** Payment Required
- **403** Forbidden
- **404** Not Found
- **429** Too Many Requests
