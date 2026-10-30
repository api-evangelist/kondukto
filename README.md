# Kondukto

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

> **Acquired or rebranded.** This company was acquired, merged or renamed. Its API, if it still exists, is offered under another name. This profile is kept as a historical record and is not maintained or rated.

Kondukto — now shipped as Invicti ASPM following Invicti Security's acquisition of the company — is an Application Security Posture Management platform that centralizes and automates the AppSec vulnerability management lifecycle. It ingests, deduplicates and correlates findings from more than eighty security scanners across SAST, DAST, SCA, container, infrastructure and pentest testing, enriches them with CWE, CVSS, EPSS, CISA KEV, EUVD threat intelligence and VEX exploitability data, and routes them to owning teams through Jira, GitLab, ServiceNow and webhook issue managers. Kondukto publishes a documented REST API v2 covering projects, products, teams, labels, scans and vulnerabilities, an open-source Go command-line client (KDT) that drives the same API from CI/CD pipelines, and a webhook surface for both outbound platform events and customer-hosted issue managers. The platform is deployed per customer, so the API host is deployment-specific.

**Areas:** Company · Application Security · ASPM · Vulnerability Management · DevSecOps · Security Orchestration · SAST · DAST · Software Composition Analysis · Container Security · SBOM · Security Testing

## Kondukto on APIs.io (historical record)

Everything profiled for Kondukto is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/kondukto/](https://apis.io/providers/kondukto/)** — or go straight to one of the APIs or properties below.

### APIs (11)

- [Kondukto Authorization Managers API](https://apis.io/apis/kondukto/kondukto-authorization-managers-api/) — The Authorization Managers API from Kondukto — 1 operation(s) for authorization managers.
- [Kondukto Events API](https://apis.io/apis/kondukto/kondukto-events-api/) — The Events API from Kondukto — 1 operation(s) for events.
- [Kondukto Health API](https://apis.io/apis/kondukto/kondukto-health-api/) — The Health API from Kondukto — 1 operation(s) for health.
- [Kondukto Labels API](https://apis.io/apis/kondukto/kondukto-labels-api/) — The Labels API from Kondukto — 3 operation(s) for labels.
- [Kondukto Products API](https://apis.io/apis/kondukto/kondukto-products-api/) — The Products API from Kondukto — 2 operation(s) for products.
- [Kondukto Projects API](https://apis.io/apis/kondukto/kondukto-projects-api/) — The Projects API from Kondukto — 7 operation(s) for projects.
- [Kondukto Scanners API](https://apis.io/apis/kondukto/kondukto-scanners-api/) — The Scanners API from Kondukto — 1 operation(s) for scanners.
- [Kondukto Scans API](https://apis.io/apis/kondukto/kondukto-scans-api/) — The Scans API from Kondukto — 10 operation(s) for scans.
- [Kondukto Teams API](https://apis.io/apis/kondukto/kondukto-teams-api/) — The Teams API from Kondukto — 5 operation(s) for teams.
- [Kondukto Users API](https://apis.io/apis/kondukto/kondukto-users-api/) — The Users API from Kondukto — 2 operation(s) for users.
- [Kondukto Vulnerabilities API](https://apis.io/apis/kondukto/kondukto-vulnerabilities-api/) — The Vulnerabilities API from Kondukto — 9 operation(s) for vulnerabilities.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Kondukto Webhooks](https://apis.io/asyncapis/kondukto/kondukto-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [kondukto](https://apis.io/servers/kondukto/kondukto/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Kondukto Agentic Access](https://apis.io/agentic-access/kondukto/kondukto-agentic-access/)

#### Collections (22)

Postman and Open Collection request collections.

- [Invicti ASPM (Kondukto) REST API v2 Authorization Managers API](https://apis.io/collections/kondukto/open-kondukto-authorization-managers-api/)
- [Invicti ASPM (Kondukto) REST API v2 Authorization Managers Events API](https://apis.io/collections/kondukto/open-kondukto-events-api/)
- [Invicti ASPM (Kondukto) REST API v2 Authorization Managers Health API](https://apis.io/collections/kondukto/open-kondukto-health-api/)
- [Invicti ASPM (Kondukto) REST API v2 Authorization Managers Labels API](https://apis.io/collections/kondukto/open-kondukto-labels-api/)
- [Invicti ASPM (Kondukto) REST API v2 Authorization Managers Products API](https://apis.io/collections/kondukto/open-kondukto-products-api/)
- [Invicti ASPM (Kondukto) REST API v2 Authorization Managers Projects API](https://apis.io/collections/kondukto/open-kondukto-projects-api/)
- [Invicti ASPM (Kondukto) REST API v2 Authorization Managers Scanners API](https://apis.io/collections/kondukto/open-kondukto-scanners-api/)
- [Invicti ASPM (Kondukto) REST API v2 Authorization Managers Scans API](https://apis.io/collections/kondukto/open-kondukto-scans-api/)
- [Invicti ASPM (Kondukto) REST API v2 Authorization Managers Teams API](https://apis.io/collections/kondukto/open-kondukto-teams-api/)
- [Invicti ASPM (Kondukto) REST API v2 Authorization Managers Users API](https://apis.io/collections/kondukto/open-kondukto-users-api/)
- [Invicti ASPM (Kondukto) REST API v2 Authorization Managers Vulnerabilities API](https://apis.io/collections/kondukto/open-kondukto-vulnerabilities-api/)
- [Invicti ASPM (Kondukto) REST API v2 Authorization Managers API](https://apis.io/collections/kondukto/postman-kondukto-authorization-managers-api/)
- [Invicti ASPM (Kondukto) REST API v2 Authorization Managers Events API](https://apis.io/collections/kondukto/postman-kondukto-events-api/)
- [Invicti ASPM (Kondukto) REST API v2 Authorization Managers Health API](https://apis.io/collections/kondukto/postman-kondukto-health-api/)
- [Invicti ASPM (Kondukto) REST API v2 Authorization Managers Labels API](https://apis.io/collections/kondukto/postman-kondukto-labels-api/)
- [Invicti ASPM (Kondukto) REST API v2 Authorization Managers Products API](https://apis.io/collections/kondukto/postman-kondukto-products-api/)
- [Invicti ASPM (Kondukto) REST API v2 Authorization Managers Projects API](https://apis.io/collections/kondukto/postman-kondukto-projects-api/)
- [Invicti ASPM (Kondukto) REST API v2 Authorization Managers Scanners API](https://apis.io/collections/kondukto/postman-kondukto-scanners-api/)
- [Invicti ASPM (Kondukto) REST API v2 Authorization Managers Scans API](https://apis.io/collections/kondukto/postman-kondukto-scans-api/)
- [Invicti ASPM (Kondukto) REST API v2 Authorization Managers Teams API](https://apis.io/collections/kondukto/postman-kondukto-teams-api/)
- [Invicti ASPM (Kondukto) REST API v2 Authorization Managers Users API](https://apis.io/collections/kondukto/postman-kondukto-users-api/)
- [Invicti ASPM (Kondukto) REST API v2 Authorization Managers Vulnerabilities API](https://apis.io/collections/kondukto/postman-kondukto-vulnerabilities-api/)

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Kondukto Aspm Overlay](https://apis.io/overlays/kondukto/kondukto-aspm-overlay/)

#### Security (4)

Authentication, trust centre, and vulnerability disclosure.

- [Kondukto Authentication](https://apis.io/security/kondukto/kondukto-authentication/)
- [Kondukto Domain Security](https://apis.io/security/kondukto/kondukto-domain-security/)
- [Kondukto Trust Center](https://apis.io/security/kondukto/kondukto-trust-center/)
- [Kondukto Vulnerability Disclosure](https://apis.io/security/kondukto/kondukto-vulnerability-disclosure/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Kondukto Plans](https://apis.io/plans/kondukto/kondukto-plans/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://kondukto.io)
- [Documentation](https://docs.kondukto.io/docs)
- [Getting started](https://docs.kondukto.io/reference/starting-with-kondukto-api)
- [API reference](https://docs.kondukto.io/reference/starting-with-kondukto-api)
- [Pricing](https://www.invicti.com/pricing)
- [Sign up](https://www.invicti.com/get-demo)
- [Support](https://docs.invicti.com/)
- [Blog](https://www.invicti.com/blog)
- [Security](https://www.invicti.com/.well-known/security.txt)
- [Compliance](https://www.invicti.com/compliance)
- [Terms of service](https://www.invicti.com/legal/terms)
- [Privacy policy](https://www.invicti.com/compliance/privacy-policy)
- [GitHub](https://github.com/kondukto-io)
- [Status](https://status.invicti.com)

## API Evangelist rating

**Not rated** — this company is recorded as acquired or rebranded, so no score is published. If it is in fact operating, say so on this repository and it will be re-profiled.

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Kondukto: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/kondukto/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
