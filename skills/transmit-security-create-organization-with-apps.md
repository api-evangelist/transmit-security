---
name: transmit-security-create-organization-with-apps
description: Create a new organization and associate applications with it.
api: openapi/transmit-security-organizations-api-openapi.yml
operations:
- createOrganization
- addAppsToOrganization
generated: '2026-10-03'
method: generated
generator: extract-docs-artifacts.py skills (local)
source: openapi/transmit-security-organizations-api-openapi.yml ; every operationId checked against the contract
---

# transmit-security-create-organization-with-apps

Create a new organization and associate applications with it.

## Steps

1. 1. Call `createOrganization` with the required request body fields for the organization (e.g., name, description).
2. 2. Call `addAppsToOrganization` using the `organization_id` returned from step 1 and provide the list of `app_id`s in the request body.

## Rules

- Auth: Include a valid `AdminAccessToken` (OAuth2) bearer token in the `Authorization` header for both calls.
- Idempotency: The `createOrganization` operation is not idempotent; avoid duplicate calls.
- Errors: Handle HTTP 4xx/5xx responses as defined by the API; on rate‑limit exhaustion no specific HTTP status is defined.
