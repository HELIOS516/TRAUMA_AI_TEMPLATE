# EPIC EHR Templates

## Clinical Documentation System for UVA Health System

This directory contains attending attestation templates and clinical documentation for EPIC EHR integration.

---

## ⚠️ CRITICAL RULES

These templates are designed for direct copy-paste into EPIC. **Strict formatting is required:**

| Rule | Correct | Incorrect |
|------|---------|-----------|
| No em dashes | `-` (hyphen) | `—` (em dash) |
| No tabs | Spaces only | Tab characters |
| No smart quotes | `"straight"` | `"curly"` |
| Preserve tokens | `{TOKEN:12345}` | `{TOKEN: 12345}` |
| ASCII only | Standard characters | Special symbols |

---

## Directory Structure

```
epic-ehr/
├── README.md              ← You are here
├── current/               ← Active production templates
│   ├── uva-attending-attestation-system-v2.0-2025-12.md
│   └── simu-progress-note-template-2025-12.md
│
└── archive/               ← Prior versions
    └── uva-attending-attestation-system-v2.0-clean-backup.md
```

---

## Current Templates

### 1. UVA Attending Attestation System v2.0

**File:** `current/uva-attending-attestation-system-v2.0-2025-12.md`

**Purpose:** Master document for all attending attestation and billing templates.

#### Menu Structure (EDATT [54319])

```
EDATT [54319]
│
├── EDATTEGS [54320]           ← EGS (Emergency General Surgery)
│   ├── EGS MDM INITIAL        ← 99221/99222/99223
│   └── EGS MDM SUBSEQUENT     ← 99231/99232/99233
│
├── EDATTTRAUMAMDM [54321]     ← Trauma
│   ├── TRAUMA ACTIVATIONS     ← Alpha/Beta/Gamma
│   ├── TRAUMA INITIAL         ← 99221
│   └── TRAUMA SUBSEQUENT      ← 99231/99232/99233
│
├── EDATTCCSPLITSIMU [55649]   ← Critical Care & SIMU
│   ├── EDATTCC                ← 99291/99292 (TIME-based)
│   ├── EDATTCCSPLITSHARE      ← Split/share CC
│   └── EDATTSIMU              ← 99232 (MDM-based)
│
└── EDATTOPERATIVE             ← CPT-based (unchanged)
```

#### Billing Basis Quick Reference

| Note Type | Billing Basis | Codes |
|-----------|---------------|-------|
| EGS Initial | MDM | 99221/99222/99223 |
| EGS Subsequent | MDM | 99231/99232/99233 |
| Trauma Activations | MDM | 99222/99223 |
| Trauma Floor | MDM | 99231/99232/99233 |
| Critical Care (ICU) | **TIME** | 99291/99292 |
| SIMU Step-down | MDM | 99232 |
| Operative | CPT | Procedure-specific |

---

### 2. SIMU Progress Note Template

**File:** `current/simu-progress-note-template-2025-12.md`

**Purpose:** Step-down unit (SIMU) attending progress note.

**Structure:**
```
SICU ATTENDING PROGRESS NOTE

Patient Name - MRN - Age/Sex POD#X s/p [procedure]; [status], on SIMU.

N: [Neuro]
CV: [Cardiovascular]
P: [Pulmonary]
GI: [Gastrointestinal]
R: [Renal]
H: [Hematology]
ID: [Infectious Disease]
Lines: [Lines/tubes/drains]
Dispo: SIMU, [plan]

ATTENDING ATTESTATION - SIMU
[Attestation content...]

E/M Billing: 99232 - Subsequent hospital care, moderate MDM
```

---

## SmartLists Reference

| SmartList | ID | Purpose |
|-----------|-----|---------|
| `{EDATTCCDX:54798}` | 54798 | Critical care diagnoses |
| `{EDATTCCSVCS:54356}` | 54356 | Critical care services rendered |
| `{EDBILLCCMENU:54470}` | 54470 | CC time buckets (99291/99292) |
| `{MRN trauma diagnoses:50834}` | 50834 | Trauma injury list |
| `{mrn response time:50839}` | 50839 | Trauma response time (Alpha/Beta) |
| `{does or does not:50840}` | 50840 | Boolean for hospitalization/OR |
| `{N/APOSTOP:55824}` | 55824 | POD/HOD selector |

---

## MDM Complexity Levels

### Low Complexity (99221/99231)
- Acute uncomplicated illness OR stable chronic condition
- Limited data review
- Low-risk management

### Moderate Complexity (99222/99232)
- One or more chronic illnesses with mild exacerbation
- Moderate data review
- Moderate-risk management

### High Complexity (99223/99233)
- Acute illness posing threat to life/function
- Extensive data review
- High-risk management decisions

---

## Critical Care Time Documentation

For 99291/99292 billing (ICU):

| Code | Time | Requirement |
|------|------|-------------|
| 99291 | 30-74 min | First unit |
| 99292 | Each additional 30 min | Subsequent units |

**Document in note:**
- Total bedside time
- Services provided
- Critical care diagnoses

---

## For AI Assistants

### When Helping with Attestations:

1. **Ask for note type first**
   - EGS? Trauma? CC? SIMU?

2. **Determine complexity/time**
   - For MDM: Low/Moderate/High
   - For CC: Total minutes

3. **Use exact template**
   - Copy phrase template exactly
   - Preserve all SmartList tokens
   - Do not alter formatting

4. **Validate output**
   - Check for tabs (replace with spaces)
   - Check for em dashes (replace with hyphens)
   - Check SmartList syntax
   - Verify character limits (SIMU first section <1500)

### Common Mistakes to Avoid:

```
WRONG: — (em dash)
RIGHT: - (hyphen)

WRONG: {TOKEN: 12345} (space after colon)
RIGHT: {TOKEN:12345}

WRONG: "Smart quotes"
RIGHT: "Straight quotes"

WRONG: Tab-indented content
RIGHT: Space-indented content
```

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 2.0 | Dec 2025 | MDM-based restructure, added SIMU |
| 1.0 | Oct 2025 | Initial attestation system |

---

## Author

**Evan Daniel DeCan, MD**
Assistant Professor, UVA School of Medicine
Trauma Surgery | EGS | Surgical Critical Care

---

*These templates are institution-specific to UVA Health System. Adaptation may be required for other institutions.*
