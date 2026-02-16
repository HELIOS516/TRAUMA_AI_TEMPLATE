# Trauma AI Template System

## Overview

Evidence-based medical education and clinical documentation system for Level 1 Trauma Centers. Contains AI system prompt templates (0-9) for evidence synthesis, journal club analysis, guideline comparison, and presentation generation, plus EPIC EHR attestation templates.

## Quick Start

1. Copy `templates/current/trauma-evidence-synthesis-system-v3.0-2026-01.md` as system prompt
2. Select template number (0-9) and provide your topic
3. Generated outputs go in `outputs/topics/{topic}/`

## File Structure

```
trauma-ai-template/
  templates/
    current/             # Active production templates (v3.0)
    archive/             # Prior versions
  outputs/
    topics/              # Completed topic syntheses (6+ topics)
    topic-lists/         # Topic brainstorms and planning
  epic-ehr/
    current/             # Active EPIC attestation templates
  reference/             # Clinical reference materials
  personal/              # Personal workflow docs
  .claude/context/       # CCPM context files
```

## Template Menu

| # | Template | Output |
|---|----------|--------|
| 0 | Complete System Setup | Full comprehensive package |
| 1 | Literature Review | Guidelines + RCTs + citations |
| 2 | Journal Club | Single article deep analysis |
| 3 | Find Articles | Tiered study search |
| 4 | Guideline Synthesis | Multi-society comparison |
| 5 | Evidence Comparison | Guidelines vs primary literature |
| 6 | Algorithm | Clinical decision flowchart |
| 7 | Presentations/Chalk Talk | Short/Medium/Long slide decks |
| 8 | Protocol Guide | Implementation-ready protocol |
| 9 | Quick Lookup | Rapid answer + citations |

## Conventions

- Evidence standards: GRADE framework (1A-4), 95% CI, NNT, exact p-values
- Citations: Every clinical claim requires PMID or DOI verification
- EPIC templates: UVA-compliant, billing-aware (99291/99292)
- Default presenter: Evan DeCan, MD

## DO NOT

- Do NOT fabricate PMIDs (most common AI error)
- Do NOT use em/en dashes in EPIC templates (ASCII only)
- Do NOT skip citation verification
- Do NOT mix template versions (always use current/)
