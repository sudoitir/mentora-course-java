# Changelog

All notable changes to the **Java: Zero to Hired** course package. Format: [Keep a Changelog]; the package
follows SemVer for its `version` and tracks the Mentora `schemaVersion` it targets.

## [Unreleased] — Course Structure v2
### Changed
- Migrated to the **v2 content schema** (block-based, capability-driven). `lessons/java-w01.json` now uses
  `lessons[].blocks[]` (flat `type`-keyed blocks), `practice` (was `project`) with generic `tables`, `recall`
  (was `exercises`), `interview` (was `interviewCorner`), and `glossary` `{term, translit, definition}`.
- `course.json` and the week declare `capabilities` (`hasCode`, `hasVersions`, `hasInterview`, `hasProject`,
  `hasDiagrams`); the Java-bespoke diagrams are now data-driven (`nested` / `flow`).
- Weeks 2–40 will be authored against the v2 schema via the `course-author` skill.

## [1.0.0] — 2026-06-19
### Added
- Initial package scaffold targeting `schemaVersion` 1.0.0.
- Course manifest (`course.json`) + six module manifests (`java-p1` … `java-p6`) covering all 40 weeks.
- Week 1 fully authored in Persian (`lessons/java-w01.json`).
- Weeks 2–40 listed as roadmap descriptors (content authored progressively via the `course-author` skill).
