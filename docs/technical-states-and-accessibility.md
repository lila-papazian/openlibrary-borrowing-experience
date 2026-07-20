---
sidebar_position: 3
---

# Technical States & Accessibility Notes

| | |
|---|---|
| Status | Documented, not wireframed |
| Date | 2026-07-19 |
| Purpose | Extends [Content & State Model](./content-state-model.md) with states that came up while prepping for interviews, not from the original research pass |
| Scope note | Documented at the same level of detail as the 6 existing states, but deliberately not taken to Figma — wireframing these now would re-open a scope I already cut once. |

## Part 1 — Technical Cross-Cutting States

Like State 6 (Loan Limit Reached), these aren't properties of the book. They're system or session conditions that can interrupt any of the 6 book-level states, not states a book "is in."

### 1. Not Logged In

| | |
|---|---|
| **Answers** | "Why is it asking me to sign in?" |
| **Label** | Sign in to borrow |
| **Copy** | "You'll need a free account to borrow books. Sign in or create one — it takes a minute." |
| **Visual** | Neutral, no warning tone — this is an expected step, not an error. |
| **Primary action** | Sign in / Sign up |
| **Resolves** | A real gap: every state in the original model assumed the user was already logged in. The actual Open Library header shows "Log In / Sign Up" as persistent nav, so this is a normal step, not an edge case. |
| **Open question** | Does this gate happen before the user even picks a state, or only at the click on Borrow/Join Waitlist? Changes where it sits in the flow. Not confirmed. |

### 2. Connection Error

| | |
|---|---|
| **Answers** | "Why isn't anything working?" |
| **Label** | Something went wrong |
| **Copy** | "We couldn't reach Open Library. Check your connection and try again." |
| **Visual** | Warning tone — different from States 3/5, where nothing's actually broken. |
| **Primary action** | Retry |
| **Resolves** | This isn't hypothetical — the Borrow flow genuinely went down during my usability walkthrough. This state just writes down something that already happened during this project's own research. |

### 3. Loading / Verifying Availability

| | |
|---|---|
| **Answers** | "Did anything happen when I tapped the button?" |
| **Label** | None needed — just a visual loading state on the button |
| **Copy** | None — brief enough to skip, but the button has to visibly change (spinner, or disabled+dimmed) the instant it's tapped. |
| **Visual** | Button goes busy, disabled to block double-submission. |
| **Resolves** | Without this, a slow response reads as "nothing happened," and the obvious reaction is a second tap — which risks a duplicate borrow. Protects States 2 and 4, which both end in a real transaction. |

### 4. Timeout (request sent, no confirmation)

| | |
|---|---|
| **Answers** | "Do I have the book or not?" |
| **Label** | We're not sure if that went through |
| **Copy** | "Your request may not have completed. Check My Loans before trying again — borrowing twice by mistake won't cause harm, but let's make sure first." |
| **Visual** | Warning tone. |
| **Primary action** | Check My Loans |
| **Secondary action** | Try again |
| **Resolves** | Different from Connection Error — here the request actually went out, so retrying blind risks a duplicate against the 10-book limit (State 6). This is the one state where bad copy could create a new problem instead of just being unclear. Worth more weight than it looks like it deserves. |

## Part 2 — Accessibility Notes (apply to the 6 existing states)

Not new states. These are requirements that cut across States 1–6 as already written — listing them as a 7th state would repeat the exact mistake I already fixed once, treating a cross-cutting concern like it belonged in the same list as book-availability states.

- **State changes need to be announced to screen readers.** When the CTA panel updates — after a failed borrow, or Loading resolving into Unavailable — that needs an `aria-live` region, or a screen reader user has no way to know the button's meaning just changed under them.
- **Focus can't get orphaned.** If a button becomes disabled (States 3, 5) or gets replaced by different content, focus needs to land somewhere sensible, not silently drop to the document body.
- **Color is never the only signal.** The tone dots (green/grey/amber) already always pair with text in every state built so far. Worth keeping as a documented rule, not an accident of how they happened to get written.
- **Contrast needs an actual check**, not an assumption. States 3 and 5 use muted grey on purpose to read as lower priority — that needs to pass WCAG AA against Open Library's real `--grey` / `--dark-grey` values (see `src/tokens/colors.css` in the prototype), not just eyeballed.
- **Touch targets** — the button and the "Locate at another library" link both need real tap area on mobile, not just readable text.

## What this doc doesn't do

- No wireframes for the 4 technical states — text only, same format as the content model.
- No prototype implementation — documented as known, scoped-out work, not built.
- No claim of a full accessibility audit — these are the specific risks for this flow, not a general checklist.
