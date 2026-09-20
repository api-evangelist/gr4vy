---
name: gr4vy-vault-a-buyer-payment-method
description: Create a buyer and store a reusable payment method in the Gr4vy vault.
api: openapi/gr4vy-openapi.yml
operations:
- add_buyer
- add_buyer_shipping_details
- create_payment_method
- list_buyer_payment_methods
- get_payment_method
- delete_payment_method
generated: '2026-09-20'
method: generated
source: openapi/gr4vy-openapi.yml + conventions/gr4vy-conventions.yml
---

# gr4vy-vault-a-buyer-payment-method

1. `add_buyer` with `display_name` and your `external_identifier`.
2. Optionally `add_buyer_shipping_details`.
3. `create_payment_method` for the buyer (card data only from a PCI-scoped server; otherwise vault via Secure Fields + a transaction with `store: true`).
4. `list_buyer_payment_methods` by `buyer_id` or `buyer_external_identifier` to present stored methods at checkout.
5. `delete_payment_method` is permanent: there is no restore.

## Rules

- Base URL is per instance: `https://api.sandbox.{id}.gr4vy.app` (sandbox) or `https://api.{id}.gr4vy.app` (production). Rehearse in sandbox; there is no dry-run flag.
- Auth: `Authorization: Bearer <JWT>` signed with your API key-pair (ES512/RS512) carrying the scopes the operations need. Send `x-gr4vy-merchant-account-id` when the instance has several merchant accounts.
- Errors are JSON `{type:"error", code, status, message, details[]}`; transaction failures carry `error_code` (see errors/gr4vy-decline-codes.yml). 409 on an idempotent retry means the original is still processing: back off and retry.
- Lists are cursor-paginated (`cursor`, `limit`; follow `next_cursor`).
