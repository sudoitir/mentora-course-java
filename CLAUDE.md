# mentora-course-java — Project Guide (CLAUDE.md)

> Source of truth for anyone (human or agent) working on this **Mentora course package**.
> This repo holds **course content only** — no app code. The app lives in the
> [Mentora](https://github.com/sudoitir/Mentora) repo.

## What this is

The **Java: Zero to Hired** course: a Persian (RTL), project-based path from zero to junior Java developer
over **40 weeks / 6 phases / ~7 hours per week**. It is packaged as a **Mentora course package** — a
directory of JSON conforming to the Mentora course-package format — that the Mentora app installs from a
local folder, `.zip`, git repo (public **or private**), or registry, and renders **fully offline**.

## Cross-repo relationship (read this)

This repo and the app repo evolve together:

- **Format / schema source of truth:** the **Mentora** repo —
  [`docs/COURSE_ECOSYSTEM.md`](https://github.com/sudoitir/Mentora/blob/master/docs/COURSE_ECOSYSTEM.md)
  (package format, directory layout, all JSON Schemas) and
  [`CONTENT_SCHEMA.md`](https://github.com/sudoitir/Mentora/blob/master/CONTENT_SCHEMA.md) (the lesson/`Week`
  field contract + `WeekValidator` counts).
- **Authoring tool:** the **`course-author`** skill in the Mentora repo
  (`.claude/skills/course-author/SKILL.md`) — the world-class-mentor generator that emits the lesson JSON in
  this repo.
- **Change protocol:** **schema changes land in Mentora first** (bump `schemaVersion`, update the spec +
  the loader/validator), **then** content here is updated to track the new `schemaVersion`. Never invent a
  field here that the spec does not define; if content needs a new field, add it to the spec first.
- When you change content here in a way that needs app support (a new `visual` kind, a new `resource.kind`),
  open a corresponding change in Mentora.

## Layout

```
course.json                 # course manifest: id "mentora.java", version, locale fa / rtl, modules[]
modules/java-p1 … java-p6/  # module (phase) manifests; each lists its weeks as {id, number, title}
lessons/java-wNN.json       # full week content as clean JSON (the app's Week schema)
localization/{fa,en}.json   # library-facing strings
authors/authors.json        # attribution
registry-entry.json         # entry for a registry index
assets/{images,diagrams,pdf,video}/
```

## Authoring rules (essentials)

- **Persian, RTL, exceptionally fluent**, warm, second-person prose addressed to the learner. **Code is
  LTR** (English keywords, Persian comments) with **authored `output`** (no real execution offline).
- **Never hardcode the learner's name** — use the `{name}` token, sparingly (welcome / next-week hook).
- **Build first, understand why later**; analogy + a typed `visual`; faded worked examples; SRS flashcards;
  active-recall quizzes; ☕ version notes (runs on Java 8+); 🎤 interview corner.
- **Target Java 25 / Spring Boot 4 (`jakarta.*`)** but teach so code runs on Java 8+; verify APIs via
  Context7 MCP. Note Spring Boot 3 → 4 differences where helpful.
- Every `lessons/<id>.json` must satisfy the **`WeekValidator`** counts (objectives ≥ 3, lessons ≥ 2,
  glossary ≥ 3, flashcards 6–10, quiz 5–8, interview 2–4, …). Run the `course-author` checklist before
  declaring a week done.
- **Deterministic ids:** lesson `java-wNN` (zero-padded), module `java-pN`; `lesson.phaseID` == owning
  module id.

## Phases (40 weeks)

| Module | Title | Weeks |
|--------|-------|-------|
| java-p1 | بنیادها | 1–4 |
| java-p2 | شیء‌گرایی | 5–10 |
| java-p3 | ابزارهای حرفه‌ای | 11–16 |
| java-p4 | پایگاه‌داده و SQL | 17–20 |
| java-p5 | اسپرینگ بوت | 21–32 |
| java-p6 | پروژه‌ی پایانی و حرفه | 33–40 |

## Status

- ✅ Manifests for all 40 weeks; **Week 1 authored** (`lessons/java-w01.json`).
- ⬜ Weeks 2–40: descriptors present; author content with the `course-author` skill.

## Working agreement

- Author as a **world-class Java mentor**: engaging, memorable, rigorous — never dry.
- Keep this guide at the level of essentials; the authoritative format lives in the Mentora repo.
- Default mentee name may be **Aylin**, but the name is configurable — always use `{name}`.
