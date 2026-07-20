---
sidebar_position: 3
---

# User Journey Map — Open Library Reading Experience

## Journey Scope

User goal:

> "I want to find a book, access it easily, and read it without unnecessary friction."

 ### Primary Persona

Casual Reader transitioning into a digital library user

(Insights also apply to students and researchers — see [Findings](../01-research/user-research-findings.md#user-personas).)

### Scope (2026-07-18)

Active focus right now: **Discover → Evaluate → Borrow**, matching the scope decision in [Findings](../01-research/user-research-findings.md#scope-decision-2026-07-18). Access/Setup, Read, and Manage Library stages are still documented below, just parked.

## Overview
| Stage         | Discover                | Evaluate                  | Borrow                | Access                        | Read                       | Manage                  |
| ------------- | ----------------------- | ------------------------- | ---------------------- | ----------------------------- | ---------------------------- | ------------------------ |
| User Goal     | Find a book             | Understand availability   | Get access            | Open book on preferred device | Enjoy reading              | Keep track of books     |
| Main Question | "Does this book exist?" | "Can I actually read it?" | "How do I borrow it?" | "How do I open it?"           | "Is this experience good?" | "Where is my book now?" |

## Detailed User Journey
![User Journey Map](/img/user-journey/map.jpg)

### 1. Discover

**User Actions**
- Searches for a title or author
- Browses recommendations
- Finds Open Library through search engines
- Opens a book page

**User Thoughts**

> "I hope they have this book."

> "This looks like the right edition."


**Emotional State**

🙂 Curious -> 🙂 Interested

**User Needs**
- Relevant search results
- Accurate metadata
- Clear book information

**Pain Points**

Search ambiguity — users may find multiple editions, different formats, old records, or incomplete metadata. (Not covered in Findings; specific to the discovery step.)

**Opportunity**

Improve discovery with:
- Edition grouping
- Better recommendations
- Clear book previews


### 2. Evaluate Availability

**User Actions**
- Opens book page
- Looks for access options
- Searches for borrow/read buttons

**User Thoughts**

>"Can I read this right now?"

>"Why is there no borrow button?"

**Emotional State**

🙂 Interested -> 😕 Confused

**User Needs**

Immediate answers:

Is it available?
Can I borrow it?
How long?
How do I read it?

**Pain Points**

See [Users Do Not Understand Book Availability](../01-research/user-research-findings.md#1-users-do-not-understand-book-availability) in Findings.

**Opportunity**

Create a clear availability component — see States 1, 3, and 5 in [Content & State Model](../content-state-model.md) for what this actually became.

### 3. Borrow

**User Actions**
- Creates account/signs in
- Clicks borrow
- Waits for availability
- Accepts loan

**User Thoughts**

>"I found it. Now I just want to start reading."

**Emotional State**

😕 Confusion -> 🙂 Relief

**User Needs**

A simple borrowing process.

**Pain Points**

See [Borrowing Restrictions Create Friction](../01-research/user-research-findings.md#2-borrowing-restrictions-create-friction) and [Borrowing Workflow Is Difficult To Understand](../01-research/user-research-findings.md#5-borrowing-workflow-is-difficult-to-understand) in Findings.

**Opportunity**

Explain before borrowing — see States 2 and 4 in [Content & State Model](../content-state-model.md) for what this actually became.

### 4. Access / Setup

**Status:** ⏸ Parked — out of scope for this phase.

**User Actions**
- Opens reader
- Downloads file
- Transfers to device
- Configures software

**User Thoughts**

>"Why isn't this working?"

**Emotional State**

🙂 Relief -> 😡 Frustration

**User Needs**

A direct path to reading.

**Pain Points**

Biggest friction point in the journey. See [E-reader Integration Is Too Complex](../01-research/user-research-findings.md#3-e-reader-integration-is-too-complex) in Findings.

**Opportunity**

Reduce technical decisions:
Where do you want to read?

📱 Phone
💻 Browser
📖 E-reader

Then provide the correct workflow.

### 5. Read

**Status:** ⏸ Parked — out of scope for this phase.

**User Actions**
- Reads online
- Uses e-reader
- Downloads EPUB/PDF
- Adjusts settings

**User Thoughts**

>"Can I comfortably read this?"

**Emotional State**

Depends on quality:

🙂 Enjoyment or 😐 Friction

**User Needs**
- Good formatting
- Stable reading experience
- Remembered progress

**Pain Points**

See [Digital Book Quality Problems](../01-research/user-research-findings.md#4-digital-book-quality-problems) in Findings.

**Opportunity**

Show quality information.

### 6. Manage Library

**Status:** ⏸ Parked — out of scope for this phase.

**User Actions**
- Saves books
- Tracks reading
- Creates lists
- Returns to previous books

**User Thoughts**

>"I want to remember this book."

>"Where did I save it?"

**Emotional State**

🙂 Satisfaction -> 😕 Lost

**User Needs**

A personal reading space.

**Pain Points**

See [Discovery Is Better Than Management](../01-research/user-research-findings.md#6-discovery-is-better-than-management) and [Personal Library Organization Is Confusing](../01-research/user-research-findings.md#7-personal-library-organization-is-confusing) in Findings.

**Opportunity**

Create a personal dashboard.

## Emotional Journey Map

![Emotional Journey Curve](/img/user-journey/emotional-curve.jpg)
![Three Biggest Friction Points](/img/user-journey/biggest-friction-points.jpg)

**Biggest Friction Points**

## 1. Before Borrowing — ✅ Active scope

**Problem**

Users cannot predict access.

**Impact**

High abandonment risk.

**Opportunity**

Clear availability information.

## 2. After Borrowing — ⏸ Parked

**Problem**

Borrowing does not guarantee successful reading.

**Impact**

Users fail at the main goal.

**Opportunity**

Simplify device access.

## 3. After Reading — ⏸ Parked

**Problem**

Users cannot easily manage their reading history.

**Impact**

Lower retention.

**Opportunity**

Improve personal library.

## Key UX Opportunities
| Opportunity                   | User Impact             | Business/Product Impact     | Scope |
| ------------------------------ | ------------------------- | ----------------------------- | ----- |
| Clear availability states     | Reduces confusion       | Higher successful borrowing | ✅ Active |
| Guided onboarding             | Faster first success    | Lower abandonment           | ✅ Active |
| Device-specific reading flows | Less technical friction | More completed reads        | ⏸ Parked |
| Digital quality indicators    | Better expectations     | Higher satisfaction         | ⏸ Parked |
| Better personal library       | Better retention        | More returning users        | ⏸ Parked |

![Key UX Opportunities](/img/user-journey/key-ux-opportunities.jpg)

[Diagram in Miro](https://miro.com/app/live-embed/uXjVH6pKkQ0=/?embedMode=view_only_without_ui&moveToViewport=17006%2C786%2C18401%2C9876&embedId=492414186818)
