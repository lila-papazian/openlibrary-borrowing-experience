---
sidebar_position: 1
---

# The Open Library Borrow Flow: Case Study

**Role:** Research, content strategy, interaction design, front-end implementation

**Scope:** Discover → Evaluate → Borrow — one moment in a much bigger product

**Stack:** Figma, React, Vite, Tailwind — styled with Open Library's own production design tokens

---

## The problem, short version

You find a book on Open Library, you want to borrow it, and — more often than it should — you can't tell why you can't, or what you're actually getting when you can.

That's the whole scope of this project. Not the site, not the full borrowing system. Just the moment between "I found this" and "now what," because that's where the evidence pointed.

## Why this scope

Early research turned up seven candidate pain points — discovery, borrowing, device compatibility, digital quality, personal library management. All real. Only two — unclear availability and borrowing workflow confusion — scored high on both frequency and severity, and only those two had evidence solid enough to act on.

Everything else got parked, not thrown out. Still documented, still tagged, waiting for a later phase. Cutting down to the two problems with the strongest evidence was the first real decision of the project, and it shaped everything after it.

## Research: what actually held up

The research went through a hard correction partway in, and I'd rather tell that straight than edit it out.

An early draft cited six Reddit threads as sources. I couldn't find them again — turned out they were closer to plausible-sounding synthesis than actual research. Instead of quietly patching the gap, I wrote it down: `sources.md` exists specifically to separate what's verified from what isn't, and to explain what happened.

What replaced it:

- **The product's own GitHub issue tracker.** Eight real issues from `internetarchive/openlibrary`, the team's own backlog naming the exact problems this project is about — [#1754](https://github.com/internetarchive/openlibrary/issues/1754) ("search results should clearly identify unavailable books"), [#648](https://github.com/internetarchive/openlibrary/issues/648) (no wait estimate on the waitlist), among others.
- **Official docs, cross-checked.** Found a real discrepancy in the process — the older FAQ still mentions Adobe Digital Editions, while Internet Archive's current help center describes an LCP-based system. The FAQ is stale.
- **My own usability testing.** Not staged — an actual attempt to borrow a real book, including a screenshot of a genuinely confusing "Readable Only" filter, and a real click on Borrow that opened a new tab with zero indication of whether I'd gotten a 1-hour or 14-day loan. Not a hypothesis. The problem, happening in real time.

## A wrong assumption, caught mid-build

Partway through the content model, I hit a question that exposed a real gap in the thinking so far: a book showing "no readable format" doesn't mean it's unavailable — Open Library's own FAQ reassures people that it just hasn't been digitized yet, nothing's wrong on their end.

The original design had folded that case into the same "Read Online" label used for books you can actually read right now. Those are opposite outcomes. Collapsing them wouldn't have fixed the confusion — it would have reproduced it. Fixing it meant splitting one state into two, and going back to fix the same error in the system-logic diagram, which had it baked in the same way.

A second one followed close behind: my assumption that "Read Online" meant no loan at all was probably also wrong. The docs describe 1-hour renewable loans as the default mechanism, which suggests "Read Online" might just be a 1-hour loan running automatically. That one's still an open question — flagged, not guessed at, because getting it wrong would undercut the whole model.

Both are left in the repo, dated, with the reasoning attached. A case study that only shows the clean final answer doesn't show how the answer got found.

## The content & state model

Six states came out of this — five tied to the book, one tied to the account:

| State | What it answers | What it fixes |
|---|---|---|
| Read Online | Can I read this? | One label instead of three ambiguous catalog states |
| Borrow Available | How long do I get it for? | States loan length before commitment, not after |
| Currently Unavailable | Why can't I access it? | Names the actual cause instead of a dead end |
| Join Waitlist | When will I get it? | Position, estimate, how the notification actually works |
| Not Digitized | Is something wrong? | Distinguishes "doesn't exist" from "in use" |
| Loan Limit Reached | Why can't I borrow this, it's available? | Account-level interrupt, not a book state |

Every row is tied to something real — a GitHub issue, an FAQ entry, or a screenshot from testing. Nothing here was invented to round out the count to six.

## Wireframes: cheap enough to be wrong

Before any of this touched a design tool, each state got tested as a throwaway low-fidelity mock — fast to make, faster to bin, which is the entire point of a wireframe. Only after the copy held up did the same six states move into [Figma](https://www.figma.com/design/8QroAtJwgeudlAZjlAXGuj/OpenLibrary-Borrowing-%E2%80%94-Wireframes?node-id=0-1&t=ilVx1UvN5G4P6K8B-1), in the same tool a real dev handoff would use.

## Prototype: real content, real tokens

Last step ports the content model into working code — React, Vite, Tailwind, styled with Open Library's actual production design tokens, pulled from their public repo (`static/css/tokens/`) instead of eyeballed off screenshots. Colors, spacing, radius, type — same CSS custom properties the real site ships. Not inspired by the product. Built from its own source of truth.

## What this is actually demonstrating

Not "can build a UI." The parts that matter more:

- **Turning a fuzzy problem into a bounded one** — seven plausible pain points down to two with real evidence, and being able to explain why the other five got cut.
- **Catching my own mistakes before they compounded** — the not-digitized/read-online mix-up got found and fixed before it reached a wireframe.
- **Treating "I don't know yet" as an acceptable answer** — the open question about disguised 1-hour loans isn't resolved with a guess; it's flagged, with a real way to check it later.
- **Design and code as one decision, not a handoff** — the same content spec drives the Figma file and the React component.

## Links

- [Full research & documentation repo](https://github.com/lila-papazian/openlibrary-borrowing-experience)
- [Figma — 6-state wireframes](https://www.figma.com/design/8QroAtJwgeudlAZjlAXGuj/OpenLibrary-Borrowing-%E2%80%94-Wireframes?node-id=0-1&t=ilVx1UvN5G4P6K8B-1)
- Prototype source: `ol-borrow-prototype/` (React + Vite + Tailwind, real OL design tokens)
- [Decision log](./decision-log.md) — the dated, unpolished version of the corrections above
