---
name: skribble-manage-signature-signer
description: Add or remove a signer to/from a signature request.
api: openapi/skribble-sign-v2-openapi.yml
operations:
- addSignatureSigner
- removeSignatureSigner
generated: '2026-10-18'
method: generated
generator: extract-docs-artifacts.py skills (deepseek)
source: openapi/skribble-sign-v2-openapi.yml ; every operationId checked against the contract
---

# skribble-manage-signature-signer

Add or remove a signer to/from a signature request.

## Steps

1. 1. Use `addSignatureSigner` POST operation with the `SR_ID` path parameter to add a new signer to a signature request, providing the signer details in the request body.
2. 2. Use `removeSignatureSigner` DELETE operation with both `SR_ID` and `SID` path parameters to remove a specific signer from a signature request.

## Rules

- Authentication requires a bearer token in the Authorization header
- Operations are idempotent for safe retry
- Use path parameters SR_ID for signature request ID and SID for signer ID
