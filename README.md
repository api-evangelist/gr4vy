# Gr4vy

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Gr4vy is a cloud-native payment orchestration platform delivered as dedicated, per-merchant infrastructure. A single REST API and a PCI DSS Level 1 vault connect merchants and platforms to hundreds of payment services, payment methods, anti-fraud providers, digital wallets and gift-card services, with no-code Flow routing rules, network tokens, 3-D Secure, payouts, payment links, reporting and webhooks. Gr4vy publishes an OpenAPI 3.1 contract, Speakeasy-generated server SDKs in six languages, mobile and web checkout components (Embed, Secure Fields), a native CLI, a Postman collection, a docs MCP server, an A2A agent card and an Agent Skill.

**Areas:** Payments · Payment Orchestration · Fintech · Checkout · Tokenization · Vault · Fraud Prevention · 3D Secure · Webhook · Commerce · A2A

## Gr4vy on APIs.io

Everything profiled for Gr4vy is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/gr4vy/](https://apis.io/providers/gr4vy/)** — or go straight to one of the APIs or properties below.

### APIs (62)

- [Gr4vy Docs MCP Server](https://apis.io/apis/gr4vy/gr4vy-docs-mcp/) — Hosted, unauthenticated Model Context Protocol server over the Gr4vy documentation: search, read-only docs filesystem queries and a docs-feedback tool. It…
- [Gr4vy 3DS scenarios API](https://apis.io/apis/gr4vy/gr4vy-3ds-scenarios-api/) — Manage and create 3DS scenarios in sandbox.
- [Gr4vy Account Updater API](https://apis.io/apis/gr4vy/gr4vy-account-updater-api/) — An Account Updater is a service provided by credit card issuers (such as banks and financial institutions) to merchants who accept recurring payments from…
- [Gr4vy Anti Fraud Service Definitions API](https://apis.io/apis/gr4vy/gr4vy-anti-fraud-service-definitions-api/) — Anti fraud service definitions describe the fields required for a anti fraud service to be configured.
- [Gr4vy Anti-Fraud Services API](https://apis.io/apis/gr4vy/gr4vy-anti-fraud-services-api/) — In Gr4vy, an anti-fraud service represents a configured anti-fraud service provider (`Sift`, `CyberSource`, etc). This third-party services will be used to…
- [Gr4vy API Key Pairs API](https://apis.io/apis/gr4vy/gr4vy-api-key-pairs-api/) — In Gr4vy, an API key pair is used to sign and validate JSON Web Tokens (JWT). JWTs are used as a HTTP `bearer` token to authenticate to the API. For more…
- [Gr4vy API Logs API](https://apis.io/apis/gr4vy/gr4vy-api-logs-api/) — API Logs provide an historic of 4XX and 5XX errors that happened in the API in the last 24 hours with a 250 result limit.
- [Gr4vy Apple Pay Certificates API](https://apis.io/apis/gr4vy/gr4vy-apple-pay-certificates-api/) — Apple Pay payment processing certificates are used by Apple to encrypt Apple Pay tokens. You must register and upload an Apple Pay payment processing…
- [Gr4vy Audit Logs API](https://apis.io/apis/gr4vy/gr4vy-audit-logs-api/) — Audit Logs provide an historic record of changes made to your Gr4vy instance.
- [Gr4vy Buyers API](https://apis.io/apis/gr4vy/gr4vy-buyers-api/) — In Gr4vy, a buyer represents your customer, the shopper who's performing a checkout and making a purchase. A buyer can be used by you to: * Display a human…
- [Gr4vy Buyers - Gift cards API](https://apis.io/apis/gr4vy/gr4vy-buyers-gift-cards-api/) — Query gift cards for buyers.
- [Gr4vy Buyers - Payment methods API](https://apis.io/apis/gr4vy/gr4vy-buyers-payment-methods-api/) — Query payment methods for buyers.
- [Gr4vy Buyers - Shipping details API](https://apis.io/apis/gr4vy/gr4vy-buyers-shipping-details-api/) — Manage shipping details for buyers.
- [Gr4vy Card Details API](https://apis.io/apis/gr4vy/gr4vy-card-details-api/) — Endpoints to retrieve details of a card by utilising a BIN lookup table.
- [Gr4vy Card Scheme Definitions API](https://apis.io/apis/gr4vy/gr4vy-card-scheme-definitions-api/) — Card Scheme definitions provide display information to a card scheme.
- [Gr4vy Checkout Sessions API](https://apis.io/apis/gr4vy/gr4vy-checkout-sessions-api/) — A Checkout Session represents the session of a user as they progress through an online checkout.
- [Gr4vy Connection Definitions API](https://apis.io/apis/gr4vy/gr4vy-connection-definitions-api/) — Endpoints to retrieve details of various connections such as payment services, digital wallets, and anti-fraud services.
- [Gr4vy Connections API](https://apis.io/apis/gr4vy/gr4vy-connections-api/) — Endpoints to retrieve details of configured connections such as payment services, digital wallets, and anti-fraud services.
- [Gr4vy Digital Wallets API](https://apis.io/apis/gr4vy/gr4vy-digital-wallets-api/) — In Gr4vy, a digital wallet represents a way for a buyer to pay using card details already stored on their device via a digital wallet service such as Apple…
- [Gr4vy Digital wallets - Sessions API](https://apis.io/apis/gr4vy/gr4vy-digital-wallets-sessions-api/) — Create sessions for digital wallets like Apple Pay and Google Pay.
- [Gr4vy Digital wallets - Setup API](https://apis.io/apis/gr4vy/gr4vy-digital-wallets-setup-api/) — Manage digital wallets like Apple Pay and Google Pay.
- [Gr4vy Flow API](https://apis.io/apis/gr4vy/gr4vy-flow-api/) — In Gr4vy, a rule can be created that triggers actions anywhere in the payment flow.
- [Gr4vy Gift Card Service Definitions API](https://apis.io/apis/gr4vy/gr4vy-gift-card-service-definitions-api/) — Gift card service definitions describe the fields required for a gift card service to be configured.
- [Gr4vy Gift Card Services API](https://apis.io/apis/gr4vy/gr4vy-gift-card-services-api/) — In Gr4vy, a gift card service represents a configured provider for processing gift cards.
- [Gr4vy Gift Cards API](https://apis.io/apis/gr4vy/gr4vy-gift-cards-api/) — In Gr4vy, a gift card represents a stored value card that can be used to pay for a transaction.
- [Gr4vy Health Dashboard API](https://apis.io/apis/gr4vy/gr4vy-health-dashboard-api/) — Endpoints to retrieve the data used for the Health Dashboard.
- [Gr4vy Insights API](https://apis.io/apis/gr4vy/gr4vy-insights-api/) — Retrieve Insights data.
- [Gr4vy Insights - Presets API](https://apis.io/apis/gr4vy/gr4vy-insights-presets-api/) — Manage presets for Insights.
- [Gr4vy Merchant accounts - 3DS configuration API](https://apis.io/apis/gr4vy/gr4vy-merchant-accounts-3ds-configuration-api/) — Manage 3DS profiles for merchant accounts.
- [Gr4vy Merchant Accounts API](https://apis.io/apis/gr4vy/gr4vy-merchant-accounts-api/) — In Gr4vy, a merchant account represents an individual merchant in an instance. Each instance has one or more merchant accounts, and each merchant account…
- [Gr4vy Metrics Explorer API](https://apis.io/apis/gr4vy/gr4vy-metrics-explorer-api/) — Endpoints to retrieve the data used for the Metrics Explorer.
- [Gr4vy Monitoring API](https://apis.io/apis/gr4vy/gr4vy-monitoring-api/) — Manage monitoring and alerting.
- [Gr4vy Payment Links API](https://apis.io/apis/gr4vy/gr4vy-payment-links-api/) — In Gr4vy, payment links allow a merchant to generate a link, send it to a customer via email, SMS, etc, and then have the customer pay without the need for…
- [Gr4vy Payment Method Definitions API](https://apis.io/apis/gr4vy/gr4vy-payment-method-definitions-api/) — Payment Method definitions provide display information to a payment method.
- [Gr4vy Payment Methods API](https://apis.io/apis/gr4vy/gr4vy-payment-methods-api/) — In Gr4vy, a payment method represents a way in which a payment can be processed, for example a card, a PayPal account, or a bank account. The payment method…
- [Gr4vy Payment methods - Definitions API](https://apis.io/apis/gr4vy/gr4vy-payment-methods-definitions-api/) — Manage payment method definitions.
- [Gr4vy Payment methods - Network tokens API](https://apis.io/apis/gr4vy/gr4vy-payment-methods-network-tokens-api/) — Manage network tokens for stored payment methods.
- [Gr4vy Payment methods - Payment service tokens API](https://apis.io/apis/gr4vy/gr4vy-payment-methods-payment-service-tokens-api/) — Manage payment service tokens for stored payment methods.
- [Gr4vy Payment Options API](https://apis.io/apis/gr4vy/gr4vy-payment-options-api/) — In Gr4vy, a payment option represents a list of methods (card, PayPal, etc) that are available for a given locale. The payment options API can be used to: *…
- [Gr4vy Payment Service Definitions API](https://apis.io/apis/gr4vy/gr4vy-payment-service-definitions-api/) — Payment service definitions describe the fields required for a payment service to be configured.
- [Gr4vy Payment Services API](https://apis.io/apis/gr4vy/gr4vy-payment-services-api/) — In Gr4vy, a payment service represents a configured payment provider (Stripe, PayPal, Adyen, etc) for a specific payment type (card, bitcoin, etc) The…
- [Gr4vy Payouts API](https://apis.io/apis/gr4vy/gr4vy-payouts-api/) — Payouts allow a merchant to send money from one of their own accounts to a third party.
- [Gr4vy Refunds API](https://apis.io/apis/gr4vy/gr4vy-refunds-api/) — Manage transaction refunds.
- [Gr4vy Reports API](https://apis.io/apis/gr4vy/gr4vy-reports-api/) — In Gr4vy, a report represents the configuration details to extract or dump a set of data into a downloadable CSV file. The data extracted by a report is…
- [Gr4vy Reports - Executions API](https://apis.io/apis/gr4vy/gr4vy-reports-executions-api/) — Manage executions of reports.
- [Gr4vy Roles API](https://apis.io/apis/gr4vy/gr4vy-roles-api/) — In Gr4vy, users can be granted access to specific types of resources and permissions to perform certain actions by being assigned one or more roles.
- [Gr4vy Sessions API](https://apis.io/apis/gr4vy/gr4vy-sessions-api/) — The sessions APIs are used to facilitate user authentication for the Gr4vy dashboard.
- [Gr4vy Tokens API](https://apis.io/apis/gr4vy/gr4vy-tokens-api/) — Endpoints related to the Gr4vy tokenization service.
- [Gr4vy Transactions - Actions API](https://apis.io/apis/gr4vy/gr4vy-transactions-actions-api/) — Read Flow actions triggered for a transaction.
- [Gr4vy Transactions API](https://apis.io/apis/gr4vy/gr4vy-transactions-api/) — In Gr4vy, a transaction represents a payment in any state, either before it is authorized, once it is captured, or after it has been refunded. The…
- [Gr4vy Transactions - Captures API](https://apis.io/apis/gr4vy/gr4vy-transactions-captures-api/) — Read transaction capture data.
- [Gr4vy Transactions - Chargeback reversals API](https://apis.io/apis/gr4vy/gr4vy-transactions-chargeback-reversals-api/) — Read transaction chargeback reversal data.
- [Gr4vy Transactions - Chargebacks API](https://apis.io/apis/gr4vy/gr4vy-transactions-chargebacks-api/) — Read transaction chargeback data.
- [Gr4vy Transactions - Refund settlements API](https://apis.io/apis/gr4vy/gr4vy-transactions-refund-settlements-api/) — Read transaction refund settlement data.
- [Gr4vy Transactions - Sessions API](https://apis.io/apis/gr4vy/gr4vy-transactions-sessions-api/) — Manage transaction session data.
- [Gr4vy Transactions - Settlements API](https://apis.io/apis/gr4vy/gr4vy-transactions-settlements-api/) — Read transaction settlement data.
- [Gr4vy Users API](https://apis.io/apis/gr4vy/gr4vy-users-api/) — In Gr4vy, a user represents an employee of the merchant with access to the dashboard.
- [Gr4vy Vault Forward API](https://apis.io/apis/gr4vy/gr4vy-vault-forward-api/) — Vault Forwarding is a way to perform requests where, provided a template, Gr4vy will evaluate it to inject PCI data and forward it to third party services…
- [Gr4vy Vault Forward Configurations API](https://apis.io/apis/gr4vy/gr4vy-vault-forward-configurations-api/) — A Vault Forward Configuration represents a third party service that is currently enabled to send requests containing PCI data.
- [Gr4vy Vault Forward Definitions API](https://apis.io/apis/gr4vy/gr4vy-vault-forward-definitions-api/) — Vault Forward definitions describe a third party service that has been vetted to receive requests containing PCI data.
- [Gr4vy Webhook subscriptions API](https://apis.io/apis/gr4vy/gr4vy-webhook-subscriptions-api/) — Endpoints related to the management of subscriptions for endpoints to receive webhooks.
- [Gr4vy Webhooks API](https://apis.io/apis/gr4vy/gr4vy-webhooks-api/) — Endpoints related to webhooks to integrate Gr4vy with payment services webhooks functionality.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Gr4Vy Webhooks](https://apis.io/asyncapis/gr4vy/gr4vy-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [Gr4vy](https://apis.io/servers/gr4vy/gr4vy/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Gr4Vy Agentic Access](https://apis.io/agentic-access/gr4vy/gr4vy-agentic-access/)

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Gr4Vy Openapi Overlay](https://apis.io/overlays/gr4vy/gr4vy-openapi-overlay/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Gr4Vy Authentication](https://apis.io/security/gr4vy/gr4vy-authentication/)
- [Gr4Vy Domain Security](https://apis.io/security/gr4vy/gr4vy-domain-security/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Gr4Vy Scopes](https://apis.io/scopes/gr4vy/gr4vy-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Gr4Vy Plans Pricing](https://apis.io/plans/gr4vy/gr4vy-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Gr4Vy Rate Limits](https://apis.io/rate-limits/gr4vy/gr4vy-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://gr4vy.com/)
- [Documentation](https://docs.gr4vy.com/guides/get-started)
- [Getting started](https://docs.gr4vy.com/guides/get-started)
- [API reference](https://docs.gr4vy.com/reference)
- [Support](https://gr4vy.com/contact/)
- [Changelog](https://docs.gr4vy.com/updates)
- [Blog](https://gr4vy.com/blog/)
- [Compliance](https://gr4vy.com/regulation-and-compliance/)
- [Terms of service](https://gr4vy.com/terms-of-service/)
- [Privacy policy](https://gr4vy.com/privacy-policy/)
- [GitHub](https://github.com/gr4vy)
- [Status](https://status.gr4vy.com/)

## API Evangelist rating

**Kin Score 62.4** — strong · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 80.0 |
| Contract quality | 60.6 |
| Contract governance | 18.2 |
| Operational transparency | 73.7 |
| Developer ergonomics | 90.5 |
| Access clarity | 28.9 |

**Agent readiness 53.2** — agent-native

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | documented (partial credit) |
| MCP Server | documented (partial credit) |
| Auth Clarity | bearer (partial credit) |
| Idempotency | verified |
| Error Semantics | verified |
| OpenAPI Examples | partial |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | yes |
| Agent Skills | yes |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | conformant |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | partial |
| Operation Distinctiveness | mostly (partial credit) |

**Regulatory alignment 48.2** — Payments

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/gr4vy/](https://apis.io/providers/gr4vy/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Gr4vy: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/gr4vy/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
