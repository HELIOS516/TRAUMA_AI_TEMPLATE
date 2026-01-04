# AI ASSISTANT GUIDE

## Complete Instructions for AI Systems Using This Repository

**Last Updated:** January 2026
**Compatibility:** Claude, GPT-4, Perplexity, Gemini, and other LLMs
**Purpose:** Enable any AI assistant to understand, implement, and extend this trauma education system

---

## QUICK START FOR AI ASSISTANTS

If a user asks you to help with trauma education content, follow these steps:

### Step 1: Identify the Task Type

| User Request | Template to Use | Location |
|--------------|-----------------|----------|
| "Create a full topic review" | Template 0 (Complete) | `templates/current/trauma-evidence-synthesis-system-v3.0-*.md` |
| "Analyze this article for journal club" | Journal Club Template | `templates/current/journal-club-chalk-talk-template-v2.0-*.md` |
| "Research a topic systematically" | Research Template | `templates/current/topic-research-template-v1.0-*.md` |
| "Help with EPIC attestation" | EPIC Templates | `epic-ehr/current/` |
| "Make a presentation" | Template 7 or outputs | `outputs/topics/*/presentations/` |

### Step 2: Load the Appropriate Template

Read the template file and use it as your system instructions. The templates contain:
- Role definitions
- Output format specifications
- Evidence standards (GRADE, CI, NNT requirements)
- Step-by-step workflows

### Step 3: Execute with User's Topic

Follow the template's workflow exactly. Key requirements:
- Use REAL evidence only (PubMed, guidelines, UpToDate)
- Cite with PMID/DOI
- Include GRADE ratings for recommendations
- Calculate NNT where applicable
- Compare across guidelines (ATLS, EAST, WEST, ACCP, SCCM)

---

## REPOSITORY ARCHITECTURE

```
TRAUMA_AI_TEMPLATE/
│
├── AI_GUIDE.md              ← YOU ARE HERE (read this first)
├── README.md                ← Human-focused overview
├── CONTRIBUTING.md          ← How to add new content
│
├── templates/               ← REUSABLE AI SYSTEM PROMPTS
│   ├── README.md            ← Template selection guide
│   ├── current/             ← Active templates (use these)
│   │   ├── CLAUDE_INSTRUCTIONS.md  ← AI-specific guidance
│   │   └── *.md             ← The actual templates
│   └── archive/             ← Old versions (reference only)
│
├── outputs/                 ← GENERATED CONTENT
│   ├── README.md            ← Output organization guide
│   ├── topics/              ← Completed syntheses by topic
│   │   └── [topic-name]/
│   │       ├── *.md         ← Main synthesis documents
│   │       └── presentations/  ← Slide decks
│   └── topic-lists/         ← Planning documents
│
├── epic-ehr/                ← CLINICAL DOCUMENTATION
│   ├── README.md            ← EPIC system guide
│   ├── current/             ← Active templates
│   └── archive/             ← Old versions
│
├── reference/               ← SUPPORTING MATERIALS
│   └── perplexity-exports/  ← Raw AI conversation archives
│
└── personal/                ← Non-template content
```

---

## TEMPLATE SYSTEM OVERVIEW

### The Master Template: Trauma Evidence Synthesis System v3.0

**Location:** `templates/current/trauma-evidence-synthesis-system-v3.0-*.md`

This is the primary system prompt. It provides a menu-driven interface (Templates 0-9):

| Template | Name | Use Case | Output Size |
|----------|------|----------|-------------|
| **0** | Complete System Setup | Full comprehensive package | Large (50+ pages) |
| **1** | Literature Review | Systematic evidence review | Medium (20-30 pages) |
| **2** | Journal Club | Single article analysis | Medium (15-20 pages) |
| **3** | Find Articles | Literature search | Small (5-10 pages) |
| **4** | Guideline Synthesis | Multi-society comparison | Medium (15-20 pages) |
| **5** | Evidence Comparison | Guidelines vs RCTs | Medium (15-20 pages) |
| **6** | Algorithm | Clinical decision flowchart | Small (5-10 pages) |
| **7** | Presentations | Short/Medium/Long slides | Variable |
| **8** | Protocol Guide | Implementation protocol | Medium (15-20 pages) |
| **9** | Quick Lookup | Rapid answer with citations | Small (2-5 pages) |

### How to Use a Template

1. **Read the full template file** into your context
2. **Adopt the role** defined in the template (Trauma Evidence Synthesis AI)
3. **Follow the workflow** exactly as specified
4. **Apply evidence standards** (citations, GRADE, confidence intervals)
5. **Format output** according to template specifications

---

## EVIDENCE STANDARDS (CRITICAL)

### Every Output MUST Include:

1. **Citations with identifiers:**
   ```
   Good: "Mortality reduced by 23% (PMID: 34567890)"
   Bad:  "Mortality was reduced significantly"
   ```

2. **GRADE ratings for recommendations:**
   ```
   Good: "GRADE 1A: Strong recommendation, high-quality evidence"
   Bad:  "This is recommended"
   ```

3. **Confidence intervals for effect sizes:**
   ```
   Good: "OR 0.67 (95% CI 0.52-0.86)"
   Bad:  "OR 0.67"
   ```

4. **NNT calculations where applicable:**
   ```
   Good: "NNT = 8 to prevent one SSI"
   Bad:  "Prophylaxis is effective"
   ```

5. **Evidence tier labeling:**
   - Tier 1A: Guidelines (ATLS, EAST, WEST, ACCP, SCCM)
   - Tier 1B: Systematic reviews, meta-analyses
   - Tier 2A: RCTs (multicenter > single center)
   - Tier 2B: Prospective cohorts
   - Tier 3A: Retrospective studies
   - Tier 3B: QI studies
   - Tier 4: Expert opinion, case reports

### What NEVER to Do:

- Hallucinate citations, PMIDs, or DOIs
- Provide recommendations without evidence quality ratings
- Give vague language instead of specific numbers
- Skip confidence intervals on major outcomes
- Ignore guideline comparisons when relevant

---

## OUTPUT FILE NAMING CONVENTION

All generated files should follow this pattern:

```
[descriptive-name]-[YYYY-MM].md
```

**Examples:**
- `antibiotic-prophylaxis-trauma-comprehensive-2025-01.md`
- `tbi-management-journal-club-2025-02.md`
- `hemorrhage-control-short-presentation-2025-01.md`

### For Presentations:
```
[topic]-[length]-[slide-count]slides-[YYYY-MM].md
```

**Examples:**
- `antibiotic-prophylaxis-short-14slides-2025-01.md`
- `psh-storming-long-45slides-2025-02.md`

---

## CREATING NEW TOPIC OUTPUTS

When generating a new topic synthesis:

### 1. Check for Existing Content
```
Look in: outputs/topics/
See if topic folder already exists
```

### 2. Create Topic Folder if Needed
```
outputs/topics/[new-topic-name]/
outputs/topics/[new-topic-name]/presentations/
```

### 3. Generate Content Using Template
- Use Template 0 for comprehensive synthesis
- Use Template 7 for presentations
- Use Template 2 for journal club analysis

### 4. Save with Proper Naming
```
outputs/topics/[topic]/[descriptive-name]-[YYYY-MM].md
```

### 5. Update Topic List (Optional)
Add to `outputs/topic-lists/` if this is a new topic area

---

## EPIC EHR SYSTEM

### Purpose
Clinical documentation templates for attending attestations and billing at UVA Health System.

### Key Files
- `uva-attending-attestation-system-v2.0-*.md` - Master attestation system
- `simu-progress-note-template-*.md` - Step-down unit notes

### Important Rules for EPIC Templates

1. **No em dashes** - Use only standard hyphens
2. **No tabs** - ASCII only, left-justified
3. **Preserve SmartLinks/SmartLists exactly** - Token names and IDs are critical
4. **Never fabricate** - Do not invent diagnoses, labs, or events
5. **Respect billing constraints** - Use exact codes specified

### Billing Basis
| Note Type | Billing Basis |
|-----------|---------------|
| EGS/Trauma floor notes | MDM (Medical Decision Making) |
| Critical Care (ICU) | TIME (99291/99292) |
| SIMU step-down | MDM |
| Operative | CPT-based |

---

## EXTENDING THE SYSTEM

### Adding a New Template

1. Create file in `templates/current/` with version number
2. Follow naming: `[template-name]-v[X.Y]-[YYYY-MM].md`
3. Include:
   - Role definition
   - Workflow steps
   - Output format specification
   - Evidence standards reference
4. Update `templates/README.md`

### Archiving Old Versions

1. Move old template to `templates/archive/`
2. Keep filename but can add `-archived` suffix
3. Git history preserves full change log

### Adding New Topic Areas

1. Create folder: `outputs/topics/[topic-name]/`
2. Create subfolder: `outputs/topics/[topic-name]/presentations/`
3. Generate content using appropriate template
4. Add entry to main README.md topic table

---

## COMMON AI TASKS

### Task: "Help me prepare a journal club on [ARTICLE]"

1. Read `templates/current/journal-club-chalk-talk-template-v2.0-*.md`
2. Ask user for:
   - Article citation/PMID
   - Target audience
   - Presentation date
3. Follow template sections:
   - Presenter info
   - Study background
   - Methods analysis
   - Results with statistics
   - Critical appraisal
   - Clinical implications
4. Generate chalk talk outline
5. Optionally create Gamma.app-ready slides

### Task: "Create a comprehensive review of [TOPIC]"

1. Read `templates/current/trauma-evidence-synthesis-system-v3.0-*.md`
2. Execute Template 0 workflow:
   - Ask Q1: Topic specification
   - Ask Q2: Target audience
   - Ask Q3 (optional): Specific controversies
3. Generate all sections:
   - Epidemiology
   - Pathophysiology
   - Guidelines comparison
   - Diagnostics
   - Treatment (tiered by evidence)
   - Complications
   - Pearls and pitfalls
4. Include bibliography organized by tier
5. Offer presentation generation (Template 7)

### Task: "Help with EPIC attestation"

1. Read `epic-ehr/current/uva-attending-attestation-system-v2.0-*.md`
2. Identify note type (EGS, Trauma, CC, SIMU)
3. Determine MDM complexity or time (for CC)
4. Use exact phrase template
5. Preserve all SmartList tokens exactly

---

## PERPLEXITY SPACE CONFIGURATION

If setting up a Perplexity Space with this system:

### System Prompt
Copy entire contents of:
```
templates/current/trauma-evidence-synthesis-system-v3.0-*.md
```

### Space Settings
- **Name:** TRAUMA EVIDENCE SYNTHESIS SYSTEM
- **Model:** Pro (for citations)
- **Search:** Enabled (for real-time evidence)

### Initial Message
The template includes the interactive menu [0-9] that displays automatically.

---

## TROUBLESHOOTING

### "Template output is too generic"
- Ensure you're using REAL evidence, not generating plausible-sounding content
- Search PubMed/guidelines for actual data
- Include specific numbers, not vague language

### "Missing citations"
- Every factual claim needs a source
- If uncertain, state: "Current high-quality data are limited"
- Provide best available evidence with honest limitations

### "Presentation format issues"
- Check Gamma.app layout instructions in template
- Use exact formatting specified (headers, bullet levels)
- Include speaker notes for each slide

### "EPIC template not working"
- Verify no tabs (use spaces only)
- Check SmartList token IDs match exactly
- Ensure no special characters (em dashes, smart quotes)

---

## VERSION HISTORY

| Version | Date | Changes |
|---------|------|---------|
| 3.0 | Jan 2026 | Added Sections 3-5 (Cases, Presentations, Gamma) |
| 2.0 | Nov 2025 | Journal Club V2.0, ADDIE-I9 framework |
| 1.0 | Oct 2025 | Initial template system |

---

## CONTACT & ATTRIBUTION

**Author:** Evan Daniel DeCan, MD
**Institution:** University of Virginia Health System
**Specialties:** Trauma Surgery, EGS, Surgical Critical Care

---

*This guide is designed for AI assistants. For human-readable documentation, see README.md*
