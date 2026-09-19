---
id: gate-taxonomy
title: "Gates: the closed list of points where Claude stops for the user"
category: concept
status: active
tags: [gates, credentials]
created: "2026-09-18T18:01:23"
updated: "2026-09-18T18:01:42"
---

<!-- compiled_truth -->
A closed list of gates where Claude stops for one user action; everything else it does without asking, and gate values are never transcribed.

## Definition

A **gate** is a point in a driven task where Claude must stop and hand one action to the user. The skill keeps a closed list, and everything outside it is Claude's to do without asking:

| Gate | Reason it stops |
|---|---|
| Usernames, passwords, MFA codes, CAPTCHA | Never handled by Claude |
| Creating an account | Never done on the user's behalf |
| Tax IDs, social security numbers, card numbers, bank routing and account numbers | Never typed, never stored |
| Signing, attesting, swearing under oath | A legal act by a person |
| Clicking Submit on a government application | Carries a certification |
| Paying any fee | Irreversible; spends the user's money |
| Sending an email or message | Outbound communication |
| Accepting terms, consents, authorisations | Binds the user |
| A fact only the user knows | For example a contact detail, a go-live date or a title |

At a gate Claude prints a fixed **HUMAN APPROVAL REQUIRED** block giving the action, where it happens, the verbatim attestation text if there is one, and the amount if there is a fee. It then gives a single instruction.

## Why it is this way

A closed list makes the boundary predictable in both directions. Claude never does something only the user may do, and it never stops for ordinary navigation. The worked example shows the payoff: six stops across roughly twenty portal pages.

## Credential discipline (part of the same boundary)

Values behind the identity and finance gates are never written into any file, log, report or message, including files Claude generates. Claude may *look at* a page showing such a value in order to continue safely, for example to confirm that a bank name resolved and no validation errors appeared. It does not transcribe the value afterwards. The skill recommends grepping the project once the task is done to confirm nothing leaked.

## Boundaries and counter-examples

- **Not a gate:** navigating, typing an address, ticking a checkbox that follows from data Claude already holds, clicking "Save & Continue" between pages.
- **Is a gate even though it is only a click:** the final Submit on a government application, because it certifies.
- **Explain before a signature.** Say in plain words what the signature commits the user to, for example standing permission to debit an account, rather than quoting the clause.

Related: [[checklist-is-the-fallback]], [[one-action-at-a-time]].


## Timeline

- time: 2026-09-18T18:01:23
  kind: decision
  summary: "Created this page: Gates: the closed list of points where Claude stops for the user"
  source: drive-the-task/SKILL.md
  affects: [gate-taxonomy]

- time: 2026-09-18T18:01:24
  kind: decision
  summary: Seeded from repository contents during brain bootstrap
  source: "README.md, drive-the-task/, git log"
  affects: [gate-taxonomy]

- time: 2026-09-18T18:01:42
  kind: decision
  summary: Added a one-line lead summary for the index
  source: brain update-truth
  affects: [gate-taxonomy]
