---
created: "2026-02-16T19:30:00-05:00"
last_updated: "2026-02-16T19:30:00-05:00"
version: "1.0.0"
author: "Claude Code CCPM"
---

# System Patterns

## Template Architecture
- Numbered template system (0-9) for different evidence synthesis tasks
- Each template is a self-contained AI system prompt
- Templates designed for any LLM (Claude, Perplexity, etc.)
- Versioned filenames with dates for tracking

## Evidence Tiers
- GRADE framework: 1A (strong/high) through 4 (insufficient)
- Multi-society guideline comparison built into templates
- Mandatory PMID/DOI verification for all clinical claims

## EPIC Attestation Routing
- Template selection based on patient context (CC vs non-CC, trauma vs EGS)
- Critical care = time-based billing (99291/99292)
- Consults = E/M-based billing (99221-99223)
- Two signature block variants based on service type

## Output Pipeline
- Evidence gathering -> grading -> synthesis -> outline -> slides -> citations -> Gamma
- Completed topics stored in outputs/topics/ with presentations subdirectory
