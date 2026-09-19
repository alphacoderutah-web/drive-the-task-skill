---
id: one-action-at-a-time
title: "Ask for one action in the moment; numbered steps and a recap every response"
category: decision
status: active
tags: [wording, ux]
created: "2026-09-18T18:01:23"
updated: "2026-09-18T18:01:42"
---

<!-- compiled_truth -->
Ask for one action at the moment it is needed, in numbered one-action steps, and end every response with a recap of the user's actions.

## Decision

When Claude needs the user, it asks for **one action, at the moment it is needed**, never a list of upcoming demands. Every instruction follows fixed wording rules:

- every action is numbered and never buried in a paragraph;
- one action per step (a step containing "and" is probably two);
- name the exact field label, button text or file;
- say what happens next, so the user knows whether it worked;
- **end every response with a numbered recap of only what the user must do**, even on short replies. Findings and reasoning go in the middle, never mixed into the steps.

Up front, once, Claude may say which fields it cannot fill, so the user knows a gate is coming without receiving the whole list.

## Alternatives considered

- **Front-load everything** ("here is everything you'll need for the rest of the run so you can get it ready"). Rejected. The user cannot act on step four while looking at step one, and a list of upcoming demands reads as homework.

## Rationale

The worked example records the near-miss. At the first login gate the temptation was to list every future need (login, phone, contact, banking, signatures). The skill calls that the checklist failure in a new costume. The run succeeded because each stop was a single instruction followed by silence until it was done.

## Blast radius

Governs all user-facing wording while the skill is active, not only browser steps. The skill's frontmatter description names the wording rules as a trigger of their own. Statute citations, form numbers and internal jargon belong in supporting files, not in the instruction.

Related: [[checklist-is-the-fallback]], [[gate-taxonomy]].


## Timeline

- time: 2026-09-18T18:01:23
  kind: decision
  summary: "Created this page: Ask for one action in the moment; numbered steps and a recap every response"
  source: "drive-the-task/SKILL.md, resources/worked-example.md"
  affects: [one-action-at-a-time]

- time: 2026-09-18T18:01:24
  kind: decision
  summary: Seeded from repository contents during brain bootstrap
  source: "README.md, drive-the-task/, git log"
  affects: [one-action-at-a-time]

- time: 2026-09-18T18:01:42
  kind: decision
  summary: Added a one-line lead summary for the index
  source: brain update-truth
  affects: [one-action-at-a-time]
