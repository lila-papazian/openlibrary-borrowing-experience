---
sidebar_position: 4
---

# Decision Log

Dated notes on what changed in this project and why, kept separate from the clean docs (`research.md`, `user-research-findings.md`, `content-state-model.md`) so those stay readable without process notes cluttering the middle of them.

The polished version of this is [case-study.md](./case-study.md). This is the raw version it came from.

---

### 2026-07-18 — Scope narrowed to Discover → Evaluate → Borrow

Cut seven candidate pain points down to two — unclear availability and borrowing workflow confusion — the only ones scoring high on both frequency and severity. Everything else (device compatibility, digital quality, personal library management, discovery/management) got parked, not deleted. Still in `user-research-findings.md`, tagged out of scope.

### 2026-07-18 — Reddit sources dropped, replaced with real evidence

Early findings cited six Reddit discussions. Couldn't relocate or verify them on review. Replaced with: 8 GitHub issues from `internetarchive/openlibrary`, two official doc sources, and my own usability walkthrough. Full list and what's still unverified is in `sources.md`.

### 2026-07-18 — Personas cut from 4 to 2

Library Enthusiast and E-reader Owner didn't map to either active pain point, so they're out — noted as out of scope, not silently deleted.

### 2026-07-18 — Insights, JTBD, and Hypotheses collapsed into one section

Same three ideas, stated three times under different framework labels. Collapsed into one "Key Findings" section, each idea stated once.

### 2026-07-18 — Cut the "quality stars" idea from research

An early draft of the Digital Quality pain point had a mocked-up star-rating UI sitting in the findings, presented like it was evidence. It wasn't — it was a designed solution I'd invented. Cut the UI, kept the actual observation.

### 2026-07-18 — Resolved: is loan type a user choice?

No. Confirmed via [help.archive.org](https://help.archive.org/help/borrowing-from-the-lending-library/) that loan type (1 hour vs. 14 days) is fixed per book — and confirmed hands-on that the real Borrow button doesn't tell you which one you're getting before you click. See `content-state-model.md`.

### 2026-07-18 — "Not Digitized" split from "Read Online"

Original content model folded "book never digitized" into the same label as "you can read this right now." Open Library's own FAQ preemptively reassures people that a non-readable book "doesn't mean something is wrong" — which told me this mix-up happens often enough to need its own FAQ entry. Split into its own state. The flowchart in `research.md` had the same error baked in and got fixed too.

### 2026-07-18 — Open question: is "Read Online" actually a disguised 1-hour loan?

Docs describe 1-hour renewable loans as the default mechanism, which makes me think "Read Online" might not be unlimited access — could be the same CDL loan as any other 1-hour book, just running automatically. Not resolved. Flagged with a concrete test (two sessions on the same book, see if the second one blocks).

### 2026-07-18 — Added State 6: Loan Limit Reached

Had been citing GitHub #439 as supporting evidence for State 2 and leaving it at that. On a second look it needed its own state — it's a different kind of thing (account property, not book property) that can interrupt any borrow regardless of the book's own availability.

### 2026-07-18 — Fixed two broken links before they shipped

Two placement bugs caught before publishing: (1) I'd written status markers directly into markdown headers, which quietly changes their anchor slugs and breaks anything linking to the old one — fixed by moving status into the body text instead. (2) `sources.md` and `content-state-model.md` assumed a `03-decisions/` folder that doesn't exist yet — fixed by placing them flat and adjusting the relative links.

### 2026-07-19 — Rewrote Pain Point #2

Still had three sub-personas in it, including "Researcher," which I'd already cut from the persona list. Also proposed asking users to self-classify their reading intent before borrowing — an idea that never made it into the actual design. What I actually built was simpler: state loan terms upfront (State 2), show waitlist position (State 4), don't ask the user anything. Rewrote the section to point at what got built instead of an idea I'd abandoned without saying so.

### 2026-07-19 — Full audit pass on user-research-findings.md

Went through the whole doc looking for places it hadn't caught up with later decisions. Found:
- The sources section still presented unverified Reddit without any caveat.
- The closing summary described the original 6-stage scope, contradicting the scope decision stated earlier in the same doc.
- The "next step" asked for a journey map that had existed for a while already.
- Pain Point #1's user need included a device question that belongs to a parked pain point.
- Pain Point #5's example opportunity had a download-related bullet, same issue.
- Key Findings #1 and #3 didn't link to the states they actually produced, unlike #2.
- Two stray backticks left over from earlier edits.

This log, and separating it out from the clean docs, is itself the fix from that audit — not just the individual corrections.
