---
name: transmit-security-auth-magic-link-login
description: Send a magic link to a user's email and then authenticate the user using the received link.
api: openapi/transmit-security-auth-api-openapi.yml
operations:
- sendMagicLinkEmail
- authenticateMagicLink
generated: '2026-10-03'
method: generated
generator: extract-docs-artifacts.py skills (local)
source: openapi/transmit-security-auth-api-openapi.yml ; every operationId checked against the contract
---

# transmit-security-auth-magic-link-login

Send a magic link to a user's email and then authenticate the user using the received link.

## Steps

1. 1. Call `sendMagicLinkEmail` with the required fields `email` and optional `redirectUrl` as defined in the contract.
2. 2. After the user clicks the link, call `authenticateMagicLink` with the fields `token` (the link token) and optional `redirectUrl`.

## Rules

- Authentication: No authentication header is required for these endpoints.
- Rate limiting: No rate limit is defined; exhaustion returns no specific HTTP status.
