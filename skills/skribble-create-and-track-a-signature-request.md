---
generated: '2026-10-18'
method: generated
name: skribble-create-and-track-a-signature-request
description: Upload a PDF, create a Skribble signature request for one or more signers, track its status and download the signed document.
api: openapi/skribble-sign-v2-openapi.yml
operations:
- accessLogin
- uploadDocument
- createSignatureRequest
- getSignatureRequestDetails
- remindSignatureRequest
- getDocumentContent
source: Grounded in openapi/skribble-sign-v2-openapi.yml (operationIds verified verbatim) and https://api.docs.skribble.com/llms-full.txt (Authentication, Limits, Callbacks, Error Handling).
---

# Create and track a signature request

Upload a PDF, create a Skribble signature request for one or more signers, track its status and download the signed document.

## Steps
1. Call `accessLogin` with username and API key; cache the JWT (~20 min) and send it as `Authorization: Bearer`.
2. Optionally `uploadDocument` first, or pass the PDF inline to `createSignatureRequest` with signers and signature quality (SES/AES/QES).
3. Set a callback URL on the request; Skribble does not offer webhooks, so prefer callbacks over polling `getSignatureRequestDetails`.
4. Use `remindSignatureRequest` sparingly: one reminder per signer per hour, or 429.
5. When status is signed, fetch the result with `getDocumentContent` using the request's document id.

## Errors
400 bad input or malformed PDF, 401 expired token (re-login), 403 forbidden, 404 not found, 429 rate limited (back off and retry). See https://api.docs.skribble.com/error-handling.

## Idempotency
No idempotency keys are documented; do not blindly retry create calls; look up the existing request first.
