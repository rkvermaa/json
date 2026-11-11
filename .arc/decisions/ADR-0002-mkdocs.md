---
id: ADR-0002
category: component
title: Mkdocs
status: accepted
superseded_by: null
component_id: comp_mkdocs
responsibility: Documentation site tooling under docs/mkdocs (MkDocs, Python); builds
  the library's documentation, published by the publish_documentation workflow.
kind: library
split_reason: exists in the code
talks_to:
- component_id: comp_brown_field_proj_c_chore_002_define_architecture
  interaction: sync
  evidence: docs/mkdocs documents the library and builds examples from docs/ (build-time)
evidence: docs/mkdocs manifest; .github/workflows/publish_documentation.yml
---

## Context

docs/mkdocs manifest; .github/workflows/publish_documentation.yml

## Decision

Documentation site tooling under docs/mkdocs (MkDocs, Python); builds the library's documentation, published by the publish_documentation workflow.

Kept separate because exists in the code.

## Talks to

- **Brown Field Proj C Chore 002 Define Architecture** (sync) — docs/mkdocs documents the library and builds examples from docs/ (build-time)
