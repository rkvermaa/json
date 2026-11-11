---
id: ADR-0001
category: component
title: Brown Field Proj C Chore 002 Define Architecture
status: accepted
superseded_by: null
component_id: comp_brown_field_proj_c_chore_002_define_architecture
responsibility: The nlohmann/json C++ header-only JSON library (headers in include/,
  amalgamated into single_include/nlohmann); the Swift Package.swift exposes the single
  header as library product 'json' for Apple platforms. Built and tested through CMake,
  Meson, Bazel and Make; tests live in tests/.
kind: library
split_reason: exists in the code
talks_to:
- component_id: comp_astyle
  interaction: sync
  evidence: tools/astyle formats sources in include/ and tests/ (build-time)
evidence: Package.swift (product 'json', path single_include/nlohmann); top-level
  CMakeLists.txt, meson.build, MODULE.bazel, include/, single_include/, tests/
---

## Context

Package.swift (product 'json', path single_include/nlohmann); top-level CMakeLists.txt, meson.build, MODULE.bazel, include/, single_include/, tests/

## Decision

The nlohmann/json C++ header-only JSON library (headers in include/, amalgamated into single_include/nlohmann); the Swift Package.swift exposes the single header as library product 'json' for Apple platforms. Built and tested through CMake, Meson, Bazel and Make; tests live in tests/.

Kept separate because exists in the code.

## Talks to

- **Astyle** (sync) — tools/astyle formats sources in include/ and tests/ (build-time)
