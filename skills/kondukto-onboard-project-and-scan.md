---
name: Onboard a project and run its first scan
description: Register a repository as an Invicti ASPM (Kondukto) project, trigger a scanner against a branch, poll the asynchronous event to completion, and read the resulting findings.
api: openapi/kondukto-aspm-openapi.yml
operations:
  - check-alm-if-it-exists
  - create-a-project
  - get-active-scanners
  - create-new-scan
  - get-event-status
  - get-scan-detail
  - get-project-vulnerabilities
generated: '2026-07-19'
method: generated
source: openapi/kondukto-aspm-openapi.yml
---

# Onboard a project and run its first scan

Use this when a repository is not yet tracked in Invicti ASPM and you need it scanned.

## Before you start

- Base URL is your deployment host plus `/api/v2` — there is no shared public endpoint. Read it from `INVICTI_ASPM_HOST`.
- Send the API token in the **`X-Cookie`** header on every call. Not `Authorization`.
- `401 {"error": "failed to authorize"}` means the token is missing or revoked; `403 {"message": "forbidden operation"}` means the token's user lacks the role or team membership for that resource.
- **There is no idempotency key on this API.** Never blindly retry a `POST`. If a create call times out, re-read state (step 1 or `get-project-list`) before issuing it again.

## Steps

1. **Check whether the repository is already onboarded.** Call `check-alm-if-it-exists` with the ALM name (`github`, `gitlab`, …) and the repository id. If it already exists, skip to step 3 and use `get-project-detail` for the id.

2. **Create the project.** Call `create-a-project`. Identify the repository by either its ALM URL or its ALM id — both are accepted, and both can be read from CI environment variables. Set the team, labels, product name and criticality level at creation time so the finding routes correctly later.

3. **Find out which scanners this deployment actually has.** Call `get-active-scanners`. Scanner availability is per deployment; do not assume a tool is configured. Pick the tool name from this response rather than hardcoding one.

4. **Trigger the scan.** Call `create-new-scan` with the project, the tool from step 3, and the branch. For a container image use `image-scan` instead. If you already hold results from a scanner that ran elsewhere, use `import-scan-result` (multipart form) rather than triggering a new run.

5. **Poll to completion.** Scan creation is asynchronous and returns an event id. Poll `get-event-status` until it reports completion — do not re-issue `create-new-scan`, which would start a second scan. Back off between polls; long scans run for many minutes.

6. **Read the results.** Call `get-scan-detail` for the scan summary, then `get-project-vulnerabilities` for the findings. Both paginate with `limit` and `start` and return `{limit, start, total, ...}` — loop until `start + limit >= total`.

## Notes

- `get-project-scans` lists prior scans for the project if you need history.
- To gate a release rather than just read findings, use the release-criteria skill instead.
