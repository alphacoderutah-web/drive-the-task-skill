# Worked example — Florida DOR registration, 2026-08-14

A real end-to-end run. Roughly 20 pages of a state tax portal, submitted successfully.
Kept here because the shape of it is more instructive than the rules alone.

## What the task was

Register a Jacksonville rental property with the Florida Department of Revenue so a sales
tax number could be issued — the number that gates a state vacation-rental licence
application, which in turn gates two county tax accounts.

## The division of labour

**Claude did:** opened the portal, checked the dashboard for an existing in-progress
application (there was none — but there were five completed ones, one of which confirmed
the correct "reason for applying"), started the application, and filled every page:
reason, dates, business partner number, legal name, addresses, NAICS, business activity
checkboxes, seasonal flags, contact details, enrolment options, and every "Save & Continue"
between them.

**The user did:** logged in, supplied a phone number, named the payment contact, typed the
bank routing and account numbers, typed two signatures, and clicked Submit.

**Six stops across twenty pages.** Each one a single instruction.

## Things that went right, and why

**Checked the dashboard before starting.** Five completed applications were listed. One
was "Additional Florida Rental Property" for a sister entity — which independently
confirmed the reason-for-applying selection was correct. Two minutes of looking replaced a
guess.

**Caught a wrong default.** The portal pre-selected a county control reporting number that
would have merged this property's return into an unrelated account. Reading the page
rather than accepting defaults caught it.

**Session timed out mid-flow.** Page 1 had saved, page 2 had not. The recovery was: say
plainly what survived, get them logged back in, verify each page persisted, refill the one
that hadn't. No drama, no lost work, no pretending it didn't happen.

**Handled banking without touching it.** The user typed the routing and account numbers.
Claude looked at the page only to confirm the bank name resolved and there were no
validation errors, then continued. Those numbers were never transcribed into a file,
a log, or a message — verified afterwards with a project-wide grep.

**Stopped hard at both signatures.** The enrolment agreement authorised ACH debits against
a business account; the final declaration was sworn under penalty of perjury. Both got a
plain-language explanation of what was being certified, then a single instruction, then
silence until done.

## Things worth copying

1. **Look for saved state before creating new state.**
2. **Read what already exists** — it often answers a question you were about to guess at.
3. **Explain what a signature actually commits them to**, in plain words, before asking for
   it. "This gives the State standing permission to pull money from that account" is more
   useful than quoting the clause.
4. **After submission, capture the confirmation number immediately** and record what is now
   being waited on and until when.
5. **Read the confirmation page properly.** This one revealed two facts that changed the
   schedule: the certificate arrives by post in 7–10 days despite email authorisation
   having been given, and confirmations go to a different address than the one entered on
   the form. Both would have caused a silent wait.

## The one thing that nearly went wrong

The temptation, at the point where the login was needed, was to write out everything the
user would need for the rest of the run — login, phone, contact, banking, signatures — so
they could "get it all ready".

That would have been the checklist failure in a new costume. They cannot act on the
banking screen while looking at the login screen, and a list of five upcoming demands
reads as work rather than help.

**One thing, in the moment, every time.**
