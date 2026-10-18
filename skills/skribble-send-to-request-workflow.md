---
name: skribble-send-to-request-workflow
description: Create, track, download, and delete a Send-To request for document signing.
api: openapi/skribble-sign-v2-openapi.yml
operations:
- createSendTo
- trackSendTo
- downloadSendTo
- deleteSendTo
generated: '2026-10-18'
method: generated
generator: extract-docs-artifacts.py skills (deepseek)
source: openapi/skribble-sign-v2-openapi.yml ; every operationId checked against the contract
---

# skribble-send-to-request-workflow

Create, track, download, and delete a Send-To request for document signing.

## Steps

1. 1. Create a Send-To request using `createSendTo` operation with the required request body fields
2. 2. Track the status of the Send-To request using `trackSendTo` operation with the `SEND_TO_ID` path parameter
3. 3. Download the completed Send-To document using `downloadSendTo` operation with the `SEND_TO_ID` path parameter
4. 4. Delete the Send-To request using `deleteSendTo` operation with the `SEND_TO_ID` path parameter

## Rules

- Authentication requires a bearer token in the Authorization header
- The `SEND_TO_ID` path parameter must be included in tracking, download, and delete operations
- Operations follow a logical workflow from creation to deletion
- Multiple server endpoints are available for different regions and API versions
