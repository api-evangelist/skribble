---
name: skribble-create-and-manage-signature-request
description: Create a signature request, add documents, initiate the signing process, and manage its lifecycle.
api: openapi/skribble-sign-v2-openapi.yml
operations:
- createSignatureRequest
- addDocumentInSignatureRequest
- initiateSignatureRequest
- getSignatureRequestDetails
- withdrawSignatureRequest
generated: '2026-10-18'
method: generated
generator: extract-docs-artifacts.py skills (deepseek)
source: openapi/skribble-sign-v2-openapi.yml ; every operationId checked against the contract
---

# skribble-create-and-manage-signature-request

Create a signature request, add documents, initiate the signing process, and manage its lifecycle.

## Steps

1. 1. Create a signature request using `createSignatureRequest` with required fields in the request body
2. 2. Add documents to the signature request using `addDocumentInSignatureRequest` with the SR_ID path parameter and document data
3. 3. Initiate the signing process using `initiateSignatureRequest` with the SR_ID path parameter
4. 4. Check status using `getSignatureRequestDetails` with the SR_ID path parameter
5. 5. Withdraw if needed using `withdrawSignatureRequest` with the SR_ID path parameter

## Rules

- Use bearer authentication header
- Signature requests can be withdrawn after initiation
- Operations require specific path parameters like SR_ID and DOC_ID
