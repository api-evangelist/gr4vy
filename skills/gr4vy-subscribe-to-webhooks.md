---
name: gr4vy-subscribe-to-webhooks
description: Create, verify and rotate a Gr4vy webhook subscription.
api: openapi/gr4vy-openapi.yml
operations:
- create_webhook_subscription
- list_webhook_subscription
- read_webhook_subscription
- update_webhook_subscription
- rotate_webhook_subscription_secret
- delete_webhook_subscription
generated: '2026-09-20'
method: generated
source: openapi/gr4vy-openapi.yml + conventions/gr4vy-conventions.yml
---

# gr4vy-subscribe-to-webhooks

1. `create_webhook_subscription` with your HTTPS endpoint URL.
2. Generate a secret (`rotate_webhook_subscription_secret`) and store it.
3. On each delivery verify `X-Gr4vy-Webhook-Signatures`: HMAC SHA256 of `{X-Gr4vy-Webhook-Timestamp}.{raw body}`; accept if any listed signature matches, and reject old timestamps.
4. Reply 2xx within 5000 ms; unacknowledged events retry with exponential delay for up to 7 days and are not ordered.
5. Event types are catalogued in asyncapi/gr4vy-webhooks.yml.

## Rules

- Base URL is per instance: `https://api.sandbox.{id}.gr4vy.app` (sandbox) or `https://api.{id}.gr4vy.app` (production). Rehearse in sandbox; there is no dry-run flag.
- Auth: `Authorization: Bearer <JWT>` signed with your API key-pair (ES512/RS512) carrying the scopes the operations need. Send `x-gr4vy-merchant-account-id` when the instance has several merchant accounts.
- Errors are JSON `{type:"error", code, status, message, details[]}`; transaction failures carry `error_code` (see errors/gr4vy-decline-codes.yml). 409 on an idempotent retry means the original is still processing: back off and retry.
- Lists are cursor-paginated (`cursor`, `limit`; follow `next_cursor`).
