# TaskRabbit

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

TaskRabbit is a gig-economy marketplace connecting customers with local, vetted Taskers for furniture assembly, handyman work, moving, and other home services. Ingka Group (IKEA) acquired TaskRabbit in 2017 and has since deepened the integration, including in-store and checkout-time TaskRabbit assembly booking at IKEA. TaskRabbit's original developer story dates to February 2012, when it ran an open API that let third-party to-do apps (Astrid, Producteev) create tasks on a user's behalf; that early open, self-serve API is long gone. In November 2024 TaskRabbit acquired on-demand delivery company Dolly and rebranded its service as TaskRabbit Delivery. Today TaskRabbit operates one gated Partner API program (developer.taskrabbit.com) spanning two live surfaces - Delivery (built on Dolly's pre-existing Partner API, "PAPI") and a newer, 2025-12-versioned Home Services Partner Platform (Estimate, Availability, Bid, Book) that lets approved partners quote, book, and manage TaskRabbit projects, including IKEA-style furniture assembly, inside their own apps. Access requires partner approval (TaskRabbit reviews requests within about two business days) and Auth0 OAuth2 client-credentials (machine-to-machine) tokens; there is no public self-serve signup and no published API price list, since commercial terms are negotiated per partner. End-customer pricing on TaskRabbit itself follows a standard Service Fee plus Trust & Support Fee structure layered on top of each Tasker's hourly rate.

**Areas:** Gig Economy · Handyman · Home Services · Marketplace · Delivery · Moving · Partner API · IKEA

## TaskRabbit on APIs.io

Everything profiled for TaskRabbit is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/taskrabbit/](https://apis.io/providers/taskrabbit/)** — or go straight to one of the APIs or properties below.

### APIs (5)

- [TaskRabbit Delivery API](https://apis.io/apis/taskrabbit/taskrabbit-delivery-api/) — Dolly-based on-demand delivery, quoting, and routing.
- [TaskRabbit Home Services Availability API](https://apis.io/apis/taskrabbit/taskrabbit-home-services-availability-api/) — Real-time bookable time windows for Home Services projects.
- [TaskRabbit Home Services Booking API](https://apis.io/apis/taskrabbit/taskrabbit-home-services-booking-api/) — Bid, book, retrieve, cancel, and reschedule Home Services projects.
- [TaskRabbit Home Services Catalog API](https://apis.io/apis/taskrabbit/taskrabbit-home-services-catalog-api/) — Partner brand service catalog for Home Services.
- [TaskRabbit Home Services Estimate API](https://apis.io/apis/taskrabbit/taskrabbit-home-services-estimate-api/) — Pricing and eligibility estimation for Home Services projects.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [taskrabbit](https://apis.io/servers/taskrabbit/taskrabbit/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Taskrabbit Agentic Access](https://apis.io/agentic-access/taskrabbit/taskrabbit-agentic-access/)

#### Collections (5)

Postman and Open Collection request collections.

- [TaskRabbit Partner Delivery API](https://apis.io/collections/taskrabbit/open-taskrabbit-delivery-api/)
- [TaskRabbit Partner Delivery Home Services Availability API](https://apis.io/collections/taskrabbit/open-taskrabbit-home-services-availability-api/)
- [TaskRabbit Partner Delivery Home Services Booking API](https://apis.io/collections/taskrabbit/open-taskrabbit-home-services-booking-api/)
- [TaskRabbit Partner Delivery Home Services Catalog API](https://apis.io/collections/taskrabbit/open-taskrabbit-home-services-catalog-api/)
- [TaskRabbit Partner Delivery Home Services Estimate API](https://apis.io/collections/taskrabbit/open-taskrabbit-home-services-estimate-api/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Taskrabbit Authentication](https://apis.io/security/taskrabbit/taskrabbit-authentication/)
- [Taskrabbit Domain Security](https://apis.io/security/taskrabbit/taskrabbit-domain-security/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Taskrabbit Scopes](https://apis.io/scopes/taskrabbit/taskrabbit-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Taskrabbit Plans Pricing](https://apis.io/plans/taskrabbit/taskrabbit-plans-pricing/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.taskrabbit.com)
- [Documentation](https://developer.taskrabbit.com/)
- [Blog](https://www.taskrabbit.com/blog/)

## API Evangelist rating

**Kin Score 25.7** — emerging · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 68.3 |
| Contract quality | 47.3 |
| Contract governance | 0.0 |
| Operational transparency | 0.0 |
| Developer ergonomics | 26.2 |
| Access clarity | 7.9 |

**Agent readiness 33.3** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | documented (partial credit) |
| MCP Server | verified |
| Auth Clarity | negotiable (partial credit) |
| Idempotency | — |
| Error Semantics | — |
| OpenAPI Examples | partial |
| Rate Limit Signal | — |
| Event Surface Described | — |
| Agent Skills | — |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | — |
| Operation Distinctiveness | distinct |

**Regulatory alignment 21.6** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/taskrabbit/](https://apis.io/providers/taskrabbit/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for TaskRabbit: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/taskrabbit/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
