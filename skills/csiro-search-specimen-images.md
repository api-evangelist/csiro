---
name: csiro-search-specimen-images
description: Search CSIRO National Research Collections specimen images.
api: csiro:dap-web-services
spec: openapi/csiro-dap-ws-v2-openapi.yml
operations:
  - getSpecimenImageResults
  - validateTerms

generated: 2026-10-22
method: generated
---

# csiro-search-specimen-images

Search CSIRO National Research Collections specimen images.

Base URL: https://data.csiro.au/dap/ws/v2 (see https://research.csiro.au/dap/developer-tools/web-services-ws-v2/).

## Steps

1. `validateTerms` — GET /ws/v2/domains/specimenImages/validateTerms to check taxonomy terms.
2. `getSpecimenImageResults` — GET /ws/v2/domains/specimenImages/search with `taxonomy`, `nationalSpecimenCollection`, `q`, paging `p`/`rpp`.

## Rules

- Read-only flow; no idempotency keys are documented.
- Page with `p` (page) and `rpp` (results per page) where offered.
- The spec declares basicAuth/bearer/oauth2 globally; check the ws/v2 guide for which calls need credentials. Never call login/token endpoints from an agent.
