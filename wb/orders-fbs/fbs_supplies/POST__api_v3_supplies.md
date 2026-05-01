# `POST` /api/v3/supplies

**Tag:** [FBS Supplies](index.md)

**Server:** `https://marketplace-api.wildberries.ru`

**Create a New Supply**

Описание метода

**Supplies limitations**:

- Supplies applicable only for assembly orders in the FBS (Fulfillment by Seller) delivery.
- All assembly orders added to supply automatically transferred from the `new` status to the `confirm` status.
- Please note that if you will `cancel` (`Canceled by the seller`) the order, we will automatically remove it from the supply.
- A supply can only be assembled from assembly jobs (orders) with the same dimensional type (cargoType). A new supply does not have a dimensional attribute. When the first assembly order is added to a supply, the supply acquires the dimensional attribute of that assembly order.


Request limit per one seller's account for FBS assembly orders, supplies and passes methods:

| Period | Limit | Interval | Burst |
| --- | --- | --- | --- |
| 1 min | 300 requests | 200 ms | 20 requests |

One request with a response code of 409 is counted as 10 requests


## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `name` | string |  | Supply name *Example: `Some test supply`* |
## Responses

### `201` Created


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `id` | string |  | Supply ID *Example: `WB-GI-1234567`* |

[Response 201](../_shared/examples/POST__api_v3_supplies_201.json)

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
- **429** Too Many Requests
