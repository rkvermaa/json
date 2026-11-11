---
id: ADR-0005
category: component
title: Serve Header
status: accepted
superseded_by: null
component_id: comp_serve_header
responsibility: Developer tooling under tools/serve_header (Python) that serves the
  amalgamated header locally; not a production service.
kind: library
split_reason: exists in the code
evidence: tools/serve_header manifest
---

## Context

tools/serve_header manifest

## Decision

Developer tooling under tools/serve_header (Python) that serves the amalgamated header locally; not a production service.

Kept separate because exists in the code.
