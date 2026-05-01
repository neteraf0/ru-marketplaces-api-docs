# `POST` /v1/cluster/list

**Tag:** [FboSupplyRequest](index.md)

**operationId:** `SupplyDraftAPI_DraftClusterList`

**Информация о кластерах и их складах**

## Request Body

Content-Type: `application/json`


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `cluster_ids` | array |  | Идентификаторы кластеров. |
| `cluster_type` | v1ClusterType | ✓ | Тип кластера: - `CLUSTER_TYPE_OZON` — кластер в России, - `CLUSTER_TYPE_CIS` — кластер в СНГ.  |

[Request example](examples/POST__v1_cluster_list_req.json)

## Responses

### `200` Информация о кластерах


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `clusters` | array |  | Кластеры. |

[Response 200](../_shared/examples/POST__v1_cluster_list_200.json)

### `default` Ошибка


| Field | Type | Req | Description |
|-------|------|-----|-------------|
| `code` | integer |  | Код ошибки. |
| `details` | array |  | Дополнительная информация об ошибке. |
| `message` | string |  | Описание ошибки. |

[Response default](../_shared/examples/POST__v1_roles_default.json)
