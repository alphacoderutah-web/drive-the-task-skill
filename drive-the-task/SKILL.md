---
name: drive-the-task
description: Execute a multi-step task end to end in the browser instead of handing back instructions — log in to portals, fill applications and forms, upload documents, reach the final screen — stopping only at genuine gates (passwords, MFA, signatures, payment, outbound sends, facts only the user knows) and directing the user one action at a time in the moment. Use for government filings, licence and permit applications, tax registrations, account setups, insurance or banking portals, vendor onboarding, form submissions, and any online workflow where the default temptation is to write a checklist. Also governs how instructions are worded — numbered steps, one action each, and a recap at the end of every response.
---

# Drive the task

The user is paying for work to be done, not for instructions on how to do it themselves.

A polished checklist still leaves the entire job on their desk. **Handing over a to-do list
is the fallback when a task genuinely cannot be automated — it is not the deliverable.**

## The loop

1. **Do everything that does not require them.** Open the portal, navigate, select options,
   fill every non-sensitive field, upload prepared documents, reach the final screen.
2. **Stop at the first thing that genuinely needs them.** Leave the browser open on that
   exact page.
3. **Ask for one thing.** Name the field, say what to type or click. Nothing else.
4. **Resume the moment they've done it.** Continue to the next stop.
5. Repeat until finished or blocked at a hard gate.

The failure mode this exists to prevent: front-loading a list of five things they'll need
later. They cannot act on step 4 while looking at step 1, and a long list reads as
homework. **One thing, in the moment.**

## What stops, and what does not

Stop only for these. Everything else is yours to do.

| Gate | Why |
|---|---|
| Usernames, passwords, MFA codes, CAPTCHA | Never handled |
| Creating an account | Never done on their behalf |
| FEIN, SSN, card numbers, bank routing/account | Never typed, never stored |
| Signing, attesting, swearing under oath | A legal act by a person |
| Clicking Submit on a government application | Carries a certification |
| Paying any fee | Irreversible, spends their money |
| Sending an email or message | Outbound communication |
| Accepting terms, consents, or authorisations | Binds them |
| A fact only they know | A contact's email, a go-live date, a title |

**Do not ask permission to navigate, type an address, tick a checkbox that follows from
data you already hold, or click "Save & Continue" between pages.** Asking about those
turns a driven task back into a checklist with extra steps.

When you hit a gate, print it plainly:

```
HUMAN APPROVAL REQUIRED
Action:      <exact action>
Where:       <portal / page>
You are certifying: <verbatim text of the attestation, if any>
Amount:      <fee, if any>
```

Then give the single instruction.

## How to word instructions

This is not optional polish. Badly structured instructions waste the work.

- **Number every action.** Never bury an action inside a paragraph.
- **One action per step.** If a step contains "and", it is probably two steps.
- **Name the exact thing** — the field label, the button text, the file path, the address.
  Not "send the zoning email" but "open `EMAILS-TO-SEND.md`, copy Email 1, send to
  `RMullaly@coj.net`".
- **Say what happens next**, so they know whether it worked.
- **End every response with a numbered recap of only what they must do.** Mandatory,
  including on short replies. Findings and reasoning go in the middle, never mixed into
  the steps.

Write for an intelligent non-specialist. Statute citations, form numbers and internal
jargon belong in the supporting files, not in the instruction.

## Before you start driving

1. **Look for saved state first.** Most portals save partial work. Check the dashboard for
   an in-progress application before starting a new one — duplicates are painful to unwind.
2. **Check what already exists.** An existing account, licence or registration changes
   which form applies. Search before you file.
3. **Have the data ready.** Assemble every value you'll need from project records first, so
   you're not stopping mid-flow for something you could have looked up.
4. **Know which fields you cannot fill**, and say so up front — once — so the user knows a
   gate is coming without being handed the whole list.

## When it breaks

- **Session timeout mid-flow.** Common on government portals. Don't panic the user. Say
  what saved and what didn't, get them logged back in, then verify each completed page
  actually persisted before continuing.
- **A field won't take a value.** Try the accessibility tree (`find`, `read_page`) before
  clicking blind at coordinates. Custom dropdowns often need the option clicked, not typed.
- **A page looks wrong.** Screenshot and read before acting. Never click Submit to "see
  what happens".
- **You cannot verify something.** Say so. Never claim a portal was checked, a form was
  submitted, or a value was confirmed unless it actually was.

## Honesty about what happened

**Never report a task as done when it was only prepared.** "I filled the form and stopped
before Submit" and "I wrote you instructions for the form" are different outcomes. Say
which one happened.

At the end of a driven task, record: what was submitted, the confirmation number, the
date and time, who approved what, and what is now being waited on and until when. If the
project has an audit log, append there. If not, say it plainly in the response.

## Credential discipline

Never write usernames, passwords, MFA codes, FEINs, SSNs, card numbers, or bank
routing/account numbers into any file, log, report, or message — including ones you
generate. If a value is needed on screen, the user types it.

You may look at a page containing such values in order to continue safely. Do not
transcribe them anywhere afterwards. When a task is finished, it is worth grepping the
project to confirm nothing leaked.

## Where this does not apply

Conversational questions, code editing, analysis, and anything with no external system to
drive. This skill is about tasks that live behind a login or a form.
