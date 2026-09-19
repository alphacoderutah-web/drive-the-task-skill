---
id: checklist-is-the-fallback
title: "Drive the task; a checklist is only the fallback"
category: decision
status: active
tags: [core, premise]
created: "2026-09-18T18:01:23"
updated: "2026-09-18T18:01:42"
---

<!-- compiled_truth -->
The deliverable is the task performed in the browser; a checklist for the user is only the fallback.

## Decision

For any task behind a login or a form, the deliverable is the **task performed**, not instructions for performing it. A checklist for the user is the fallback, used only when a step genuinely cannot be automated. This is the premise the whole skill rests on.

## Alternatives considered

- **Return a clear, well-organised checklist.** This is the default the skill argues against. It looks helpful but leaves the whole job with the user.
- **Ask permission at each step.** The skill rejects this explicitly. Asking before navigating, ticking a checkbox that follows from known data, or clicking "Save & Continue" turns a driven task back into a checklist with extra steps.

## Rationale

The first commit says the skill was written after a run where four tasks that could have been performed came back as a list. The README repeats that framing. The user is paying for work to be done, and a polished checklist still leaves all of it with them.

## Blast radius

- Defines the loop in `SKILL.md`: do everything that doesn't need the user, stop at the first real gate, ask for one thing, resume.
- Sets the user-facing correction: saying **"drive it"** when Claude hands back a checklist it could have performed.
- Bounded by [[gate-taxonomy]], which lists what still stops, and shaped by [[one-action-at-a-time]], which says how the stops are communicated.


## Timeline

- time: 2026-09-18T18:01:23
  kind: decision
  summary: "Created this page: Drive the task; a checklist is only the fallback"
  source: "README.md, drive-the-task/SKILL.md, git log"
  affects: [checklist-is-the-fallback]

- time: 2026-09-18T18:01:23
  kind: decision
  summary: Seeded from repository contents during brain bootstrap
  source: "README.md, drive-the-task/, git log"
  affects: [checklist-is-the-fallback]

- time: 2026-09-18T18:01:42
  kind: decision
  summary: Added a one-line lead summary for the index
  source: brain update-truth
  affects: [checklist-is-the-fallback]
