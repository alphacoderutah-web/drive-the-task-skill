---
slug: flow
title: Key flows
role: key flows
updated: "2026-09-18T18:01:24"
---

# Key flows

## End-to-end path of a typical request

A typical run is a portal application. Claude prepares, drives until the first gate, asks for one action, resumes, and records the outcome.

```mermaid
sequenceDiagram
  participant U as User
  participant C as Claude (skill active)
  participant P as Portal / form
  U->>C: Task behind a login or form
  C->>C: Gather every value from project records first
  C-->>U: Say once, up front, which fields only the user can fill
  C->>P: Open portal
  P-->>C: Login page (gate)
  C-->>U: One instruction: sign in here
  U->>P: Signs in
  C->>P: Check dashboard for saved or existing applications
  loop Every page
    C->>P: Fill non-sensitive fields, Save and Continue
  end
  P-->>C: Page needs a gate value (bank details, signature)
  C-->>U: HUMAN APPROVAL REQUIRED block + a single instruction
  U->>P: Performs that one action
  C->>P: Checks the page shows no errors, continues
  P-->>C: Final Submit (certification gate)
  C-->>U: Explain what is being certified, then one instruction
  U->>P: Clicks Submit
  C->>C: Record confirmation number, date/time, approvals, what is awaited
  C-->>U: Plain report of what happened + numbered recap of user actions
```

## Other important flows

- **Session timeout mid-flow.** Say plainly which pages saved and which did not, get the user signed back in, confirm that each completed page actually persisted, and refill whatever did not.
- **Field won't take a value.** Use the accessibility tree before clicking at coordinates. Custom dropdowns usually need the option clicked, not typed.
- **Page looks wrong.** Take a screenshot and read the page before acting. Never click Submit to "see what happens".
- **Install.** Copy the folder into a skills directory, clone then copy, or use the `.skill` package. Then start a new conversation and check that the skill appears under `/`. See [[folder-plus-packaged-skill]].
