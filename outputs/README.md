# Outputs Directory

## Generated Evidence Syntheses & Educational Content

This directory contains completed topic syntheses, presentations, and educational materials generated using the template system.

---

## Directory Structure

```
outputs/
├── README.md              ← You are here
├── topics/                ← Completed topic syntheses
│   ├── antibiotic-prophylaxis/
│   │   ├── [synthesis docs]
│   │   └── presentations/
│   ├── psh-storming/
│   ├── stress-ulcer-prophylaxis/
│   ├── hemorrhage-resuscitation/
│   ├── spinal-cord-injury/
│   └── rib-fractures/
│
└── topic-lists/           ← Planning and brainstorm documents
```

---

## Current Topics

### Antibiotic Prophylaxis in Trauma
**Folder:** `topics/antibiotic-prophylaxis/`

| File | Description | Template Used |
|------|-------------|---------------|
| `antibiotic-prophylaxis-trauma-comprehensive-2025-01-02.md` | Full synthesis (108KB) | Template 0 |
| `facial-fractures-antibiotics-template0-2025-01.md` | Facial fractures focus | Template 0 |
| `antibiotic-prophylaxis-general-summary-2025-01.md` | Condensed version | Template 0 |
| `antibiotic-prophylaxis-evidence-synthesis-2025-01.md` | Evidence summary | Template 0 |
| `antibiotic-duration-24h-analysis-2025-01.md` | Duration subtopic | Template 0 |

**Presentations:** `presentations/`
- Short (14 slides)
- Medium (25 slides)
- Long (40 slides)

---

### PSH (Paroxysmal Sympathetic Hyperactivity)
**Folder:** `topics/psh-storming/`

| File | Description | Template Used |
|------|-------------|---------------|
| `psh-journal-club-complete-2025-11.md` | Complete journal club | Journal Club v2.0 |

---

### Stress Ulcer Prophylaxis
**Folder:** `topics/stress-ulcer-prophylaxis/`

| File | Description | Template Used |
|------|-------------|---------------|
| `revise-trial-sup-analysis-2025-01.md` | REVISE trial analysis | Journal Club v2.0 |
| `stress-ulcer-ppx-journal-club-2025-01.md` | SUP overview | Journal Club v2.0 |

---

### Hemorrhage Control & Resuscitation
**Folder:** `topics/hemorrhage-resuscitation/`

| File | Description | Template Used |
|------|-------------|---------------|
| `hemorrhage-control-resuscitation-fundamentals-2025-01.md` | Fundamentals overview | Template 0 |

---

### Spinal Cord Injury
**Folder:** `topics/spinal-cord-injury/`

| File | Description | Template Used |
|------|-------------|---------------|
| `spinal-cord-injury-management-2025-01.md` | SCI management | Template 0 |

---

### Rib Fractures
**Folder:** `topics/rib-fractures/`

| File | Description | Template Used |
|------|-------------|---------------|
| `rib-fracture-fixation-strategies-2025-01.md` | Fixation strategies | Template 0 |

---

## Adding New Outputs

### Step 1: Determine Topic Folder

Check if a folder exists for your topic:
- If yes → save to existing folder
- If no → create new folder: `topics/[topic-name]/`

### Step 2: Generate Content

Use appropriate template:
- **Full synthesis:** Template 0 from `trauma-evidence-synthesis-system-v3.0`
- **Article analysis:** Journal Club template
- **Presentations:** Template 7 or generate from synthesis

### Step 3: Name the File

Format: `[descriptive-name]-[YYYY-MM].md`

**Good examples:**
- `tbi-management-comprehensive-2025-02.md`
- `damage-control-surgery-journal-club-2025-02.md`
- `mtp-protocol-short-15slides-2025-02.md`

**Bad examples:**
- `new_document.md` (not descriptive)
- `TBI.md` (no date, too short)
- `Document 1.md` (meaningless)

### Step 4: Create Presentations Subfolder (if needed)

If generating slides: `topics/[topic-name]/presentations/`

---

## Topic Lists

**Folder:** `topic-lists/`

Contains planning documents and brainstormed topics for future development.

| File | Content |
|------|---------|
| `trauma-icu-topic-ideas-2025-01.md` | 30+ potential presentation topics |

---

## Output Quality Standards

All outputs in this directory should meet these criteria:

### Evidence Requirements
- [ ] Every claim has citation (PMID/DOI)
- [ ] GRADE ratings for recommendations
- [ ] 95% CI for effect sizes
- [ ] NNT calculated where applicable
- [ ] Evidence tier labeled (1A through 4)

### Format Requirements
- [ ] Clear section headers
- [ ] Tables for comparisons
- [ ] Bullet points for key findings
- [ ] Bibliography organized by tier

### Presentation Requirements (if applicable)
- [ ] Gamma.app layout instructions
- [ ] Speaker notes for each slide
- [ ] Appropriate slide count for length
- [ ] Image prompts included

---

## For AI Assistants

When creating new outputs:

1. **Read the template** from `templates/current/`
2. **Follow the workflow** exactly as specified
3. **Apply evidence standards** rigorously
4. **Save to correct location** with proper naming
5. **Suggest adding** to this README's topic list

---

*See `/AI_GUIDE.md` for complete AI documentation*
