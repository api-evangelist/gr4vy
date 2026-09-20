---
name: gr4vy-take-a-payment
description: Authorize, capture, and verify a payment through Gr4vy, with safe retries.
api: openapi/gr4vy-openapi.yml
operations:
- create_checkout_session
- create_transaction
- get_transaction
- capture_transaction
- list_transaction_events
generated: '2026-09-20'
method: generated
source: openapi/gr4vy-openapi.yml + conventions/gr4vy-conventions.yml
---

# gr4vy-take-a-payment

1. (Frontend card entry) `create_checkout_session` and hand the session id to Secure Fields / the mobile SDK.
2. `create_transaction` with `amount`, `currency`, `payment_method` and an `Idempotency-Key` header (UUIDv4, valid 24 hours). Use `intent: authorize` to capture later or `intent: capture` to do both.
3. Inspect `status`; when the buyer must approve (3DS/redirect) follow `payment_method.approval_url`, then `get_transaction`.
4. `capture_transaction` (full or partial) with its own `Idempotency-Key`. Optionally send `Prefer: resource=transaction-capture` to get the capture resource back.
5. `list_transaction_events` to audit what each connector did. Do not poll for final state: subscribe to webhooks instead.

## Rules

- Base URL is per instance: `https://api.sandbox.{id}.gr4vy.app` (sandbox) or `https://api.{id}.gr4vy.app` (production). Rehearse in sandbox; there is no dry-run flag.
- Auth: `Authorization: Bearer <JWT>` signed with your API key-pair (ES512/RS512) carrying the scopes the operations need. Send `x-gr4vy-merchant-account-id` when the instance has several merchant accounts.
- Errors are JSON `{type:"error", code, status, message, details[]}`; transaction failures carry `error_code` (see errors/gr4vy-decline-codes.yml). 409 on an idempotent retry means the original is still processing: back off and retry.
- Lists are cursor-paginated (`cursor`, `limit`; follow `next_cursor`).
