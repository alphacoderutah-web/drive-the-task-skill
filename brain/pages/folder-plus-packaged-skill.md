---
id: folder-plus-packaged-skill
title: Ship both the skill folder and a packaged .skill zip
category: decision
status: active
tags: [distribution, packaging]
created: "2026-09-18T18:01:23"
updated: "2026-09-18T18:01:42"
---

<!-- compiled_truth -->
The skill ships as a plain folder and as a packaged .skill zip; the two copies must be kept in sync by hand.

## Decision

The skill is distributed two ways from the same repository:

1. the plain `drive-the-task/` folder, which users copy into a personal or project `.claude/skills/` directory, either directly or after cloning;
2. `drive-the-task.skill`, a zip of that folder, for Claude Code clients that offer a "Save skill" action.

The README gives three install methods (copy, clone then copy, packaged file) and a check: start a new conversation and confirm the skill is listed under `/`.

## Alternatives considered

- **Folder only.** Works everywhere but misses one-click install where the client supports it.
- **Package only.** Not every client can open a `.skill` file, so the README makes the folder the method that "works everywhere".

## Rationale

Maximum reach with minimal tooling: one repo, no build system, two install paths (inferred from the README's framing of the methods).

## Blast radius and risk

- The folder and the zip are two copies of the same content. They matched when this page was written (both held `SKILL.md` and `resources/worked-example.md`, byte-identical). The repo has no build script, so **every edit to the folder needs the zip rebuilt and committed with it**, or the two install paths drift apart (inferred risk).
- Skills load at session start, so any install or update needs a fresh conversation.


## Timeline

- time: 2026-09-18T18:01:23
  kind: decision
  summary: "Created this page: Ship both the skill folder and a packaged .skill zip"
  source: "README.md, file list"
  affects: [folder-plus-packaged-skill]

- time: 2026-09-18T18:01:24
  kind: decision
  summary: Seeded from repository contents during brain bootstrap
  source: "README.md, drive-the-task/, git log"
  affects: [folder-plus-packaged-skill]

- time: 2026-09-18T18:01:42
  kind: decision
  summary: Added a one-line lead summary for the index
  source: brain update-truth
  affects: [folder-plus-packaged-skill]
