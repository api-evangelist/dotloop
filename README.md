# dotloop (dotloop)

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
