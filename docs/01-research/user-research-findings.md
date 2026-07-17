---
sidebar_position: 2
---

User Research Findings
========================================================

Research Topic
--------------

**Understanding reader pain points when discovering, borrowing, accessing, and managing books through Open Library and Internet Archive.**

Research Question
-----------------

**How do readers discover, borrow, access, and manage books through Open Library, and where does the experience break down?**

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
    

Research Sources
================

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
    
*   What device can I use?
    

Opportunity
-----------

Introduce clearer availability indicators:

Example:

The Hobbit

🟢 Available now
Borrow for 14 days

or

🟡 Available online only

or

⚪ Catalog record only`

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

Different users have different goals:

### Casual Reader

 >"I want to read this once."

### Student

> "I need this textbook throughout the semester."

### Researcher

> "I need reliable access and citations."

The platform provides the same borrowing model for different user needs.

User Need
---------

Users need borrowing experiences adapted to intent.

Opportunity
-----------

Support reading goals:

Why are you accessing this book?

○ Casual reading

○ Studying

○ Research

○ Reference


3\. E-reader Integration Is Too Complex
=======================================

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

Add book quality indicators:

Example:

Digital Edition Quality

Text accuracy: ★★★★★

Formatting: ★★★★☆

Scan quality: ★★★★★  `

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

Add contextual guidance:

Example:

This book is available through digital lending.

You can:

✓ Borrow for 14 days

✓ Read in browser

✓ Download with supported software

6\. Discovery Is Better Than Management
=======================================

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
Reading History   `

User Personas
=============

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

Find → Borrow → Read   `

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

Persona 3 — The E-reader Owner
==============================

Goal
----

Read books on dedicated devices.

Behaviors
---------

*   Uses Kobo, Kindle, or similar devices
    
*   Expects digital compatibility
    

Frustrations
------------

*   DRM workflows
    
*   File formats
    
*   Manual transfers
    

Needs
-----

One-click device integration.

Persona 4 — The Library Enthusiast
==================================

Goal
----

Discover rare and historical books.

Behaviors
---------

*   Explores collections
    
*   Searches unusual titles
    
*   Values preservation
    

Frustrations
------------

*   Metadata inconsistencies
    
*   Scan quality
    
*   Unclear availability
    

Needs
-----

Better archival information.

Prioritized Pain Point Matrix
=============================

| Pain Point                    | Frequency | Severity | Opportunity                     |
| ----------------------------- | --------- | -------- | ------------------------------- |
| Unclear availability status   | High      | High     | Redesign book status indicators |
| Borrowing workflow confusion  | High      | High     | Add guided onboarding           |
| Device compatibility problems | Medium    | High     | Improve reading integrations    |
| Digital format quality        | Medium    | Medium   | Add quality indicators          |
| Personal library organization | Medium    | Medium   | Improve library dashboard       |
| Search and discovery          | Medium    | Medium   | Improve recommendations         |


Research Insights
=================

Insight 1
---------

Readers think about access, not lending models.
-----------------------------------------------

### Problem Statement

Users need to understand how they can access a book immediately because current experiences expose library complexity instead of user outcomes.

Insight 2
---------

Borrowing is only one step in the reading journey.
--------------------------------------------------

### Problem Statement

Users need a seamless path from discovery to reading because technical barriers after borrowing prevent successful completion of their goal.

Insight 3
---------

Open Library combines multiple experiences into one interface.
--------------------------------------------------------------

### Problem Statement

Users need clearer separation between:

*   Finding books
    
*   Borrowing books
    
*   Reading books
    
*   Managing books
    

Recommended Next Research Steps
===============================

1\. Create User Journey Map
---------------------------

Map the complete experience:

Discover -> Evaluate -> Borrow -> Access -> Read -> Manage Library


Identify:

*   User actions
    
*   Emotional states
    
*   Friction points
    
*   Opportunities
    

2\. Define Jobs To Be Done
--------------------------

Examples:

> "When I discover a book, I want to immediately know whether I can access it, so I can decide whether to invest time."

> "When I borrow a book, I want to read it on my preferred device, so I can continue my reading habit."

3\. Create UX Hypotheses
------------------------

Examples:

### Hypothesis 1

If availability states are clearer, users will spend less time searching for access options.

### Hypothesis 2

If device setup is simplified, more borrowed books will become completed reads.

### Hypothesis 3

If personal library organization improves, users will return more frequently.

Final Research Summary
======================

The main opportunity is not simply improving book discovery.

The larger opportunity is reducing the gap between:

**"I found a book"**

and

**"I successfully read the book."**

Open Library already provides a valuable collection. The strongest UX opportunity lies in making access, borrowing, reading, and organization feel like one continuous experience instead of separate library systems.