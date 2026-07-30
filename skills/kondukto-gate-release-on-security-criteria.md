---
name: Gate a release on security criteria
description: Run a scan in a CI/CD pipeline and decide whether to pass or fail the build using Invicti ASPM (Kondukto) project security criteria.
api: openapi/kondukto-aspm-openapi.yml
operations:
  - get-project-detail
  - create-new-scan
  - get-event-status
  - get-scan-release-status
  - project-security-criteria-status
  - get-project-vulnerabilities
generated: '2026-07-19'
method: generated
source: openapi/kondukto-aspm-openapi.yml
---

# Gate a release on security criteria

Use this inside a pipeline to block a deploy when an application's security posture regresses.

## Before you start

- Authenticate with the `X-Cookie` header. See `authentication/kondukto-authentication.yml`.
- Security criteria are configured per project in the platform; this flow reads the verdict, it does not define it.
- Prefer this over threshold arithmetic in your own pipeline script: the criteria live with the project, so they stay consistent across every pipeline that scans it.

## Steps

1. **Resolve the project.** Call `get-project-detail` to confirm the project exists and to read its default branch.

2. **Scan the branch under test.** Call `create-new-scan` with the project, tool and branch. Poll `get-event-status` until the event completes. Do not re-issue the scan while polling — there is no idempotency key on this API and a retry starts a second scan.

3. **Read the verdict for that scan.** Call `get-scan-release-status` with the scan id. This returns the security criteria evaluation for the specific scan you just ran, which is the correct signal for a pipeline gate.

4. **Or read the project-level posture.** Call `project-security-criteria-status` when you want the current criteria state of the project as a whole rather than of one scan — for example on a scheduled posture check rather than a per-commit gate.

5. **Fail the build on a negative verdict.** Map the criteria result to your exit code. If you need to explain the failure, call `get-project-vulnerabilities` filtered by `severity` and `status` to list what breached, and page through with `limit`/`start`.

## Notes

- The `kdt` CLI wraps this whole flow as `kdt release -p <project> -b <branch> --sast --sca --dast`, and `kdt scan` accepts `--threshold-crit`/`--threshold-high`/… plus `--threshold-risk` for threshold-based gating instead of configured criteria. Exit code `100` from the CLI means the token was not authorized, not that the gate failed.
- For pull-request gating, the target branch must have been scanned at least once to serve as the comparison baseline.
