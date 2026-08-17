# Drive The Task Skill

A Claude Code skill that makes multi-step online tasks **get done rather than described**.
When active, Claude drives a portal or form end to end — logging in, filling applications,
uploading documents, reaching the final screen — and stops only at the points that genuinely
require a person, directing you one action at a time.

The full standard lives in [`drive-the-task/SKILL.md`](drive-the-task/SKILL.md).

## Why it exists

Ask for four tasks to be done and you can easily get back a well-organised list of four
tasks to do yourself. A polished checklist still leaves the entire job on your desk.

This skill treats handing over a to-do list as the *fallback* when a task genuinely cannot
be automated — not as the deliverable.

## What it does

Once installed, Claude will (among other things):

- **Drive, then stop** — open the portal, navigate, fill every non-sensitive field, reach
  the final screen, and stop at the first thing that actually needs you.
- **Ask for one thing at a time** — the exact field and what to type, in the moment. Never
  a list of five things you will hit later.
- **Know what counts as a gate** — passwords, MFA, CAPTCHA, account creation, tax or bank
  identifiers, signatures, Submit on a government application, payments, outbound email,
  and facts only you know. Everything else it just does, without asking permission to
  navigate or tick a box.
- **Say what actually happened** — "I filled the form and stopped before Submit" and "I
  wrote you instructions" are different outcomes, and it never blurs them.
- **Keep credentials off disk** — nothing sensitive is written into any file it generates,
  including its own logs and reports.
- **Recover cleanly** — session timeouts and stuck fields are expected; it verifies what
  actually persisted rather than assuming.

It also governs how instructions are worded: numbered steps, one action each, naming the
exact file, field or button, with a recap of your actions at the end of every response.

## What's included

| Path | What it is |
|---|---|
| `drive-the-task/SKILL.md` | The workflow, the gate taxonomy, wording rules, recovery guidance |
| `drive-the-task/resources/worked-example.md` | A real twenty-page state tax portal run, start to finish, including the moment it nearly reverted to handing over a checklist |

## Install

Pick whichever method fits your Claude Code client.

### Method 1 — Copy the skill folder (works everywhere)

Copy the `drive-the-task/` folder into your personal skills directory:

- **Windows:** `C:\Users\<you>\.claude\skills\drive-the-task\`
- **macOS / Linux:** `~/.claude/skills/drive-the-task/`

The result should be `…/.claude/skills/drive-the-task/SKILL.md`. Then open a **new** Claude
Code conversation — skills load at session start, so an already-open session won't see it
until you start a fresh one.

To install it for a single project instead of globally, copy the folder into that project's
`.claude/skills/` directory rather than your home directory.

### Method 2 — Clone this repo, then copy

```bash
git clone https://github.com/<owner>/drive-the-task-skill.git
```

Then copy the `drive-the-task` folder from the clone into `.claude/skills/` as described in
Method 1.

### Method 3 — The packaged `.skill` file

This repo also includes `drive-the-task.skill` (a zip package of the skill). If your Claude
Code client shows a **Save skill** action when you open a `.skill` file, you can use that to
install it directly. If not, use Method 1.

## Use

In a new conversation, the skill triggers **automatically** when you begin a task behind a
login or a form — a government filing, a licence application, a tax registration, an
account setup. You can also invoke it explicitly:

```
/drive-the-task
```

If Claude ever hands you a checklist for work it could have performed, say **"drive it"** —
that is the correction.

## Verify it loaded

Start a new conversation and type `/` — `drive-the-task` should appear in the skills list.
That confirms it installed correctly.

## Scope

Built for tasks that live behind a login or a form. Not for conversation, analysis, or code
— there is no external system to drive.

Pairs well with [`agency-conduct`](https://github.com/alphacoderutah-web/agency-conduct-skill),
which sets the broader operating standard for autonomous engineering work.
