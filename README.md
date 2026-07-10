# Applied Systems (applied-systems)

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
