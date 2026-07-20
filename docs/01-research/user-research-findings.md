---
sidebar_position: 2
---

User Research Findings
========================================================

Research Topic
--------------

Understanding reader pain points when discovering, borrowing, accessing, and managing books through Open Library and Internet Archive.

Research Question
-----------------

How do readers discover, borrow, access, and manage books through Open Library, and where does the experience break down?

1\. Executive Summary
=====================

This research analyzes user feedback from Reddit discussions and Open Library feature documentation to identify recurring usability issues, frustrations, and opportunities.

The main finding is that users do not struggle primarily with finding books — they struggle with understanding **what they can do with those books after discovery**.

The current experience exposes library concepts such as lending models, availability states, DRM, and formats, while users expect a simpler mental model:

> "I found a book → I want to read it."

The biggest gaps appear between:

*   Discovery and access
*   Borrowing and reading
*   Digital availability and device compatibility
*   Personal collections and library management

## Scope Decision (2026-07-18)

Narrowing this to the **Discover → Evaluate → Borrow** moment — the confusion between finding a book and actually starting a loan. That's where the two worst pain points sit in the matrix below (unclear availability, borrowing workflow confusion).

Device compatibility, digital quality, and personal library management are parked, not solved. Still documented below, just not in scope for design or prototyping right now.

Research Sources
================

> **Note:** the Reddit discussions listed below are from an early draft and could not be verified — see [Sources](./sources.md) for what's actually confirmed (official documentation, GitHub issues, and a first-hand usability walkthrough). Don't cite the Reddit list below as evidence.

Community Discussions
---------------------

*   Reddit — YA Literature discussion about Open Library borrowing experiences
*   Reddit — Internet Archive/Open Library borrowable books discussion
*   Reddit — LibGen discussion about downloading books from Open Library
*   Reddit — Internet Archive discussion about unavailable books
*   Reddit — LibGen discussion about downloading from Archive.org
*   Reddit — Kobo discussion about using Open Library/Internet Archive

Product Documentation
---------------------

*   Open Library Blog — New Features category

Key User Pain Points
====================

1\. Users Do Not Understand Book Availability
=============================================

Observation
-----------

Users frequently discover books but cannot understand why they cannot borrow or read them.

A book may appear in search results but have different states:

*   Available for borrowing
*   Available for limited borrowing
*   Read online only
*   Preview only
*   Catalog record only
*   Available elsewhere

The interface does not always communicate these differences clearly.

User Pain Point
---------------

> "I found the book, but I don't know why I cannot access it."

Root Cause
----------

The system is organized around library catalog concepts, while users think in terms of outcomes:

Expected user model:

Search book
     ↓
Open book
     ↓
Read/download

Actual system model:

Search book
     ↓
Book record
     ↓
Check availability type
     ↓
Understand lending rules
     ↓
Determine access method

User Need
---------

Users need immediate clarity about:

*   Can I read this?
*   Can I borrow this?
*   How long can I access it?

Opportunity
-----------

This is the pain point behind States 1, 3, and 5 in [Content & State Model](../content-state-model.md) — Read Online, Currently Unavailable, and Not Digitized. Early sketch, before those states were refined:

The Hobbit

🟢 Available now
Borrow for 14 days

or

🟡 Available online only

or

⚪ Catalog record only

2\. Borrowing Restrictions Create Friction
==========================================

Observation
-----------

Users become frustrated when books exist digitally but are limited by lending rules.

Common issues:

*   Short borrowing periods
*   Waiting lists
*   Limited simultaneous access
*   Confusion around controlled digital lending

User Pain Point
---------------

> "I can access the book, but not in the way I need."

The platform's lending rules (loan length, waitlist eligibility) aren't communicated before the user commits to borrowing — the friction isn't the rules themselves, it's discovering them after the fact.

User Need
---------

Users need loan terms — length, and whether a waitlist applies — stated *before* they click Borrow, not discovered afterward.

Opportunity
-----------

This is the pain point directly behind two of the states built out in [Content & State Model](../content-state-model.md): **State 2 (Borrow Available)** states loan length upfront instead of after commitment, and **State 4 (Join Waitlist)** surfaces position and estimated wait instead of a bare "join waitlist" button. (See [Decision Log](../decision-log.md#2026-07-19--rewrote-pain-point-2) for what this section originally said and why it changed.)


3\. E-reader Integration Is Too Complex
=======================================

**Status:** ⏸ Out of scope for this phase — see [Scope Decision](#scope-decision-2026-07-18).

Observation
-----------

Users attempting to read borrowed books on devices such as Kobo experience technical friction.

Problems include:

*   DRM confusion
*   File compatibility
*   EPUB issues
*   Required external software
*   Device transfer problems

User Pain Point
---------------

> "I borrowed the book, but getting it onto my device is another problem."

Current Journey
---------------

Find book
    ↓
Borrow
    ↓
Download file
    ↓
Understand DRM
    ↓
Install software
    ↓
Convert format
    ↓
Transfer to device
    ↓
Read

The borrowing action is simple; the reading action is not.

User Need
---------

Users need a seamless transition from borrowing to reading.

Opportunity
-----------

Create device-aware flows:

Borrow book

Choose device:

📱 Mobile
📖 Browser
📘 Kobo
📗 Kindle

Continue reading

4\. Digital Book Quality Problems
=================================

**Status:** ⏸ Out of scope for this phase — see [Scope Decision](#scope-decision-2026-07-18).

Observation
-----------

Users report issues with:

*   Poor EPUB formatting
*   OCR mistakes
*   Low-quality scans
*   Difficult reading experiences

This especially affects older and archival books.

User Pain Point
---------------

> "The book exists digitally, but the reading experience is poor."

User Need
---------

Users need confidence that a digital edition is usable before opening it.

Opportunity
-----------

Communicate digital edition quality before the user commits to opening it. The specific mechanism (rating system, flags, sample preview, etc.) is a design decision to be evaluated during prototyping, not a finding from this research phase.

5\. Borrowing Workflow Is Difficult To Understand
=================================================

Observation
-----------

Users repeatedly ask:

*   How do I borrow?
*   Why can't I download?
*   Why is there no borrow button?
*   How do I read on my device?

This suggests the workflow requires previous library knowledge.

User Pain Point
---------------

> "The platform assumes library knowledge."

Root Cause
----------

Users must understand concepts such as:

*   Controlled digital lending
*   Loans
*   DRM
*   Formats
*   Availability rules

These concepts are invisible to experienced library users but confusing for new users.

Opportunity
-----------

This is the pain point behind States 2 and 4 in [Content & State Model](../content-state-model.md) — stating loan terms and waitlist position before commitment, instead of after.

Example:

This book is available through digital lending.

You can:

✓ Borrow for 14 days

✓ Read in browser

6\. Discovery Is Better Than Management
=======================================

**Status:** ⏸ Out of scope for this phase — see [Scope Decision](#scope-decision-2026-07-18).

Observation
-----------

Open Library has introduced improvements around:

*   Search
*   Reading logs
*   Lists
*   Recommendations
*   Want-to-read functionality

These improvements suggest historical problems around discovery and organization.

User Pain Point
---------------

> "Finding a book is easier than managing what I found."

User Need
---------

Users need better ways to:

*   Save books
*   Track progress
*   Organize collections
*   Return to books later

7\. Personal Library Organization Is Confusing
==============================================

**Status:** ⏸ Out of scope for this phase — see [Scope Decision](#scope-decision-2026-07-18).

Observation
-----------

Users have different categories of books:

*   Borrowed
*   Want to read
*   Currently reading
*   Finished
*   Saved lists

These categories are not always clearly separated.

User Pain Point
---------------

> "I don't know where my books are."

Opportunity
-----------

Create a clearer personal dashboard:

My Library  
Currently Reading  
Borrowed Books  
Want To Read  
Finished  
Collections  
Reading History

User Personas
=============

Two personas are developed in depth because they map directly onto the highest-frequency, highest-severity pain points identified above (unclear availability, borrowing workflow confusion). Other user types (e.g. e-reader owners, archival/rare-book researchers) surface in the source discussions but with lower frequency and are treated as **out of scope** for this phase — worth revisiting only if later evidence shows their needs diverge meaningfully from these two.

Persona 1 — The Casual Reader
=============================

Goal
----

Quickly find and read books.

Behaviors
---------

*   Searches for specific titles
*   Wants immediate access
*   Does not want technical explanations

Frustrations
------------

*   Cannot understand availability
*   Too many steps
*   Confusing actions

Needs
-----

A simple path:

Find → Borrow → Read

Persona 2 — The Student / Researcher
====================================

Goal
----

Access books for learning and reference.

Behaviors
---------

*   Needs reliable access
*   Reads for longer periods
*   Requires notes and references

Frustrations
------------

*   Loan expiration
*   Limited access
*   Difficulty using books offline

Needs
-----

Long-term access and research-friendly tools.

Prioritized Pain Point Matrix
=============================

| Pain Point                    | Frequency | Severity | Opportunity                     | Scope |
| ----------------------------- | --------- | -------- | -------------------------------- | ----- |
| Unclear availability status   | High      | High     | Redesign book status indicators | ✅ Active |
| Borrowing workflow confusion  | High      | High     | Add guided onboarding           | ✅ Active |
| Device compatibility problems | Medium    | High     | Improve reading integrations    | ⏸ Parked |
| Digital format quality        | Medium    | Medium   | Add quality indicators          | ⏸ Parked |
| Personal library organization | Medium    | Medium   | Improve library dashboard       | ⏸ Parked |
| Search and discovery          | Medium    | Medium   | Improve recommendations         | ⏸ Parked |


Key Findings
=================

Three patterns show up across the pain points above. Stating each once, as a hypothesis, instead of repeating it three times as an "insight," a "job to be done," and a "hypothesis."

1\. Readers think about access, not lending models
---------------------------------------------------

**Problem:** current experiences expose library complexity (loan types, DRM, formats) instead of user outcomes (can I read this, and how).

**Job to be done:** "When I discover a book, I want to immediately know whether I can access it, so I can decide whether to invest time."

**Hypothesis:** if availability states are clearer, users will spend less time searching for access options.

*(This is the reasoning behind States 1, 3, and 5 in [Content & State Model](../content-state-model.md).)*

2\. Borrowing is only one step in the reading journey
---------------------------------------------------------

**Status:** ⏸ Out of scope for this phase.

**Problem:** technical barriers after borrowing (DRM, device setup, format conversion) get in the way of the actual goal — reading. This is about what happens after a successful loan, outside the current scope. Kept here, not being worked on.

**Hypothesis (parked):** if device setup is simplified, more borrowed books will become completed reads.

3\. Open Library exposes catalog concepts instead of a simple find-and-borrow path
--------------------------------------------------------------------------------------

**Problem:** between finding a book and having it in hand, users have to interpret concepts (edition, loan type, waitlist, availability state) that the interface doesn't translate into a simple yes/no answer.

**Hypothesis:** if the path from finding a book to borrowing it surfaces one clear next action instead of catalog concepts, fewer users will abandon before completing a loan.

*(This is the reasoning behind all six states in [Content & State Model](../content-state-model.md) — each one replaces a catalog concept with a plain-language answer to what the user actually wants to know.)*

*(Managing and reading books once borrowed — the second half of the original insight — is parked along with the rest of the post-borrow scope above.)*

Recommended Next Research Step
===============================

~~Create a User Journey Map~~ — done, see [User Journey Map](../02-user-models/user-journey-map.md). Content model, Figma wireframes, and a React prototype followed from it.

Next up: usability testing of the wireframed states with real readers. Haven't done this yet.

Final Research Summary
======================

The opportunity isn't just improving discovery.

Within this project's scope, it's closing the gap between:

**"I found a book"**

and

**"I successfully started borrowing it."**

Open Library already has a valuable collection. The real opportunity in this moment is making availability and loan terms clear *before* the user commits, not after.

The bigger ambition — one continuous experience across discovery, reading, and personal library management — is real, but that's exactly what the [Scope Decision](#scope-decision-2026-07-18) above parked. This is what this phase actually set out to do, not the full product vision.
