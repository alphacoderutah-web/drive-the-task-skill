---
id: prepared-is-not-done
title: "Never report prepared as done; record the outcome of every driven task"
category: decision
status: active
tags: [honesty, records]
created: "2026-09-18T18:01:23"
updated: "2026-09-18T18:01:42"
---

<!-- compiled_truth -->
Reports say exactly what happened (prepared, submitted or blocked), and every driven task ends with a recorded outcome.

## Decision

Claude never reports a task as done when it was only prepared. "I filled the form and stopped before Submit" and "I wrote you instructions for the form" are different outcomes, and the report must say which one happened. Claude also never claims a portal was checked, a form submitted or a value confirmed unless that actually happened.

At the end of a driven task Claude records what was submitted, the confirmation number, the date and time, who approved what, and what is now being waited on and until when. The record goes in the project's audit log if it has one, and otherwise into the response itself.

## Rationale

- A driven task can end in several states (prepared, submitted, blocked at a gate). Blurring them hides work that is still open.
- The worked example shows why the confirmation page must be read properly. It revealed that the certificate would arrive by post rather than electronically, and that confirmations would go to a different address from the one entered. Both would otherwise have meant waiting without knowing why.

## Related recovery rule

After a session timeout, verify that each completed page actually persisted before continuing, rather than assuming it did. The worked example had one page saved and the next lost.

Related: [[checklist-is-the-fallback]], [[gate-taxonomy]].


## Timeline

- time: 2026-09-18T18:01:23
  kind: decision
  summary: "Created this page: Never report prepared as done; record the outcome of every driven task"
  source: "drive-the-task/SKILL.md, resources/worked-example.md"
  affects: [prepared-is-not-done]

- time: 2026-09-18T18:01:24
  kind: decision
  summary: Seeded from repository contents during brain bootstrap
  source: "README.md, drive-the-task/, git log"
  affects: [prepared-is-not-done]

- time: 2026-09-18T18:01:42
  kind: decision
  summary: Added a one-line lead summary for the index
  source: brain update-truth
  affects: [prepared-is-not-done]
