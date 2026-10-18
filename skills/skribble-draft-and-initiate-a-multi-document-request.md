---
generated: '2026-10-18'
method: generated
name: skribble-draft-and-initiate-a-multi-document-request
description: Use Sign API v3 to build a draft signature request with several documents and observers, then invite signers.
api: openapi/skribble-sign-v3-openapi.yml
operations:
- accessLogin
- createSignatureRequest
- addDocumentInSignatureRequest
- addSignatureObserver
- initiateSignatureRequest
- getSignatureRequestDetails
source: Grounded in openapi/skribble-sign-v3-openapi.yml (operationIds verified verbatim) and https://api.docs.skribble.com/llms-full.txt (Authentication, Limits, Callbacks, Error Handling).
---

# Draft and initiate a multi document request

Use Sign API v3 to build a draft signature request with several documents and observers, then invite signers.

## Steps
1. Authenticate with `accessLogin`.
2. Create the request with `createSignatureRequest` (v3 supports drafts).
3. Attach additional PDFs with `addDocumentInSignatureRequest` and watchers with `addSignatureObserver`.
4. Start signing with `initiateSignatureRequest`, then follow status via callbacks or `getSignatureRequestDetails`.
5. v3 is a preview; see https://api.docs.skribble.com/api/sign-v3/migrate-from-v2 before switching from v2.

## Errors
400 bad input or malformed PDF, 401 expired token (re-login), 403 forbidden, 404 not found, 429 rate limited (back off and retry). See https://api.docs.skribble.com/error-handling.

## Idempotency
No idempotency keys are documented; do not blindly retry create calls; look up the existing request first.
