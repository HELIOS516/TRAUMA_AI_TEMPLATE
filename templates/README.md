# Templates Directory

## AI System Prompts for Evidence-Based Medical Education

This directory contains reusable templates that serve as AI system prompts for generating trauma/critical care educational content.

---

## Quick Reference: Which Template Should I Use?

```
┌─────────────────────────────────────────────────────────────────────┐
│                        TEMPLATE SELECTION GUIDE                      │
├─────────────────────────────────────────────────────────────────────┤
│                                                                       │
│  "I need a COMPLETE topic review"                                    │
│     └──→ trauma-evidence-synthesis-system-v3.0 (Template 0)         │
│                                                                       │
│  "I need to ANALYZE A SPECIFIC ARTICLE for journal club"            │
│     └──→ journal-club-chalk-talk-template-v2.0                      │
│                                                                       │
│  "I need to SYSTEMATICALLY RESEARCH a topic"                        │
│     └──→ topic-research-template-v1.0                               │
│                                                                       │
│  "I need to INTEGRATE OPENEVIDENCE searches"                        │
│     └──→ openevidence-workflow-template-v1.0                        │
│                                                                       │
│  "I just need a QUICK WORKFLOW guide"                               │
│     └──→ journal-club-simplified-workflow-v1.0                      │
│                                                                       │
└─────────────────────────────────────────────────────────────────────┘
```

---

## Current Templates (Active)

### 1. Trauma Evidence Synthesis System v3.0 ⭐ MASTER

**File:** `current/trauma-evidence-synthesis-system-v3.0-2026-01.md`

The comprehensive menu-driven system with Templates 0-9:

| # | Template | Best For |
|---|----------|----------|
| 0 | Complete Setup | Full topic package (epi, patho, guidelines, treatment, presentations) |
| 1 | Literature Review | Systematic evidence synthesis with 20-30 citations |
| 2 | Journal Club | Deep analysis of single article |
| 3 | Find Articles | Tiered literature search |
| 4 | Guideline Synthesis | ATLS/EAST/WEST/ACCP comparison matrix |
| 5 | Evidence Comparison | Guidelines vs primary literature analysis |
| 6 | Algorithm | Clinical decision flowchart with evidence per node |
| 7 | Presentations | Short/Medium/Long Gamma.app-ready slides |
| 8 | Protocol Guide | Implementation-ready institutional protocol |
| 9 | Quick Lookup | Rapid answer with 3-5 key citations |

**How to Use:**
1. Copy entire file contents
2. Paste as system prompt in AI assistant
3. User selects template number (0-9)
4. AI asks clarifying questions one at a time
5. AI generates output with full evidence standards

---

### 2. Journal Club & Chalk Talk Template v2.0

**File:** `current/journal-club-chalk-talk-template-v2.0-2025-11.md`

Structured workflow for analyzing medical literature and creating teaching materials.

**Includes:**
- Part I: Comprehensive Journal Club Analysis
  - Presenter information
  - Study background & clinical context
  - Methods deep-dive
  - Results with statistics (CI, p-values, NNT)
  - Critical appraisal (strengths, limitations, bias)
  - Clinical application

- Part II: Chalk Talk Development
  - ADDIE-I9 instructional design framework
  - Gagne's Nine Events of Instruction
  - Board map templates
  - Discussion questions

- Part III: Gamma.app Slide Templates
  - Layout instructions per slide type
  - Image prompts for AI image generation
  - Speaker notes framework

---

### 3. Topic Research Template v1.0

**File:** `current/topic-research-template-v1.0-2025-12.md`

Systematic literature review workflow following Open Evidence principles.

**Sections:**
- Part I: Topic Definition & Evidence Hierarchy
- Part II: Systematic Evidence Collection
- Part III: Evidence Synthesis Tables
- Part IV: Clinical Overview Generation
- Part V: Algorithm Development
- Part VI: Presentation Output

**Evidence Tier System:**
- Tier 1A: Institutional guidelines (ATLS, EAST, WEST)
- Tier 1B: Systematic reviews, meta-analyses
- Tier 2A: RCTs
- Tier 2B: Prospective cohorts
- Tier 3A: Retrospective studies
- Tier 3B: QI studies
- Tier 4: Expert opinion

---

### 4. OpenEvidence Workflow Template v1.0

**File:** `current/openevidence-workflow-template-v1.0-2025-01.md`

Integration workflow for using OpenEvidence.com with journal club development.

**Phases:**
1. Initial Setup (Google Docs, article identification)
2. Primary Article Analysis (CRITICAL: read full article first)
3. OpenEvidence Queries (fill knowledge gaps)
4. Template Population
5. Output Generation

---

### 5. Journal Club Simplified Workflow v1.0

**File:** `current/journal-club-simplified-workflow-v1.0-2025-01.md`

Condensed version of the journal club template for quick reference.

**Best for:** Users familiar with the system who need a quick checklist.

---

## Archive Directory

**Location:** `archive/`

Contains prior versions of templates for reference. These should NOT be used for new content generation but are preserved for:
- Historical reference
- Understanding evolution of the system
- Rollback if needed

**Current Archives:**
- `journal-club-chalk-talk-template-v1.0-2025-11.md` - Original journal club template
- `trauma-evidence-synthesis-system-v3.0-backup.txt` - Backup copy of master template

---

## Version Numbering

Templates follow semantic versioning: `vX.Y`

- **X (Major):** Significant structural changes, new sections
- **Y (Minor):** Refinements, bug fixes, clarifications

**Date suffix:** `-YYYY-MM` indicates creation/update month

---

## Creating a New Template

1. Create file in `current/` with proper naming:
   ```
   [template-name]-v[X.Y]-[YYYY-MM].md
   ```

2. Include these required sections:
   - Purpose statement
   - Role definition for AI
   - Workflow steps
   - Output format specifications
   - Evidence standards reference

3. Update this README with template description

4. If replacing existing template:
   - Move old version to `archive/`
   - Increment version number

---

## For AI Assistants

See `CLAUDE_INSTRUCTIONS.md` in this directory for specific guidance on implementing these templates.

See `/AI_GUIDE.md` at repository root for comprehensive AI documentation.
