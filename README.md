# dotloop (dotloop)

dotloop is a real estate transaction management platform (owned by Zillow Group) that lets agents, teams, and brokerages create and manage transactions - called "loops" - end to end, including documents, e-signatures, tasks, participants, and compliance workflows. The **dotloop Public API v2** is a documented, OAuth2-secured JSON REST API at `https://api-gateway.dotloop.com/public/v2` that exposes accounts, profiles, loops and loop details, folders, documents, participants, tasks, activities, contacts, loop templates, and webhook subscriptions, plus a Loop-It facade for one-call loop creation.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/dotloop/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/dotloop/refs/heads/main/apis.yml)

## Tags

- Real Estate
- Transaction Management
- Loops
- Documents
- E-Signature
- Zillow Group

## Timestamps

- **Created:** 2026-07-04
- **Modified:** 2026-07-04

## Authentication

The dotloop Public API v2 uses OAuth 2.0. Applications direct users to `https://auth.dotloop.com/oauth/authorize`, exchange the code at `https://auth.dotloop.com/oauth/token`, and call the API with a short-lived (typically 12-hour) Bearer access token. Access is currently restricted to `INDIVIDUAL` profiles.

## APIs

### dotloop Account API

Retrieve the authenticated dotloop account, including the individual's name, email, and default profile.

- **Base URL:** `https://api-gateway.dotloop.com/public/v2`
- **Documentation:** [https://dotloop.github.io/public-api/](https://dotloop.github.io/public-api/)

### dotloop Profiles API

List, retrieve, create, and update dotloop profiles - the individual, team, or brokerage contexts under which loops are organized.

### dotloop Loops API

List, retrieve, create, and update loops (transactions) within a profile, with pagination, filtering, and sorting.

### dotloop Loop Details API

Get and update the structured detail fields of a loop - sections such as Property Address, Financials, Contract Dates, Listing Information, and Offer details.

### dotloop Loop-It API

A facade endpoint that creates a new loop and populates it in a single call - transaction type and status, participant contact data, property and listing details, and optional form templates via NRDS or MLS Agent IDs.

### dotloop Folders API

List, retrieve, create, and update the folders inside a loop that organize its documents.

### dotloop Documents API

List and retrieve documents within a loop folder, and upload new documents via multipart form-data. Documents can be downloaded as PDFs.

### dotloop Participants API

List, retrieve, add, update, and remove the participants on a loop - agents, buyers, sellers, and other parties, each with a role and contact details.

### dotloop Tasks API

Read the task lists on a loop and the individual task items within each list - the checklist of steps, due dates, and completion status that drive a transaction's workflow and compliance.

### dotloop Activities API

List the read-only activity feed for a loop - a chronological audit trail of events and actions taken on the transaction.

### dotloop Contacts API

Full CRUD over the authenticated user's contacts (address book) - the people an agent works with and can add as loop participants.

### dotloop Loop Templates API

List and retrieve the reusable loop templates defined under a profile - transaction blueprints that predefine folders, documents, and settings.

### dotloop Webhooks API

Manage webhook subscriptions and inspect delivered events. Clients subscribe to loop or contact events; dotloop sends an HTTPS POST to the configured URL when events occur. Events are retained for 90 days.

## Common Properties

- [GitHub Organization](https://github.com/dotloop)
- [LinkedIn](https://www.linkedin.com/company/dotloop)
- [Website](https://www.dotloop.com)
- [Documentation](https://dotloop.github.io/public-api/)
- [Plans](plans/dotloop-plans-pricing.yml)
- [Rate Limits](rate-limits/dotloop-rate-limits.yml)
- [FinOps](finops/dotloop-finops.yml)

## Rate Limits

The API allows each client application up to **100 requests per minute per user**. Exceeding the limit returns HTTP 429. Responses include `X-RateLimit-Limit`, `X-RateLimit-Remaining`, and `X-RateLimit-Reset` headers.

## Pricing

dotloop is sold as a per-seat SaaS subscription (agent, team, and brokerage plans, billed monthly or annually). The Public API v2 is not separately metered - programmatic access is provisioned to approved partners and integrators on top of a dotloop subscription, with no published per-call fee. See [plans/dotloop-plans-pricing.yml](plans/dotloop-plans-pricing.yml).

## Maintainers

- **Kin Lane** — kin@apievangelist.com
