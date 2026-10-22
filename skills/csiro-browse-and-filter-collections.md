---
name: csiro-browse-and-filter-collections
description: Browse DAP collections by field of research, keyword or geographic bounding box.
api: csiro:dap-web-services
spec: openapi/csiro-dap-ws-v2-openapi.yml
operations:
  - getFieldsOfResearch
  - getKeywords
  - getCollectionsByBrowse
  - getCollectionsByLocation
  - getCollectionsSearch

generated: 2026-10-22
method: generated
---

# csiro-browse-and-filter-collections

Browse DAP collections by field of research, keyword or geographic bounding box.

Base URL: https://data.csiro.au/dap/ws/v2 (see https://research.csiro.au/dap/developer-tools/web-services-ws-v2/).

## Steps

1. `getFieldsOfResearch` / `getKeywords` — list browse vocabularies.
2. `getCollectionsByBrowse` — GET /ws/v2/collections/browse/{browseType}/{browseValue}, paged with `p`/`rpp`.
3. `getCollectionsByLocation` — GET /ws/v2/collections/searchbylocation with `n`,`s`,`e`,`w` bounds.
4. `getCollectionsSearch` — GET /ws/v2/collections/search for field-specific filters (`name`, `for`, dates `psd`/`ped`).

## Rules

- Read-only flow; no idempotency keys are documented.
- Page with `p` (page) and `rpp` (results per page) where offered.
- The spec declares basicAuth/bearer/oauth2 globally; check the ws/v2 guide for which calls need credentials. Never call login/token endpoints from an agent.
