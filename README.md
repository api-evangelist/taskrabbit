# TaskRabbit (taskrabbit)

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

TaskRabbit is a gig-economy marketplace connecting customers with local, vetted Taskers for furniture assembly, handyman work, moving, and other home services. Ingka Group (IKEA) acquired TaskRabbit outright in September 2017 and has since deepened the integration, including in-store and checkout-time TaskRabbit assembly booking at IKEA.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/taskrabbit/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/taskrabbit/refs/heads/main/apis.yml)

## API Status

TaskRabbit's developer story is not a single, continuous line - it has an open past and a gated present:

- **2012 - open developer API (defunct).** In February 2012 TaskRabbit launched a self-serve, publicly documented API that let third-party to-do-list apps (Astrid, Producteev) and other integrators create TaskRabbit tasks on a consumer's behalf. That original open API no longer exists; there is no public self-serve developer signup on taskrabbit.com today.
- **2017 - IKEA acquisition.** Ingka Group (IKEA) acquired TaskRabbit, and the company's developer priorities shifted toward retail/marketplace integration partners rather than hobbyist consumer apps.
- **2024 - Dolly acquisition.** TaskRabbit acquired on-demand delivery company Dolly in November 2024 and rebranded its service as TaskRabbit Delivery. Dolly's existing Partner API (PAPI) continues to power that surface.
- **Today - one gated Partner API program.** developer.taskrabbit.com hosts a single Developer Hub covering two live REST surfaces: **Delivery** (Dolly-derived, mature) and **Home Services** (a newer, 2025-12-versioned Partner Platform covering Estimate, Availability, Bid, Book). The top-level overview page still tags Home Services "(coming soon!)," but individual endpoint pages describe it as available in both Sandbox and Production - that top-level copy looks stale relative to the endpoint docs. Access to either surface requires partner approval (TaskRabbit says it typically reviews requests within about two business days) and Auth0 OAuth2 client-credentials (machine-to-machine) tokens. There is no public self-serve signup and no published API price list; commercial terms are negotiated per partner.

See [review.yml](review.yml) for the full sourced findings, including confirmed endpoint paths and why no AsyncAPI document was created (TaskRabbit's event notifications are HTTP POST webhooks, not WebSocket or SSE).

## Tags

- Gig Economy
- Handyman
- Home Services
- Marketplace
- Delivery
- Moving
- Partner API
- IKEA

## Timestamps

- **Created:** 2026-07-03
- **Modified:** 2026-07-03

## APIs

### TaskRabbit Home Services Estimate API

POST `/projects/estimate` is the first call in the Estimate, Availability, Bid, Book booking sequence - it returns service eligibility and a price estimate for a postal code or full address plus one or more requested services.

- **Human URL:** [https://developer.taskrabbit.com/docs/project-estimate](https://developer.taskrabbit.com/docs/project-estimate)
- **Base URL:** `https://{api_subdomain}.partner-platform.taskrabbit.com/2025-12`

#### Properties

- [Documentation](https://developer.taskrabbit.com/docs/overview-taskrabbit-home-services-api)
- [API Reference](https://developer.taskrabbit.com/reference/projectestimate)
- [OpenAPI](openapi/taskrabbit-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### TaskRabbit Home Services Availability API

POST `/projects/availability` returns real-time bookable time windows and estimated pricing for one or more services at a location.

- **Human URL:** [https://developer.taskrabbit.com/docs/checking-availability](https://developer.taskrabbit.com/docs/checking-availability)
- **Base URL:** `https://{api_subdomain}.partner-platform.taskrabbit.com/2025-12`

#### Properties

- [API Reference](https://developer.taskrabbit.com/reference/projectavailability)
- [OpenAPI](openapi/taskrabbit-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### TaskRabbit Home Services Booking API

POST `/projects/bid` locks a formal quote and Project UUID against a chosen time window, POST `/projects/book` completes the booking, GET `/projects/{project_uuid}` and POST `/projects/list` check status, POST `/projects/{project_uuid}/cancel` cancels with an enumerated reason, and a reschedule-availability/reschedule pair moves a booked project. `project.completed`, `project.canceled`, and `project.rescheduled` events are pushed as Svix-signed HTTP POST webhooks.

- **Human URL:** [https://developer.taskrabbit.com/docs/booking-a-project](https://developer.taskrabbit.com/docs/booking-a-project)
- **Base URL:** `https://{api_subdomain}.partner-platform.taskrabbit.com/2025-12`

#### Properties

- [API Reference: Bid](https://developer.taskrabbit.com/reference/projectbid)
- [API Reference: Book](https://developer.taskrabbit.com/reference/projectbook)
- [API Reference: Get Project](https://developer.taskrabbit.com/reference/getprojectbyuuid)
- [API Reference: Cancel](https://developer.taskrabbit.com/reference/cancelbookedproject)
- [Webhooks](https://developer.taskrabbit.com/docs/webhooks-1)
- [OpenAPI](openapi/taskrabbit-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### TaskRabbit Home Services Catalog API

GET `/brands/{brand_uuid}/services` returns a partner brand's full configured service catalog - names, pricing, and requirements. PUT updates a service's partner-defined external identifier for catalog reconciliation.

- **Human URL:** [https://developer.taskrabbit.com/docs/get-service-catalog](https://developer.taskrabbit.com/docs/get-service-catalog)
- **Base URL:** `https://{api_subdomain}.partner-platform.taskrabbit.com/2025-12`

#### Properties

- [API Reference: List Services](https://developer.taskrabbit.com/reference/listservicesbybranduuid)
- [API Reference: Update External Identifier](https://developer.taskrabbit.com/reference/updateserviceexternalidentifier)
- [OpenAPI](openapi/taskrabbit-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### TaskRabbit Delivery API (Dolly)

TaskRabbit acquired on-demand moving/delivery company Dolly in November 2024 and rebranded its service TaskRabbit Delivery; the pre-existing Dolly Partner API (PAPI) continues to power it. POST `/deliveries` quotes and creates a delivery, with companion endpoints for delivery info, units, tips, cancellation, routing, partner identity, and health checks. Courier lifecycle events (`COURIER_REQUESTED` through `DELIVERED`) are pushed as HTTP POST webhooks from an allowlisted set of source IPs.

- **Human URL:** [https://developer.taskrabbit.com/docs/overview](https://developer.taskrabbit.com/docs/overview)
- **Base URL:** `https://papi.dolly.com/v1` (Production) / `https://papi.sandbox.dolly.com/v1` (Sandbox)

#### Properties

- [Quoting Deliveries](https://developer.taskrabbit.com/docs/requesting-delivery-quotes)
- [Scheduling Deliveries](https://developer.taskrabbit.com/docs/scheduling)
- [Webhooks](https://developer.taskrabbit.com/docs/webhooks)
- [API Reference: Get Partner Info](https://developer.taskrabbit.com/reference/get-partner-information)
- [OpenAPI](openapi/taskrabbit-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/taskrabbit)
- [Website](https://www.taskrabbit.com)
- [Documentation](https://developer.taskrabbit.com/)
- [Plans](plans/taskrabbit-plans-pricing.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
