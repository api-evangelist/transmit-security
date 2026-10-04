---
name: transmit-security-verify-session
description: Create a verification session, retrieve its result, and clean up the session.
api: openapi/transmit-security-verification-api-openapi.yml
operations:
- createSession
- getResult
- deleteSession
generated: '2026-10-03'
method: generated
generator: extract-docs-artifacts.py skills (local)
source: openapi/transmit-security-verification-api-openapi.yml ; every operationId checked against the contract
---

# transmit-security-verify-session

Create a verification session, retrieve its result, and clean up the session.

## Steps

1. 1. Call `createSession` – send a POST to `/api/v1/verification` with the required request body fields (as defined in the contract) and include an authentication header (e.g., `Authorization: Bearer <token>`).
2. 2. Call `getResult` – send a GET to `/api/v1/verification/{sid}/result` using the session ID returned from step 1 and include the same authentication header.
3. 3. Call `deleteSession` – send a DELETE to `/api/v1/verification/{sid}` with the session ID and the authentication header to remove the session.

## Rules

- Authentication: All requests must include a valid bearer token (e.g., `Authorization: Bearer <UserAccessToken>` or other supported scheme).
- Idempotency: The `deleteSession` operation is idempotent; repeating it after a successful deletion returns a not‑found response.
