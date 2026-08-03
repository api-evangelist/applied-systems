# Applied Systems (applied-systems)

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Applied Systems is a leading global provider of cloud-based software for the business of insurance, best known for the **Applied Epic** agency management system (alongside TAM, Applied CSR24, and related products). Applied exposes a RESTful developer platform for Applied Epic through the **Applied Dev Center** ([devcenter.myappliedproducts.com](https://devcenter.myappliedproducts.com/docs/overview)), which supersedes the older Applied Epic SDK.

The platform lets certified partners and agencies read and write core Epic data - clients/accounts, policies, contacts, attachments, and activities - over OAuth 2.0, with a base URL of `https://api.myappliedproducts.com`.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/applied-systems/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/applied-systems/refs/heads/main/apis.yml)

## Access Model (Gated)

Applied's developer platform is **not open self-serve**. Access is tied to being (or partnering with) an Applied Epic customer:

1. **Register** at the Applied Dev Center and create an application.
2. **Obtain credentials** - an API key plus OAuth client ID / client secret - and subscribe to API products.
3. **Build and test in a sandbox** against simulated data.
4. **Submit a production request** with your name, email, organization name, enterprise ID, and Epic database name.
5. **Await approval** - Applied reviews the request and, once approved, emails production credentials.

Applied also runs a **certified integration partner** program for third-party vendors distributing integrations against Applied Epic.

**Authentication:** OAuth 2.0 - exchange client ID / client secret for a Bearer access token; scopes such as `epic/clients:read` and `epic/clients:all` gate resource access.

## Tags

- Insurance
- InsurTech
- Agency Management
- Applied Epic
- CRM
- Policy Management
- Partner Gated

## Timestamps

- **Created:** 2026-07-10
- **Modified:** 2026-07-10

## APIs

### Applied Epic Clients (CRM) API

Read Applied Epic client (account) records - client lookup, benefits data (employee counts, HIPAA compliance), and identifiers used for VoIP caller identification.

- **Base URL:** `https://api.myappliedproducts.com/crm/v1`
- **Confirmed endpoint:** `GET /crm/v1/clients`
- **Scopes:** `epic/clients:read`, `epic/clients:all`

### Applied Epic Policies API

Retrieve the policies attached to an Epic client.

- **Base URL:** `https://api.myappliedproducts.com/policy/v1`
- **Confirmed endpoint:** `GET /policy/v1/clients/{clientId}/policies`

### Applied Epic Contacts API *(endpoints modeled)*

Centralize contact data for clients, prospects, carriers, and vendors, filtered by classification, email, or account. Named in Applied's own API blog; specific REST paths are behind the gated Dev Center and are not fabricated here.

### Applied Epic Attachments API *(endpoints modeled)*

Manage documents across Epic workflows - retrieve active attachments on a client account, upload call recordings and transcripts to accounts or activities, access proof-of-insurance attachments, and attach damage photos to claims. Named in Applied's own API blog; REST paths behind the gated Dev Center.

### Applied Epic Activities API *(endpoints modeled)*

Work with Epic activities - the actions and follow-up reminders tracked against each account. The legacy Applied Epic SDK exposed activity insert operations; the modern REST surface is behind the gated Dev Center.

## Common Properties

- [Website](https://www.appliedsystems.com)
- [LinkedIn](https://www.linkedin.com/company/applied-systems)
- [Documentation](https://devcenter.myappliedproducts.com/docs/overview)
- [Developer Portal](https://devcenter.myappliedproducts.com/home)
- [Plans](plans/applied-systems-plans-pricing.yml)
- [Rate Limits](rate-limits/applied-systems-rate-limits.yml)
- [Fin Ops](finops/applied-systems-finops.yml)

## WebSocket Review

Applied Systems does **not** publish a documented public WebSocket API. The Applied Epic developer platform is request/response REST over HTTPS secured with OAuth 2.0; no `ws://` or `wss://` endpoint is documented on Applied's own API. See [review.yml](review.yml).

## Pricing Note

There is no standalone, published, usage-metered API price. The developer sandbox is free; production access is approval-gated and bundled with the Applied Epic license (enterprise, quote-based) and any certified-partner agreement. Public dollar figures cited in the plans/FinOps files come from third-party aggregators, not Applied.

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
