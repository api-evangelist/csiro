---
name: csiro-find-and-download-dataset
description: Search the CSIRO Data Access Portal for a research data collection, inspect its metadata and licence, list its files and obtain download URLs.
api: csiro:dap-web-services
spec: openapi/csiro-dap-ws-v2-openapi.yml
operations:
  - getCollections
  - getCollection
  - getCollectionLicenceFile
  - getFiles
  - getDownloadUrls

generated: 2026-10-22
method: generated
---

# csiro-find-and-download-dataset

Search the CSIRO Data Access Portal for a research data collection, inspect its metadata and licence, list its files and obtain download URLs.

Base URL: https://data.csiro.au/dap/ws/v2 (see https://research.csiro.au/dap/developer-tools/web-services-ws-v2/).

## Steps

1. `getCollections` — GET /ws/v2/collections{ext} with `q` (keywords), `p`/`rpp` for paging, `sb` for sort. `ext` is a path parameter in the spec (format suffix).
2. `getCollection` — GET /ws/v2/collections/{id} for the chosen result.
3. `getCollectionLicenceFile` — GET /ws/v2/collections/{id}/licence; respect the licence before reuse.
4. `getFiles` — GET /ws/v2/collections/{id}/files (`folder`, `page`, `size`) to list contents.
5. `getDownloadUrls` — POST /ws/v2/collections/{collectionId}/downloadurls with the file selection body. This is a read-only request (no state change) despite using POST.

## Rules

- Read-only flow; no idempotency keys are documented.
- Page with `p` (page) and `rpp` (results per page) where offered.
- The spec declares basicAuth/bearer/oauth2 globally; check the ws/v2 guide for which calls need credentials. Never call login/token endpoints from an agent.
