---
name: Manage teams, products and finding ownership
description: Set up the ownership graph in Invicti ASPM (Kondukto) — teams, members, labels, products — so vulnerabilities route to the right people.
api: openapi/kondukto-aspm-openapi.yml
operations:
  - get-users
  - get-teams
  - create-a-team
  - update-team-members
  - get-team-members
  - create-label
  - get-labels
  - create-a-product
  - update-a-product
  - update-a-project
generated: '2026-07-19'
method: generated
source: openapi/kondukto-aspm-openapi.yml
---

# Manage teams, products and finding ownership

Use this when onboarding an organisation, not per scan. Ownership metadata is what makes the vulnerability filters and issue assignment useful later.

## Before you start

- Authenticate with the `X-Cookie` header. These are administrative operations; a `403 {"message": "forbidden operation"}` means the token's user lacks the role, not that the payload is wrong.
- The ownership graph is: **product** groups **projects**; a **project** belongs to a **team** and carries **labels**; a **team** has **users** as members. See `data-model/kondukto-data-model.yml`.

## Steps

1. **Find the users.** Call `get-users`, which queries by username or email, and `get-user-details` for one record. Users originate from local accounts or from a configured SSO authorization manager — list those with `get-active-auth-managers`. You cannot create users through this API.

2. **Create the team.** Call `create-a-team`. Then set membership with `update-team-members` and verify with `get-team-members`. Check `get-teams` or `get-teams-with-members` first so you do not create a duplicate — there is no idempotency key, and a repeated create is a second team, not a no-op.

3. **Create labels.** Call `create-label` for the cross-cutting tags you want to filter on later — compliance scope, data sensitivity, exposure. Read existing ones with `get-labels` first. Labels are the main lever for slicing the vulnerability database, so define them before onboarding projects rather than after.

4. **Create the product.** Call `create-a-product`. The product name must be unique and must not contain spaces. Attach projects with `update-a-product` — note this **overwrites** the product's project list with the values you send, so read the current membership with `get-a-product-details` and send the full intended set, not just additions.

5. **Attach projects to the graph.** Call `update-a-project` to set the team, labels and business criticality on existing projects. New projects can carry all of this at creation time instead.

## Notes

- `get-business-unit-tags` exposes business-unit classification tags for reporting.
- Roles and the permission matrix are configured in the platform UI, not through this API — see the user permission matrix in the docs.
