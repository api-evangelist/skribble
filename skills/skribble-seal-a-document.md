---
generated: '2026-10-18'
method: generated
name: skribble-seal-a-document
description: Apply an organisation (legal entity) electronic seal to a PDF without human signers.
api: openapi/skribble-sign-v2-openapi.yml
operations:
- accessLogin
- sealDocument
- getDocumentContent
source: Grounded in openapi/skribble-sign-v2-openapi.yml (operationIds verified verbatim) and https://api.docs.skribble.com/llms-full.txt (Authentication, Limits, Callbacks, Error Handling).
---

# Seal a document

Apply an organisation (legal entity) electronic seal to a PDF without human signers.

## Steps
1. Authenticate with `accessLogin` using an account entitled to sealing.
2. Call `sealDocument` with the PDF content (and seal account name if you have several).
3. Download the sealed PDF with `getDocumentContent`. See https://api.docs.skribble.com/sign-api-sealing.

## Errors
400 bad input or malformed PDF, 401 expired token (re-login), 403 forbidden, 404 not found, 429 rate limited (back off and retry). See https://api.docs.skribble.com/error-handling.

## Idempotency
No idempotency keys are documented; do not blindly retry create calls; look up the existing request first.
