# omrei

⚠️ **START — WORK IN PROGRESS** ⚠️ 
⚠️ **FOUNDATIONAL STAGE — EXPECT BREAKING CHANGES** ⚠️ 

This repository represents the **beginning** of a long-term effort.
Structure, naming, scope, and behavior are all subject to change.

Nothing here should be considered complete.

---

## What is omrei?

**omrei** is a foundation project for building a **PHP Subject-Matter-Expert (SME) AI model**.

The goal is not to build a chatbot first.

The goal is to build **trustworthy understanding** of the PHP language — grounded in its specifications, history, and design decisions — and only then layer AI capabilities on top.

This repository starts with the most critical prerequisite:

> A clean, auditable, AI-ready corpus of PHP RFCs.

---

## Why PHP RFCs?

PHP RFCs encode:

- Language evolution decisions
- Migration implications
- Design trade-offs and rejected ideas
- Behavioral edge cases not obvious from documentation alone

For an AI model to act as a **true PHP SME**, it must understand not just *what PHP does*, but *why it does it*.

RFCs are the canonical source of that truth.

---

## Core Principles

omrei is built on a small number of non-negotiable rules:

- Extraction before inference
- Rules before AI
- Archival data must never be modified
- AI must not invent facts
- Every transformation must be auditable and reversible

AI is introduced **only after** deterministic extraction and curation are complete.

---

## Current Scope (Intentionally Minimal)

At present, this repository provides **only three scripts**.

These scripts form a **deterministic corpus-generation pipeline** for PHP RFCs.

There is:
- No agent loop
- No interactive UI
- No automation magic
- No opinionated summaries

This restraint is intentional.

---

## Foundational Corpus Pipeline

The current pipeline consists of **three explicit stages**:

```text
PHP RFC Wiki HTML
        ↓
01_extract_rfc_to_json.php
        ↓
all/*.json   (archival truth)
        ↓
02_build_actionable_corpus.sh
        ↓
actionable/raw/*.json
actionable/enriched/*.json
        ↓
03_emit_markdown_for_ai.sh
        ↓
actionable/enriched/markdown/*.md
        ↓
AI analysis / refinement (future)
```

### Stage 1: Archival Truth

- Raw RFC HTML is extracted
- Output is stored as structured JSON
- No interpretation or enrichment
- This data is immutable

### Stage 2: Actionable Structuring

- RFCs are reorganized into developer-relevant forms
- Still deterministic
- Still reversible
- No inference

### Stage 3: AI-Oriented Emission

- Markdown is emitted specifically for AI consumption
- This is the *boundary* where AI may eventually be applied
- Upstream data remains untouched

---

## What This Is *Not* (Yet)

- Not an AI assistant
- Not a CLI tool for end users
- Not a TUI application
- Not a finished pipeline

Those will come later — *only after* the foundation is solid.

---

## Planned Direction

Future development will expand omrei along two paths:

### 1. Wizard-Driven TUI Pipeline

A guided terminal interface that:

- Walks users through corpus ingestion
- Explains each transformation step
- Allows inspection, validation, and correction
- Makes the system understandable, not opaque

The wizard teaches before it automates.

### 2. CLI-Only Power Commands

For advanced users who want direct control:

- RFC normalization
- Schema inspection
- Diffing and comparison
- Consistency checks
- Targeted extraction

The TUI explains.
The CLI scales.

---

## The Name: omrei

**omrei** is a constructed name derived from Japanese concepts:

- **om** — from *onmyō* (陰陽): hidden balance, internal structure
- **rei** — from *rei* (霊): spirit, essence, animating presence

Together, omrei means:

> *The animating spirit of hidden systems.*

---

## Design Philosophy

- Local-first
- Transparent transformations
- No silent automation
- No unverifiable inference
- Respect for historical truth
- Build understanding before abstraction

omrei does not attempt to replace developers.

It exists to help them see clearly.

---

## Final Note

This repository is intentionally small.

Every layer added must earn its place.

If you are reading this at the beginning, you are early.
