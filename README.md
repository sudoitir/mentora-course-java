# Java: Zero to Hired — a Mentora course

> A Persian (RTL), project-based path from zero to junior Java developer over **40 weeks / 6 phases**.
> This repository is a **Mentora course package** — a portable bundle of JSON the
> [Mentora](https://github.com/sudoitir/Mentora) app installs and renders **offline**.

## What this is

A course in Mentora is a directory of JSON conforming to the **Mentora course-package format**
(`schemaVersion` 1.0.0). The app can install it from a local folder, a `.zip`, a git repo (public **or
private**), or a registry — and renders it fully offline once cached. See the format spec in the Mentora
repo: [`docs/COURSE_ECOSYSTEM.md`](https://github.com/sudoitir/Mentora/blob/master/docs/COURSE_ECOSYSTEM.md).

## Layout

```
course.json                 # course manifest (id, version, locale/RTL, modules[])
modules/java-p1 … java-p6/  # one module (phase) manifest each; lists week descriptors
lessons/java-wNN.json       # full week content (the app's Week schema, as clean JSON)
localization/               # library-facing strings (fa, en)
authors/authors.json        # attribution
registry-entry.json         # this course's entry for a registry index
assets/                     # images / diagrams / pdf / video (referenced by lessons)
```

## Status

- ✅ Manifests for all 40 weeks (6 phases).
- ✅ **Week 1** authored in full (`lessons/java-w01.json`).
- ⬜ Weeks 2–40: roadmap descriptors present; content authored progressively.

## Authoring

Content is generated/edited with the **`course-author`** skill that lives in the Mentora repo
(`.claude/skills/course-author/SKILL.md`) — a world-class-mentor guide that emits schema-valid lesson JSON.
Each `lessons/<id>.json` must satisfy the `WeekValidator` rules documented in
[`CONTENT_SCHEMA.md`](https://github.com/sudoitir/Mentora/blob/master/CONTENT_SCHEMA.md).

## Installing into Mentora

In Mentora → **Add Course**, choose a source:
- **Git URL** — `https://github.com/sudoitir/mentora-course-java` (for a **private** repo, paste a token;
  it is stored in the system Keychain, never on disk).
- **Local folder** — point at a clone of this repo.
- **Zip** — a zipped export of this repo.

## License

Course content: **CC BY-NC-SA 4.0** (see [`LICENSE`](LICENSE)). Embedded code snippets are free to reuse.
