---
name: csiro-casda-cutouts
description: Find CASDA (ASKAP) cutout data products for a sky position.
api: csiro:dap-web-services
spec: openapi/csiro-dap-ws-v2-openapi.yml
operations:
  - getCutoutSurveys
  - getCutoutDetail

generated: 2026-10-22
method: generated
---

# csiro-casda-cutouts

Find CASDA (ASKAP) cutout data products for a sky position.

Base URL: https://data.csiro.au/dap/ws/v2 (see https://research.csiro.au/dap/developer-tools/web-services-ws-v2/).

## Steps

1. `getCutoutSurveys` — GET /ws/v2/domains/casdaCutout/surveys to list supported surveys.
2. `getCutoutDetail` — GET /ws/v2/domains/casdaCutout/cutout with `surveys`, `ra`, `dec`, `size`.

## Rules

- Read-only flow; no idempotency keys are documented.
- Page with `p` (page) and `rpp` (results per page) where offered.
- The spec declares basicAuth/bearer/oauth2 globally; check the ws/v2 guide for which calls need credentials. Never call login/token endpoints from an agent.
