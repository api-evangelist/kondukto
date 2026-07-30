---
name: Search and triage vulnerabilities
description: Query the correlated vulnerability database in Invicti ASPM (Kondukto) with its filter set, page through results safely, and pull the detail and attachments for a finding.
api: openapi/kondukto-aspm-openapi.yml
operations:
  - get-vulnerabilities
  - get-vulnerability-details
  - get-project-vulnerabilities
  - upload-screenshots
  - delete-a-screenshot
  - get-labels
  - get-teams
generated: '2026-07-19'
method: generated
source: openapi/kondukto-aspm-openapi.yml
---

# Search and triage vulnerabilities

Use this to answer posture questions across the estate — "what critical reachable findings are open on production branches" — rather than to look at one scan.

## Before you start

- Authenticate with the `X-Cookie` header.
- Findings in this database are **deduplicated and correlated across scanners**. One record may represent the same issue reported by several tools, so do not sum counts across tools.

## Steps

1. **Query the database.** Call `get-vulnerabilities`. It takes roughly thirty filters; combine them rather than filtering client-side. The ones that matter most:
   - Risk: `severity`, `cvss`, `woe` (window of exposure, accepts comparison operators).
   - Scope: `project_name`, `product_name`, `teams`, `team_ids`, `labels`, `label_ids`, `branch`, `path`.
   - Classification: `type` (`sast`, `dast`, `sca`, `cs`, `infra`), `cwe_no`, `cwe_name`, `tool_name`.
   - Triage state: `status` (`new`, `recurrent`, …), `fp`, `tp`, `wf`, `mitigated`, `overdue`, `issue_status`.
   - Time: `from`, `to` on first-seen.

   Several filters accept comma-separated lists. Parameters the reference marks searchable match partial values; the rest need an exact match — passing a partial value to an exact-match filter silently returns nothing, which is the most common cause of an unexpectedly empty result.

2. **Page correctly.** Use `limit` and `start`. The response is `{limit, start, total, vulnerabilities[]}` — loop until `start + limit >= total`. There is no cursor and no `Link` header.

3. **Resolve filter ids first when filtering by team or label id.** Call `get-teams` or `get-labels` to map names to ids; `team_ids` and `label_ids` will not accept names.

4. **Scope to one project** with `get-project-vulnerabilities` when you already know the project — it is the narrower query and avoids paging the whole estate.

5. **Pull the detail.** Call `get-vulnerability-details` with the vulnerability id (a 24-character hex ObjectId) for the full record.

6. **Attach evidence if triaging.** `upload-screenshots` takes base64-encoded attachments limited to pdf, html, jpg, png, avi, txt and mp4; `delete-a-screenshot` removes one by attachment id.

## Notes

- Records carry CWE, CVSS v3, and — on recent releases — EPSS, CISA KEV and VEX applicability. Prefer exploitability signals over raw CVSS when ranking.
- Importing findings from a scanner the platform does not natively integrate is a different flow: `create-a-sast-vulnerability`, `create-a-dast-vulnerability`, `create-a-sca-vulnerability`, `create-a-pentest-vulnerability` and `create-an-infra-vulnerability` each import findings of that class against a project.
