---
id: ADR-0009
category: cross_cutting
title: 'Cross-cutting: Security and quality scanning'
status: accepted
superseded_by: null
component_id: null
decision: CodeQL, Semgrep, Flawfinder, CIFuzz and OpenSSF Scorecards run in CI; dependency-review
  checks dependency changes.
evidence: .github/workflows/codeql-analysis.yml, semgrep.yml, flawfinder.yml, cifuzz.yml,
  scorecards.yml, dependency-review.yml
---

## Context

.github/workflows/codeql-analysis.yml, semgrep.yml, flawfinder.yml, cifuzz.yml, scorecards.yml, dependency-review.yml

## Decision

CodeQL, Semgrep, Flawfinder, CIFuzz and OpenSSF Scorecards run in CI; dependency-review checks dependency changes.
