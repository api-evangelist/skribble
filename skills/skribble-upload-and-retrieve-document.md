---
name: skribble-upload-and-retrieve-document
description: Upload a document to Skribble and then retrieve its metadata and content.
api: openapi/skribble-sign-v2-openapi.yml
operations:
- uploadDocument
- getDocumentMetadata
- getDocumentContent
generated: '2026-10-18'
method: generated
generator: extract-docs-artifacts.py skills (deepseek)
source: openapi/skribble-sign-v2-openapi.yml ; every operationId checked against the contract
---

# skribble-upload-and-retrieve-document

Upload a document to Skribble and then retrieve its metadata and content.

## Steps

1. 1. Upload a document using `uploadDocument` operation with the document file in the request body
2. 2. Retrieve document metadata using `getDocumentMetadata` operation with the DOC_ID path parameter from the upload response
3. 3. Get document content using `getDocumentContent` operation with the DOC_ID path parameter

## Rules

- Authentication requires a bearer token in the Authorization header
- Document operations use path parameters like DOC_ID and PAGE_ID for specific resources
- The API supports multiple server endpoints including https://api.skribble.com/v2 and https://api.skribble.com/v3
