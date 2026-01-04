# TRAUMA AI TEMPLATE SYSTEM

## Evidence-Based Medical Education & Clinical Documentation for Level 1 Trauma Centers

[![Version](https://img.shields.io/badge/version-3.0-blue.svg)]()
[![Institution](https://img.shields.io/badge/institution-UVA%20Health-orange.svg)]()
[![Updated](https://img.shields.io/badge/updated-January%202026-green.svg)]()

---

## Overview

This repository contains a comprehensive AI-assisted system for:

1. **Trauma Evidence Synthesis** - Generate evidence-based topic reviews, journal clubs, and presentations
2. **EPIC EHR Templates** - Clinical documentation templates for attending attestations and billing
3. **Educational Outputs** - Completed topic syntheses ready for teaching use

---

## Quick Start

### For Evidence Synthesis (Templates 0-9)

1. Open your AI assistant (Perplexity Space, Claude, etc.)
2. Copy the contents of `templates/current/trauma-evidence-synthesis-system-v3.0-2026-01.md`
3. Paste as the system prompt
4. Select a template number (0-9) and provide your topic

**Template Menu:**
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

### For Journal Club Presentations

Use `templates/current/journal-club-chalk-talk-template-v2.0-2025-11.md` for structured article analysis with ADDIE-I9 teaching framework.

---

## Repository Structure

```
TRAUMA_AI_TEMPLATE/
│
├── templates/                    # REUSABLE AI SYSTEM PROMPTS
│   ├── current/                  # Active production templates
│   │   ├── trauma-evidence-synthesis-system-v3.0-2026-01.md  # Master template
│   │   ├── journal-club-chalk-talk-template-v2.0-2025-11.md
│   │   ├── topic-research-template-v1.0-2025-12.md
│   │   ├── openevidence-workflow-template-v1.0-2025-01.md
│   │   └── journal-club-simplified-workflow-v1.0-2025-01.md
│   │
│   └── archive/                  # Prior versions
│
├── outputs/                      # GENERATED CONTENT
│   ├── topics/                   # Completed topic syntheses
│   │   ├── antibiotic-prophylaxis/
│   │   │   └── presentations/    # Gamma.app-ready slides
│   │   ├── psh-storming/
│   │   ├── stress-ulcer-prophylaxis/
│   │   ├── hemorrhage-resuscitation/
│   │   ├── spinal-cord-injury/
│   │   └── rib-fractures/
│   │
│   └── topic-lists/              # Topic brainstorms & planning
│
├── epic-ehr/                     # CLINICAL DOCUMENTATION
│   ├── current/                  # Active EPIC templates
│   │   ├── uva-attending-attestation-system-v2.0-2025-12.md
│   │   └── simu-progress-note-template-2025-12.md
│   └── archive/
│
├── reference/                    # SUPPORTING DOCS
│   ├── perplexity-exports/       # Raw AI session archives
│   └── *.md                      # Quick references
│
└── personal/                     # Non-template content
```

---

## Completed Topic Outputs

### Ready-to-Use Evidence Syntheses

| Topic | Files | Presentations |
|-------|-------|---------------|
| **Antibiotic Prophylaxis in Trauma** | 5 documents | Short/Medium/Long |
| **PSH (Storming)** | 1 complete journal club | - |
| **Stress Ulcer Prophylaxis** | 2 documents (incl. REVISE trial) | - |
| **Hemorrhage Control & Resuscitation** | 1 document | - |
| **Spinal Cord Injury** | 1 document | - |
| **Rib Fracture Fixation** | 1 document | - |

---

## EPIC EHR System

### Attending Attestation System v2.0

The attestation system provides MDM-based billing templates for:

- **EGS** (Emergency General Surgery) - Initial/Subsequent (99221-99233)
- **Trauma** - Alpha/Beta/Gamma activations + floor notes
- **Critical Care** - Time-based (99291/99292)
- **SIMU** - Step-down unit notes (99232)

See `epic-ehr/current/uva-attending-attestation-system-v2.0-2025-12.md` for complete routing logic and phrase templates.

---

## Naming Convention

All files follow: `descriptive-name-version-YYYY-MM.md`

**Examples:**
- `antibiotic-prophylaxis-trauma-comprehensive-2025-01-02.md`
- `trauma-evidence-synthesis-system-v3.0-2026-01.md`
- `simu-progress-note-template-2025-12.md`

---

## Usage Guidelines

### Adding New Topic Outputs

1. Run the appropriate template with your topic
2. Save output to `outputs/topics/[topic-name]/`
3. Name file: `[descriptive-name]-[YYYY-MM].md`
4. If presentations generated, save to `presentations/` subfolder

### Updating Templates

1. Create new version in `templates/current/`
2. Move old version to `templates/archive/`
3. Update version number in filename
4. Commit with descriptive message

---

## Evidence Standards

All outputs adhere to:

- **Citations**: PMID/DOI for every claim
- **GRADE ratings**: For all treatment recommendations
- **95% CI**: For all effect sizes
- **NNT**: Where applicable
- **Evidence tiers**: 1A (guidelines) through 4 (expert opinion)
- **Guideline comparison**: ATLS, EAST, WEST, ACCP, SCCM

---

## For AI Assistants

This repository is designed to be self-documenting for AI systems. If you are an AI assistant (Claude, GPT, Perplexity, Gemini, etc.) helping a user with this system:

### Quick Start for AIs

1. **Read first:** `AI_GUIDE.md` - Comprehensive instructions for all AI assistants
2. **Template selection:** `templates/README.md` - Which template to use
3. **Claude-specific:** `templates/current/CLAUDE_INSTRUCTIONS.md` - Claude-specific guidance

### Key Documents

| Document | Purpose |
|----------|---------|
| `AI_GUIDE.md` | Complete AI implementation guide |
| `CONTRIBUTING.md` | How to add new content |
| `templates/README.md` | Template selection and usage |
| `templates/current/CLAUDE_INSTRUCTIONS.md` | Claude-specific instructions |
| `outputs/README.md` | Output organization guide |
| `epic-ehr/README.md` | EPIC EHR system documentation |

### Critical Requirements

When generating content using these templates:

```
✓ Cite every claim with PMID/DOI
✓ Include GRADE ratings for recommendations
✓ Use 95% CI for effect sizes
✓ Calculate NNT where applicable
✓ Label evidence tiers (1A through 4)
✓ Compare across guidelines (ATLS, EAST, WEST, ACCP, SCCM)

✗ Never fabricate citations
✗ Never skip evidence quality ratings
✗ Never use vague language when specific data exists
```

---

## Documentation Map

```
Repository Documentation Structure:

README.md (you are here)
├── AI_GUIDE.md              ← AI assistants start here
├── CONTRIBUTING.md          ← How to add content
│
├── templates/
│   ├── README.md            ← Template selection guide
│   └── current/
│       └── CLAUDE_INSTRUCTIONS.md  ← Claude-specific
│
├── outputs/
│   └── README.md            ← Output organization
│
└── epic-ehr/
    └── README.md            ← EPIC system guide
```

---

## Author

**Evan Daniel DeCan, MD**
Assistant Professor, University of Virginia School of Medicine
Trauma Surgery | Emergency General Surgery | Surgical Critical Care

---

## License

This repository is for educational and clinical use. Evidence syntheses should be verified against primary sources before clinical application.

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 3.0 | Jan 2026 | Repository reorganization, AI documentation, comprehensive structure |
| 2.0 | Nov 2025 | Journal Club v2.0, ADDIE-I9 framework |
| 1.0 | Oct 2025 | Initial template system |
