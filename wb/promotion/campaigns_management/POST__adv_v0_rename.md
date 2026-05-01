# `POST` /adv/v0/rename

**Tag:** [Campaigns Management](index.md)

**Server:** `https://advert-api.wildberries.ru`

**Rename Campaign**

Описание метода

The method allows to rename a campaign.


Request limit per one seller's account:


| Type | Period | Limit | Interval | Burst |
| --- | --- | --- | --- | --- |
| Personal | 1 s | 5 requests | 200 ms | 5 requests |
| Service | 1 s | 5 requests | 200 ms | 5 requests |
| Base | 1 h | 2 requests | 30 min | 1 request |


## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `advertId` | integer | ✓ | ID of the campaign where the name is changing |
| `name` | string | ✓ | New name (max 100 characters) |

[Request example](examples/POST__adv_v0_rename_req.json)

## Responses

- **200** Success
### `400` Bad request

`string`

[Response 400: InvalidRcIdAdv](../_shared/examples/POST__adv_v0_rename_400_InvalidRcIdAdv.json)


[Response 400: IncorrectName](../_shared/examples/POST__adv_v0_rename_400_IncorrectName.json)


[Response 400: IncorrectSupplierIdAdv](../_shared/examples/POST__adv_v0_rename_400_IncorrectSupplierIdAdv.json)

- **401** Unauthorized
### `422` Error processing request parameters

`string`

[Response 422: RequestBodyProcessErrorAdv](../_shared/examples/POST__adv_v2_supplier_nms_400.json)


[Response 422: CompanyNameChangeErr](../_shared/examples/POST__adv_v0_rename_422_CompanyNameChangeErr.json)

- **429** Too Many Requests
