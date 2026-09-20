---
name: gr4vy
description: Use when building payment integrations, processing transactions, managing payment methods, configuring payment processors, implementing webhooks, or handling payment orchestration across multiple payment service providers.
metadata:
    mintlify-proj: gr4vy
    version: "1.0"
---

# Gr4vy Skill

## Product summary

Gr4vy is a payment orchestration platform that connects multiple payment processors, routes transactions intelligently, and manages your entire payments stack from one place. Use Gr4vy to accept payments via web, mobile, or API; store and manage payment methods; process refunds and captures; and receive real-time event notifications. Key resources: REST API at `https://api.{gr4vyId}.gr4vy.app`, SDKs for server-side (C#, Go, Java, PHP, Python, TypeScript) and client-side (Embed, Secure Fields, React Native, iOS, Android), CLI for command-line operations, and dashboard at `https://dashboard.gr4vy.com`. Primary docs: https://docs.gr4vy.com

## When to use

Reach for this skill when:
- Building a payment checkout experience (web, mobile, or custom)
- Creating transactions and processing payments through multiple payment providers
- Storing, vaulting, or managing payment methods for customers
- Implementing 3-D Secure authentication
- Setting up webhooks to receive transaction status updates
- Configuring payment service providers (Stripe, Adyen, PayPal, etc.)
- Handling refunds, captures, voids, or other transaction operations
- Implementing recurring payments or subscriptions
- Forwarding vaulted card data to third-party endpoints
- Querying transaction history or payment method details
- Managing buyers and their associated payment methods

## Quick reference

### Authentication
- Create API key in dashboard **Integrations** > **Add API key**
- Generate JWT bearer token server-side using private key
- All API requests require `Authorization: Bearer {jwtToken}` header
- Use SDKs to handle token generation automatically

### Integration paths
| Path | Use case | Client-side | Server-side |
|------|----------|-------------|-------------|
| **Embed** | Drop-in hosted checkout UI | Embed SDK | JWT token generation |
| **Secure Fields** | Custom checkout with PCI-compliant card fields | Secure Fields SDK | Checkout session creation |
| **Direct API** | Full custom control, wallet/APM integration | None (custom UI) | Transaction API calls |
| **Mobile** | Native iOS/Android experiences | iOS/Android SDK | JWT token generation |
| **E-commerce plugins** | commercetools, Magento, SFCC | Plugin handles it | Plugin handles it |

### Core API endpoints
| Resource | Key operations |
|----------|-----------------|
| **Transactions** | Create, get, list, capture, void, refund, sync |
| **Payment Methods** | Create, get, list, update, delete (stored cards) |
| **Checkout Sessions** | Create, get, update, delete (for Secure Fields) |
| **Buyers** | Create, get, list, update, delete (customer records) |
| **Payment Services** | List, create, update, delete (PSP configurations) |
| **Webhooks** | Subscribe, list, verify signatures |

### CLI commands
```bash
# Generate tokens
gr4vy token --scope transactions.read --scope transactions.write
gr4vy embed 1299 USD buyer_external_identifier=user-123

# API calls
gr4vy transactions list --limit 20 --status capture_pending
gr4vy transactions get <transaction-id>
gr4vy transactions refunds create <transaction-id> --data '{"amount":500}'
gr4vy buyers create --data '{"display_name":"Jane Doe"}'
```

### Transaction statuses
- `processing` — Being processed with payment services
- `buyer_approval_pending` — Awaiting buyer authentication (3DS, redirect)
- `authorization_succeeded` — Authorized but not captured
- `authorization_failed` / `authorization_declined` — Auth failed
- `capture_pending` — Submitted for capture
- `capture_succeeded` — Authorized and captured
- `authorization_voided` — Authorization canceled before capture

### Payment method statuses
- `processing` — Created, ready to use
- `succeeded` — Successfully validated
- `failed` — Could not be processed
- `buyer_approval_required` — Needs buyer action (e.g., PayPal redirect)

## Decision guidance

### When to use Embed vs Secure Fields vs Direct API

| Scenario | Embed | Secure Fields | Direct API |
|----------|-------|---------------|-----------|
| Want drop-in UI with payment method selector | ✓ | ✗ | ✗ |
| Need custom checkout design | ✗ | ✓ | ✓ |
| Integrating wallet or APM directly | ✗ | ✗ | ✓ |
| Minimal PCI scope required | ✓ | ✓ | ✗ |
| Building for web | ✓ | ✓ | ✓ |
| Building for mobile | ✗ | ✗ | ✓ (use native SDK) |
| Want hosted 3DS flow | ✓ | ✗ | ✓ |

### When to use checkout sessions

Use checkout sessions when:
- Building with Secure Fields (required)
- Collecting CVV for stored cards
- Forwarding vaulted data via Vault Forward
- Storing cart items, metadata, or airline data upfront
- Implementing 3DS forwarding

### When to use webhooks vs polling

| Approach | When to use |
|----------|------------|
| **Webhooks** | Default choice; real-time updates; reliable for transaction status |
| **Polling** | Webhook endpoint unavailable; testing; fallback for timeout scenarios |

## Workflow

### 1. Set up authentication
1. Go to dashboard **Integrations** > **Add API key**
2. Download the private key (`.pem` file)
3. Store securely (environment variable or vault)
4. Use SDK or CLI to generate JWT tokens server-side
5. Never expose private key to client-side code

### 2. Create a transaction (Embed path)
1. Create API key and generate JWT token server-side
2. Initialize Embed SDK on client with token
3. Embed renders payment method selector
4. User selects payment method and enters details
5. Embed submits transaction to API
6. Listen for webhook `transaction.captured` or `transaction.declined`
7. Verify transaction status via API if needed

### 3. Create a transaction (Direct API path)
1. Generate JWT token server-side
2. Call `GET /payment-options` to list available methods
3. Call `POST /transactions` with payment method details
4. If `buyer_approval_pending`, redirect user to `approval_url`
5. Poll or listen for webhook to determine final status
6. Capture or void as needed

### 4. Store a payment method
1. Create checkout session: `POST /checkout/sessions`
2. Use Secure Fields with checkout session ID
3. User enters card details
4. Set `store: true` on transaction or call `POST /payment-methods` directly
5. Returned payment method ID can be reused for future transactions

### 5. Process a refund
1. Get transaction ID
2. Call `POST /transactions/{id}/refunds` with amount
3. Listen for webhook `refund.succeeded` or `refund.failed`
4. Verify status via `GET /transactions/{id}/refunds`

### 6. Set up webhooks
1. Go to dashboard **Settings** > **Manage Integrations** > **Webhook subscriptions**
2. Add webhook URL (HTTPS required)
3. Configure authentication (basic or OAuth)
4. Select events to listen for
5. Verify webhook signatures using provided secret
6. Acknowledge receipt with HTTP 200-299 within 5 seconds
7. Implement retry logic for failed deliveries

## Common gotchas

- **Never expose private key to client** — Always generate JWT tokens server-side. Client-side code should only receive short-lived tokens.
- **Webhooks are the reliable way to track status** — Don't rely solely on browser events (Embed's `transactionCreated`, `onComplete`). Browsers are unreliable; webhooks are the source of truth.
- **Set unique reference IDs** — Use `externalIdentifier` or `metadata` to link transactions to orders. Use `onBeforeTransaction` callback in Embed to set this just-in-time.
- **Idempotency is built-in for Embed** — If using Direct API, include `Idempotency-Key` header to safely retry failed requests.
- **Checkout sessions expire** — Default expiry is 1 hour. Create them close to when needed.
- **3DS is required for many cards** — Transactions may move to `buyer_approval_pending` status. Always handle redirects or hosted flows.
- **Amounts are in smallest currency unit** — 1299 = $12.99 USD. Verify calculations before submitting.
- **Payment method status ≠ transaction status** — A payment method can be `processing` while a transaction using it is `capture_succeeded`.
- **Capture is separate from authorization** — Some payment methods authorize first, then require explicit capture. Check payment service documentation.
- **Refunds have time limits** — Some payment services don't allow refunds after a certain period. Check error codes.
- **Vault Forward requires endpoint registration** — You must whitelist endpoints in the dashboard before forwarding PCI data to them in production.

## Verification checklist

Before submitting work:

- [ ] API key created and private key stored securely
- [ ] JWT token generation tested server-side
- [ ] Payment service provider(s) configured in dashboard
- [ ] Webhook subscription created and endpoint verified
- [ ] Webhook signatures validated in code
- [ ] Transaction includes `externalIdentifier` or `metadata` linking to order
- [ ] Idempotency key used for Direct API calls (or Embed handles it)
- [ ] 3DS flow tested (redirect or hosted)
- [ ] Refund, void, and capture operations tested
- [ ] Error handling implemented for all API calls
- [ ] Amounts verified in smallest currency unit
- [ ] Buyer information included where applicable
- [ ] Cart items included for BNPL methods
- [ ] Tested in sandbox before production
- [ ] Webhook retry logic implemented
- [ ] Payment method storage tested if needed
- [ ] Mobile SDK tested on target platforms (if applicable)

## Resources

- **Full page navigation**: https://docs.gr4vy.com/llms.txt
- **API Reference**: https://docs.gr4vy.com/reference
- **Authentication guide**: https://docs.gr4vy.com/guides/api/authentication
- **Embed quick start**: https://docs.gr4vy.com/guides/payments/embed/quick-start/overview
- **Direct API quick start**: https://docs.gr4vy.com/guides/payments/direct-api/quick-start/overview
- **Webhooks guide**: https://docs.gr4vy.com/guides/features/webhooks/overview
- **Best practices**: https://docs.gr4vy.com/guides/best-practices/overview
- **CLI documentation**: https://docs.gr4vy.com/guides/tools/cli

---

> For additional documentation and navigation, see: https://docs.gr4vy.com/llms.txt