# Research

Diagrams represents understanding using [Borrowing Books Through Open Library](https://openlibrary.org/help/faq/borrow) as source.

| Status | WIP |
|--------|-----|
| Last Updated | 2026-07-16 |
| Source | Borrowing Books Through Open Library |

## Evidence

| Source | Confidence |
|---------|------------|
| Official documentation | High |
| User reports | Not researched |
| GitHub issues | Not researched |
| Source code | Not researched |

## Purpose

This document is based on the OpenLibrary documentation and will be continuously updated as additional sources are reviewed.

## Domain Understanding

```mermaid
classDiagram
    class User {
        userId
    }

    class Book {
        workId
        title
    }

    class Edition {
        editionId
        format
    }

    class Loan {
        loanType
        dueDate
        status
    }

    class Waitlist {
        position
    }

    User "1" --> "0..*" Loan : borrows
    Loan --> "1" Edition : for
    Book "1" --> "1..*" Edition : contains
    User "1" --> "0..*" Waitlist : joins
    Waitlist --> "1" Edition : for
```

## Borrowing Decision Flow

```mermaid
flowchart TD

A[Book Page]

A --> B{Borrowable?}

B -->|No| C[Read only]

B -->|Yes| D{Loan Type}

D --> E[1 Hour]

D --> F[14 Days]

E --> G{Available?}

F --> H{Available?}

G -->|Yes| I[Borrow]

G -->|No| J[Unavailable]

H -->|Yes| K[Borrow]

H -->|No| L[Join Waitlist]
```

## Assumptions

- Loan types are mutually exclusive.
- Waitlists are only available for some loan types.
- Availability is evaluated after loan type.

## Open Questions

- How do waitlists work?
- Can different editions have different lending states?
- Can users renew every loan?
- Are there account-level borrowing limits?