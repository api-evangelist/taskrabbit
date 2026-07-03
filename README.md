# TaskRabbit (taskrabbit)

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
