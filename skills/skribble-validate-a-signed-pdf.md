---
generated: '2026-10-18'
method: generated
name: skribble-validate-a-signed-pdf
description: Validate the digital signatures in a PDF with the Skribble Validation API and fetch the reports.
api: openapi/skribble-validation-v1-openapi.yml
operations:
- postAccessLogin
- postValidateDocument
- getInfosSigners
- getSkribbleReport
- getReportsETSI
- deleteValidation
source: Grounded in openapi/skribble-validation-v1-openapi.yml (operationIds verified verbatim) and https://api.docs.skribble.com/llms-full.txt (Authentication, Limits, Callbacks, Error Handling).
---

# Validate a signed pdf

Validate the digital signatures in a PDF with the Skribble Validation API and fetch the reports.

## Steps
1. Authenticate with `postAccessLogin` against document-validation.skribble.com.
2. Submit the file to `postValidateDocument`; keep the returned validation id.
3. Read signer details with `getInfosSigners` and reports with `getSkribbleReport` or `getReportsETSI`.
4. Remove the stored validation with `deleteValidation` when done. Validations consume credits; check `getBillingCreditsUsage`.

## Errors
400 bad input or malformed PDF, 401 expired token (re-login), 403 forbidden, 404 not found, 429 rate limited (back off and retry). See https://api.docs.skribble.com/error-handling.

## Idempotency
No idempotency keys are documented; do not blindly retry create calls; look up the existing request first.
