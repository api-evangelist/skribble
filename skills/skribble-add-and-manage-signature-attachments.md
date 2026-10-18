---
name: skribble-add-and-manage-signature-attachments
description: Add and manage attachments to a signature request.
api: openapi/skribble-sign-v2-openapi.yml
operations:
- createSignatureAttachment
- getSignatureAttachmentContent
- deleteSignatureAttachment
generated: '2026-10-18'
method: generated
generator: extract-docs-artifacts.py skills (deepseek)
source: openapi/skribble-sign-v2-openapi.yml ; every operationId checked against the contract
---

# skribble-add-and-manage-signature-attachments

Add and manage attachments to a signature request.

## Steps

1. 1. Add an attachment to a signature request using `createSignatureAttachment` with the SR_ID path parameter and attachment data in the request body
2. 2. Retrieve the content of a specific attachment using `getSignatureAttachmentContent` with SR_ID and ATTACHMENT_ID path parameters
3. 3. Remove an attachment from a signature request using `deleteSignatureAttachment` with SR_ID and ATTACHMENT_ID path parameters

## Rules

- Authentication requires a bearer token in the Authorization header
- Operations are idempotent for safe retries
- Path parameters SR_ID and ATTACHMENT_ID are required for specific operations
