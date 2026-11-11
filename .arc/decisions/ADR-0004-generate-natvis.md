---
id: ADR-0004
category: component
title: Generate Natvis
status: accepted
superseded_by: null
component_id: comp_generate_natvis
responsibility: Natvis generation tooling under tools/generate_natvis, recorded as
  it exists today. It has its own manifest and is Python.
kind: library
split_reason: exists in the code
evidence: 'Codebase scan: tools/generate_natvis has its own manifest; Python with
  no server or UI framework'
---

## Context

Codebase scan: tools/generate_natvis has its own manifest; Python with no server or UI framework

## Decision

Natvis generation tooling under tools/generate_natvis, recorded as it exists today. It has its own manifest and is Python.

Kept separate because exists in the code.
