---
slug: background
title: Project background
role: project background
updated: "2026-09-18T18:01:24"
---

# Project background

## Why

Asked to carry out several online tasks, an assistant can easily return a well-organised list of those same tasks for the user to do. That leaves the whole job with the user. This skill exists to change the default: when a task lives behind a login or a form, Claude does the work in the browser and only hands over the steps that genuinely need a person. The first commit says it was written right after such a run, where four tasks that could have been performed came back as a checklist.

## Goals

- Tasks behind a portal or form get **done, not described**: Claude navigates, fills every non-sensitive field, uploads prepared documents and reaches the final screen.
- The user is interrupted only at genuine gates (see [[gate-taxonomy]]), and then for **one action at a time** (see [[one-action-at-a-time]]).
- What Claude reports matches what actually happened. "Prepared" is never reported as "done" (see [[prepared-is-not-done]]).
- Sensitive values never end up in any file, log or message Claude writes.

No measurable success criteria are written down in the repo. **Open question:** is there a target, such as the number of stops per task or checklist hand-backs avoided, or an eval set?

## Non-goals

- Conversation, analysis and code editing. There is no external system to drive, so the skill says it does not apply.
- Handling anything that is legally or financially the user's own act: credentials, signatures, payments, outbound messages, accepting terms.
- Replacing the broader engineering operating standard. The README points to the companion `agency-conduct` skill for that.

## Target user

Claude Code users who hand Claude online admin work: government filings, licence and permit applications, tax registrations, account setups, insurance or banking portals, vendor onboarding. They want the job finished and are willing to step in briefly at the gates.
