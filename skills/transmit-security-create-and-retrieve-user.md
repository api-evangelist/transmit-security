---
name: transmit-security-create-and-retrieve-user
description: Create a new user and then retrieve its details.
api: openapi/transmit-security-users-api-openapi.yml
operations:
- createUser
- getUserById
generated: '2026-10-03'
method: generated
generator: extract-docs-artifacts.py skills (local)
source: openapi/transmit-security-users-api-openapi.yml ; every operationId checked against the contract
---

# transmit-security-create-and-retrieve-user

Create a new user and then retrieve its details.

## Steps

1. 1. Call `createUser` with a JSON body containing the required user fields (e.g., `email`, `username`, `password`).
2. 2. Use the `user_id` returned from `createUser` and call `getUserById` with the path parameter `{user_id}` to fetch the created user.

## Rules

- Auth: Include a valid `Authorization: Bearer <UserAccessToken>` header (or any of the listed OAuth2 tokens) for both operations.
- Errors: Handle HTTP 4xx/5xx responses as defined in the API contract; no rate‑limit headers are provided.
