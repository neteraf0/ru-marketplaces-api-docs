# In-Store Pickup Assembly Orders

[← In-Store Pickup Orders](../index.md)

## Endpoints

- [`GET` /api/v3/click-collect/orders/new](GET__api_v3_click_collect_orders_new.md) — Get New Assembly Orders List
- [`POST` /api/marketplace/v3/click-collect/orders/status/confirm](POST__api_marketplace_v3_click_collect_orders_status_confirm.md) — Transfer to Assembly
- [`POST` /api/marketplace/v3/click-collect/orders/status/prepare](POST__api_marketplace_v3_click_collect_orders_status_prepare.md) — Notify That the Assembly Orders Are Ready for Pickup
- [`PATCH` /api/v3/click-collect/orders/{orderId}/confirm](PATCH__api_v3_click_collect_orders__orderId__confirm.md) — Transfer to Assembly
- [`PATCH` /api/v3/click-collect/orders/{orderId}/prepare](PATCH__api_v3_click_collect_orders__orderId__prepare.md) — Notify That the Assembly Order Is Ready for Pickup
- [`POST` /api/v3/click-collect/orders/client](POST__api_v3_click_collect_orders_client.md) — Buyer Information
- [`POST` /api/v3/click-collect/orders/client/identity](POST__api_v3_click_collect_orders_client_identity.md) — Check If the Order Belongs to the Buyer
- [`POST` /api/marketplace/v3/click-collect/orders/status/receive](POST__api_marketplace_v3_click_collect_orders_status_receive.md) — Notify That the Orders Were Received by the Buyers
- [`POST` /api/marketplace/v3/click-collect/orders/status/reject](POST__api_marketplace_v3_click_collect_orders_status_reject.md) — Notify that the Orders Are Declined
- [`PATCH` /api/v3/click-collect/orders/{orderId}/receive](PATCH__api_v3_click_collect_orders__orderId__receive.md) — Notify That the Order Has Been Accepted by the Buyer
- [`PATCH` /api/v3/click-collect/orders/{orderId}/reject](PATCH__api_v3_click_collect_orders__orderId__reject.md) — Notify That the Buyer Refused the Order
- [`POST` /api/marketplace/v3/click-collect/orders/status/info](POST__api_marketplace_v3_click_collect_orders_status_info.md) — Get Assembly Order Statuses
- [`POST` /api/v3/click-collect/orders/status](POST__api_v3_click_collect_orders_status.md) — Get Assembly Order Statuses
- [`GET` /api/v3/click-collect/orders](GET__api_v3_click_collect_orders.md) — Retrieve Information on Completed Assembly Orders
- [`POST` /api/marketplace/v3/click-collect/orders/status/cancel](POST__api_marketplace_v3_click_collect_orders_status_cancel.md) — Cancel the Assembly Orders
- [`PATCH` /api/v3/click-collect/orders/{orderId}/cancel](PATCH__api_v3_click_collect_orders__orderId__cancel.md) — Cancel the Assembly Order
