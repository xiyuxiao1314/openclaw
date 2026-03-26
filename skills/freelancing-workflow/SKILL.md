---
name: freelancing-workflow
description: Run a conservative semi-automated freelancing workflow for small, well-defined client tasks. Use when screening freelance jobs, deciding whether to engage, drafting concise professional replies, enforcing pricing and scope gates, managing delivery, handling bounded aftercare, and capturing lessons for future work.
---

# Freelancing Workflow

Use this skill for small freelance opportunities where speed, clarity, and scope control matter more than volume.

## Goal

Operate a conservative workflow that:

- finds small, clear, low-risk jobs
- rejects ambiguous, risky, or poor-fit work early
- drafts concise professional communication
- requires human confirmation before external engagement, pricing, execution, and final delivery
- keeps delivery bounded
- records lessons for future improvement

## Core Principle

The goal is not to win the most jobs. The goal is to accept only work that is clear, controllable, and likely to be delivered well.

## Top-Level Workflow

Follow this order:

1. Screening
2. Communication
3. Price confirmation
4. Start work
5. Ongoing communication and delivery
6. Aftercare if needed
7. Review
8. Close the objective
9. Summarize lessons

Do not skip steps.

## Hard Rules

Always reject or pause when any of the following apply:

- the task is ambiguous
- the user documents are insufficient and clarification does not fix that
- the work looks larger than a small task
- the task contains a difficult bug or deep debugging uncertainty
- the task needs high-risk permissions, production changes, or sensitive external actions
- the task appears to involve cheating, abuse, infringement, deception, or other unsafe activity
- you do not have a clear path to complete the work reliably

## Required Behavior by Stage

### 1. Screening

Do all of the following:

- read the listing carefully
- read attached docs if present
- classify the task
- check client quality signals
- score the task
- decide: recommend, clarify, or reject

Use:
- `references/workflow-overview.md`
- `references/screening-rules.md`
- `references/job-hunting-rhythm.md`
- `templates/project-screening-summary.md`
- `templates/project-record.md`

### 2. Communication

Only after user approval.

Keep communication:

- concise
- professional
- honest
- non-committal when scope is unclear

Use:
- `templates/first-contact.md`
- `templates/clarification-questions.md`
- `templates/rejection.md`

### 3. Price Confirmation

Only confirm pricing after scope and deliverables are clear.

- do not hard-quote ambiguous work
- do not overpromise timing
- prefer small bounded scope

Use:
- `templates/price-and-scope.md`

### 4. Start Work

Before execution:

- confirm the task is still small and clear
- confirm user approval
- confirm no new risks appeared

Use:
- `references/checklists.md`

### 5. Ongoing Communication and Delivery

- report meaningful changes early
- do not silently absorb scope creep
- validate before delivery
- require user confirmation before final external delivery

Use:
- `references/checklists.md`
- `references/failure-handling.md`

### 6. Aftercare

Treat aftercare as bounded support for the original scope only.

If the request changes task nature, re-run intake instead of treating it as aftercare.

Use:
- `templates/aftercare-boundary.md`
- `references/checklists.md`

### 7. Review

Record what happened, including:

- why the task was accepted or rejected
- whether scope drift occurred
- whether the client showed warning signs
- whether the original judgment was accurate

Use:
- `references/review-and-lessons.md`
- `templates/project-record.md`

### 8. Close the Objective

A task is closed only when it is either:

- delivered and bounded
- or explicitly abandoned with a clear reason

### 9. Summarize Lessons

Extract at least one reusable lesson and decide whether templates, checklists, scoring, or boundaries should change.

Use:
- `references/review-and-lessons.md`
- `templates/project-record.md`

## Directory Guide

- `templates/` → message and reporting templates
- `references/` → rules, checklists, scoring, and boundaries
- `../../reviews/freelancing/` → optional run records and project reviews

## Suggested Run Discipline

- keep candidate reports compact
- prefer no candidate over weak candidates
- log meaningful decisions
- keep project records reusable
- tighten the system whenever the same failure pattern appears twice

## External Action Gates

Require explicit user approval before:

- contacting a client
- confirming price or timeline externally
- starting execution on a client task
- sending final delivery
- taking any action involving outside accounts, payments, deployments, or sensitive systems

## Output Style

When reporting freelance opportunities to the user, prefer compact summaries with:

- title
- link
- type
- clarity level
- fit assessment
- risk notes
- recommendation

When rejecting, be clean and direct. Do not over-explain.
