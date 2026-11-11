---
id: ADR-0007
category: deployment_target
title: "Deployment target: No hosted runtime: the library is distributed as source\
  \ (single header / CMake\u2026"
status: accepted
superseded_by: null
component_id: null
decision: 'No hosted runtime: the library is distributed as source (single header
  / CMake, Meson, Bazel and Swift package) and consumed by downstream projects; CI
  runs on GitHub Actions; documentation is published as a static site.'
evidence: Package.swift, CMakeLists.txt, .github/workflows/*.yml (ubuntu, macos, windows,
  publish_documentation)
---

## Context

Package.swift, CMakeLists.txt, .github/workflows/*.yml (ubuntu, macos, windows, publish_documentation)

## Decision

No hosted runtime: the library is distributed as source (single header / CMake, Meson, Bazel and Swift package) and consumed by downstream projects; CI runs on GitHub Actions; documentation is published as a static site.
