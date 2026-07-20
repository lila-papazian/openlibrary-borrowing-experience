---
sidebar_position: 3
---

# Sources

Real, linkable evidence for the pain points in [User Research Findings](./user-research-findings.md).

| Status | Partial — GitHub issues verified, Reddit not substantiated |
|--------|-----|
| Last Updated | 2026-07-18 |

## Why this exists

An early version of the research listed "Reddit discussions" as a source without any links or quotes. I couldn't find those threads again on review. This doc replaces that with sources that actually check out.

## Verified Sources

### Official Documentation

- **Official FAQ** — [openlibrary.org/help/faq/borrow](https://openlibrary.org/help/faq/borrow): confirms the waitlist mechanism (email + 24hr claim window), that Borrow isn't the only access path (Listen/audio exists too), and — in its "not in a readable format" entry — that a book with no readable option isn't necessarily gone, might just not be digitized yet. Note: this page still mentions Adobe Digital Editions and looks outdated on the DRM side — see below.
- **Official help center (more current)** — [help.archive.org — Borrowing From The Lending Library](https://help.archive.org/help/borrowing-from-the-lending-library/): confirms loan type (1 hour vs. 14 days) is fixed per book, not chosen by the user, and that it decides what you can actually do with the book (1hr = browser only; 14 days = browser or download via LCP reader — Thorium, Cantook). Describes the current LCP-based system, replacing the Adobe one from the older FAQ.

### My Own Usability Walkthrough (strongest evidence here)

Direct testing of openlibrary.org, 2026-07-18. Stronger than any secondhand report — it's not an interpretation of someone else's complaint, it's the actual interface.

- **Search results screenshot** ("harry potter"): confirms a "Readable Only" filter exists in the product today, separate from general search — backs up treating "Read Online" as its own state (see [Content & State Model](../content-state-model.md)).
- **Book page screenshot** (*Harry Potter and the Half-Blood Prince*): confirms the Borrow button has no visible loan-type choice — the dropdown next to it shows "Listen" and "Locate," not a 1hr/14-day picker.
- **Reproduced directly:** clicked Borrow on a real book, got a new tab immediately with no indication of whether it was a 1-hour or 14-day loan. Not a hypothesis — this is the actual bug.

### GitHub Issues — internetarchive/openlibrary

The product's own public issue tracker. Stronger than forum complaints, since these are problems the team itself logged or got asked to fix.

**Unclear availability status**
- [#1754 — Search results should clearly identify unavailable books](https://github.com/internetarchive/openlibrary/issues/1754)
- [#12826 — Design: Consolidate book page left sidebar into a single CTA card](https://github.com/internetarchive/openlibrary/issues/12826)
- [#684 — Canonical Books Pages: Merging Works + Editions UI](https://github.com/internetarchive/openlibrary/issues/684) — relevant to edition ambiguity during Discover/Evaluate.

**Waitlist / borrowing restriction friction**
- [#648 — Give readers on waitlist an estimate when book will be available](https://github.com/internetarchive/openlibrary/issues/648)
- [#2938 — Add wait time to loans page](https://github.com/internetarchive/openlibrary/issues/2938)
- [#12025 — Does Open Library have a Waitlist feature?](https://github.com/internetarchive/openlibrary/issues/12025) — someone filed this as a question, which is itself evidence the feature isn't discoverable.
- [#439 — Graceful error should occur when user w/ MAX LOANS attempts borrow](https://github.com/internetarchive/openlibrary/issues/439) — the 10-book limit is confirmed in the [help center](https://help.archive.org/help/borrowing-from-the-lending-library/); this one now has its own state (State 6) instead of just backing up other states.

**Workflow difficult to understand**
- [#2066 — Improve Effectiveness of Help & Support Flow: Reduce Unnecessary Support Emails](https://github.com/internetarchive/openlibrary/issues/2066) — implies a real volume of confused support requests tied to borrowing.

### Other sources

- **[Jessamyn West — "Things That Make the Librarian Angry" (Medium)](https://medium.com/tilty/things-that-make-the-librarian-angry-1d30cd27cf60)** — a librarian's account of the friction moving a borrowed book onto a device via Adobe DRM. Backs the E-reader Integration pain point with a real, named source.
- **[Goodreads — "Pick-a-Shelf" discussion thread](https://www.goodreads.com/topic/show/20963569-buddy-reads?page=3)** — readers discussing uncertainty about how the lending model actually works. Backs Insight 1 ("readers think about access, not lending models").

## Not yet substantiated

- The Reddit discussions from an earlier draft couldn't be located. Don't cite them until real threads are found and linked here.

## Closed, not pursuing

- Device compatibility and digital quality pain points are out of scope for this phase (see [Scope Decision](./user-research-findings.md#scope-decision-2026-07-18)). Their evidence stays as-is — one Medium source, no verified GitHub issues — and I'm not chasing more right now.
