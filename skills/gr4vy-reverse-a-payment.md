---
name: gr4vy-reverse-a-payment
description: 'Choose and perform the right reversal for a Gr4vy transaction: cancel,
  void, or refund.'
api: openapi/gr4vy-openapi.yml
operations:
- get_transaction
- cancel_transaction
- void_transaction
- create_transaction_refund
- create_full_transaction_refund
- list_transaction_refunds
generated: '2026-09-20'
method: generated
source: openapi/gr4vy-openapi.yml + conventions/gr4vy-conventions.yml
---

# gr4vy-reverse-a-payment

1. `get_transaction` and read `status`.
2. Still pending (buyer approval outstanding): `cancel_transaction`.
3. Authorized, not captured: `void_transaction` with an `Idempotency-Key`.
4. Captured: `create_transaction_refund` (partial `amount` allowed) or `create_full_transaction_refund` for every instrument (card + gift cards), each with an `Idempotency-Key`.
5. `list_transaction_refunds` to confirm; refunds settle asynchronously (`refund.succeeded` / `refund.failed` webhooks).

Gr4vy documents no fixed refund window: the downstream payment service decides, and an expired window surfaces as error code `refund_period_expired`.

## Rules

- Base URL is per instance: `https://api.sandbox.{id}.gr4vy.app` (sandbox) or `https://api.{id}.gr4vy.app` (production). Rehearse in sandbox; there is no dry-run flag.
- Auth: `Authorization: Bearer <JWT>` signed with your API key-pair (ES512/RS512) carrying the scopes the operations need. Send `x-gr4vy-merchant-account-id` when the instance has several merchant accounts.
- Errors are JSON `{type:"error", code, status, message, details[]}`; transaction failures carry `error_code` (see errors/gr4vy-decline-codes.yml). 409 on an idempotent retry means the original is still processing: back off and retry.
- Lists are cursor-paginated (`cursor`, `limit`; follow `next_cursor`).
