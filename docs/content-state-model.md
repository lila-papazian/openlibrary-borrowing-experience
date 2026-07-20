---
sidebar_position: 2
---

# Decision: Content & State Model — Borrowing Flow

| | |
|---|---|
| Status | Draft |
| Date | 2026-07-18 |
| Scope | Discover → Evaluate → Borrow (see [Scope Decision](./01-research/user-research-findings.md#scope-decision-2026-07-18)) |
| Input | [Borrowing Decision Flow](./01-research/research.md#borrowing-decision-flow) |
| Figma | [Wireframes — 6 states](https://www.figma.com/design/8QroAtJwgeudlAZjlAXGuj/OpenLibrary-Borrowing-%E2%80%94-Wireframes?node-id=0-1&t=ilVx1UvN5G4P6K8B-1) |

> Note: this file lives flat at `docs/content-state-model.md` for now. When `03-decisions/` gets created (still a deferred TODO), move it there and fix the two `01-research/` links above.

## Purpose

The Borrowing Decision Flow in `research.md` is system logic — Borrowable? → Loan Type → Available? It doesn't say what the user actually sees. This doc assigns real content (label, copy, visual, action) to every terminal state in that flow.

Every state below maps to one of the two in-scope pain points: unclear availability, or borrowing workflow confusion. Nothing here is new functionality, just clearer content for what already exists.

## Two things this model depends on

- **Loan type (1 hour vs. 14 days) is fixed per book, not something the user picks.** Confirmed via [help.archive.org](https://help.archive.org/help/borrowing-from-the-lending-library/), and confirmed the hard way — clicking Borrow on a real book opened a new tab with zero indication of which type applied. That matters because loan type decides whether you can only read in-browser (1hr) or also download (14 days). Full story in the [Decision Log](./decision-log.md#2026-07-18--resolved-is-loan-type-a-user-choice).
- **"Not Digitized" and "Read Online" are different states, not the same one.** An earlier version of this doc had them collapsed together. Open Library's FAQ reassures users that a non-readable book "doesn't mean something is wrong" — which told me this confusion is common enough that they wrote a whole FAQ entry about it. Split them. See the [Decision Log](./decision-log.md#2026-07-18--not-digitized-split-from-read-online) for the full story.

## States

### 1. Read Online (not borrowable)

Open question, still unresolved: this state assumes "read online" means no loan at all. I don't think that's right. The docs describe 1-hour renewable loans as the default mechanism, which means "Read Online" might just be a 1-hour loan running automatically — against the same limited copy pool as anything else. If so, it can run out.

If it does run out, don't invent new copy for that — reuse State 3's pattern (same icon, same "all copies checked out, no waitlist" reasoning). It's the same underlying mechanism, so it should read the same way.

Still need to verify whether some books are genuinely copy-unlimited (true open access, no CDL) as opposed to just an auto-borrowed 1-hour loan. A real test would be opening two sessions on the same "Readable" book and seeing if the second one ever gets blocked. Until then, treat every "Read Online" label as a loan in disguise, not guaranteed access.

| | |
|---|---|
| **Answers** | "Can I read this?" |
| **Label** | Read Online |
| **Copy** | "Read this book in your browser now." (Dropped "No borrowing needed" from an earlier draft — can't verify that claim, and it might be false.) |
| **Visual** | Green, open-book icon. Falls back to State 3's gray/lock treatment if copies run out. |
| **Primary action** | Read Online |
| **Resolves** | Pain Point #1 — one label for "preview only" and "read online" instead of the raw catalog state. Doesn't cover catalog-only/not-digitized — that's State 5. Open Library's own "Readable Only" search filter (208 results for "harry potter") backs this up: the product already treats it as a distinct, filterable state. |

### 2. Borrow Available

| | |
|---|---|
| **Answers** | "Can I borrow this? For how long?" |
| **Label** | Borrow for [X] |
| **Copy** | "Available now. You'll have it for [1 hour / 14 days]." Loan length is always stated, never assumed obvious. |
| **Visual** | Green, clock or book icon depending on loan type. |
| **Primary action** | Borrow Now |
| **Resolves** | Pain Point #5. I confirmed this one myself: clicking Borrow on a real book opened a new tab with no loan-type info, even though that info determines whether the book is browser-only or downloadable (see [the fact above](#two-things-this-model-depends-on)). Also answers GitHub [#439](https://github.com/internetarchive/openlibrary/issues/439), which flags that loan limits get discovered after the fact, not before. |

### 3. Borrow Unavailable (no waitlist path)

| | |
|---|---|
| **Answers** | "Why can't I access it?" |
| **Label** | Currently Unavailable |
| **Copy** | "All copies are checked out right now. This edition only offers 1-hour loans, which don't have a waitlist." States the cause and why there's no waitlist, instead of a dead-end button with no explanation. |
| **Visual** | Gray, lock icon. |
| **Primary action** | None — there's genuinely nothing to do here. |
| **Secondary action** | Locate at another library (WorldCat). Already exists on the real book page, just buried in the sidebar — should surface earlier. |
| **Resolves** | Pain Point #1. Answers GitHub [#1754](https://github.com/internetarchive/openlibrary/issues/1754) ("search results should clearly identify unavailable books") by naming the reason instead of just hiding the button. |

### 4. Join Waitlist

| | |
|---|---|
| **Answers** | "When will I be able to read it?" |
| **Label** | Join Waitlist |
| **Copy** | "[N] people ahead of you. Estimated wait: [X days]. We'll email you when it's your turn — you'll have 24 hours to check it out before it passes to the next person." |
| **Visual** | Yellow, queue icon. |
| **Primary action** | Join Waitlist |
| **Secondary action** | Leave Waitlist. Not "Notify me" — per the FAQ, email notification is already automatic once you join, so a separate opt-in would just be confusing. |
| **Resolves** | Pain Point #2, and three GitHub issues at once: [#648](https://github.com/internetarchive/openlibrary/issues/648) (no wait estimate), [#2938](https://github.com/internetarchive/openlibrary/issues/2938) (add wait time to loans page), [#12025](https://github.com/internetarchive/openlibrary/issues/12025) (people don't know the waitlist exists). Email + 24hr window comes straight from the [official FAQ](https://openlibrary.org/help/faq/borrow). |

### 5. Not Digitized

| | |
|---|---|
| **Answers** | "Why can't I read or borrow it?" |
| **Label** | Not available digitally |
| **Copy** | "This book hasn't been digitized yet — nothing's wrong on your end." Echoes the FAQ's own reassuring tone on purpose, since that's exactly what people are worried about when they hit this. |
| **Visual** | Gray, book-off icon — deliberately different from State 3's lock, since the cause isn't the same (doesn't exist vs. checked out). |
| **Primary action** | None — nothing's in progress to wait for. |
| **Secondary action** | Locate at another library (WorldCat), same as State 3. |
| **Resolves** | Pain Point #1, specifically the FAQ's own "found a book but it isn't readable" entry — evidence this confusion comes up often enough that Open Library felt they had to address it directly. |

### 6. Loan Limit Reached (account-level, not book-level)

This one's different from the other five — it's not a property of the book, it's a property of the account, and it can interrupt a borrow attempt on any book, including one that's otherwise in State 2. It fires at the click, not on page load.

| | |
|---|---|
| **Answers** | "Why can't I borrow this if the book is available?" |
| **Label** | Loan limit reached |
| **Copy** | "You already have 10 books borrowed — the most you can have at once. Return one to borrow this one." |
| **Visual** | Amber, warning icon — unlike States 3/5, something actually needs the user's attention here. |
| **Primary action** | View my loans |
| **Resolves** | GitHub [#439](https://github.com/internetarchive/openlibrary/issues/439) — I'd cited this earlier just as supporting evidence for State 2, but it deserves its own state. 10-book limit confirmed in the [help center](https://help.archive.org/help/borrowing-from-the-lending-library/). |

Open question: does the loan limit also block joining a waitlist, or only completing an actual borrow? Waitlist entries might not count against the cap since no loan has started. Not confirmed — don't assume either way.

## What this doc doesn't decide

- Visual design (colors, spacing, components) — that's a wireframe decision.
- Device/download mechanics (LCP readers, Thorium, Cantook) — out of scope. Loan type matters here only as something to communicate, not something to redesign.

## Status

All six states have wireframes ([Figma](https://www.figma.com/design/8QroAtJwgeudlAZjlAXGuj/OpenLibrary-Borrowing-%E2%80%94-Wireframes?node-id=0-1&t=ilVx1UvN5G4P6K8B-1)) and a working prototype (React + Vite + Tailwind, real Open Library design tokens). The flowchart in `research.md` matches the Not Digitized / Read Online split.

Not done yet: usability testing with real readers. This model is evidence-backed on the problem side. It hasn't been validated on the solution side.
