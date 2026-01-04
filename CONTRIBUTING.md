# Contributing to Trauma AI Template System

## How to Add New Content, Templates, and Outputs

This guide covers how to extend the repository with new templates, topic syntheses, and documentation.

---

## Quick Links

- [Adding New Topic Outputs](#adding-new-topic-outputs)
- [Creating New Templates](#creating-new-templates)
- [Updating Existing Templates](#updating-existing-templates)
- [Adding EPIC EHR Templates](#adding-epic-ehr-templates)
- [Documentation Standards](#documentation-standards)
- [Git Workflow](#git-workflow)

---

## Adding New Topic Outputs

### Step 1: Choose or Create Topic Folder

```bash
# Check existing topics
ls outputs/topics/

# If topic doesn't exist, create folder
mkdir -p outputs/topics/[new-topic-name]
mkdir -p outputs/topics/[new-topic-name]/presentations
```

### Step 2: Generate Content

Use the appropriate template:

| Content Type | Template | Location |
|--------------|----------|----------|
| Full synthesis | Template 0 | `templates/current/trauma-evidence-synthesis-system-v3.0-*.md` |
| Journal club | Journal Club v2.0 | `templates/current/journal-club-chalk-talk-template-v2.0-*.md` |
| Research review | Research Template | `templates/current/topic-research-template-v1.0-*.md` |
| Presentations | Template 7 | Part of synthesis system |

### Step 3: Name the File

Format: `[descriptive-name]-[YYYY-MM].md`

**Naming Rules:**
- Use lowercase with hyphens
- Be descriptive but concise
- Include the date (year-month minimum)
- Include document type if not obvious

**Examples:**
```
tbi-management-comprehensive-2025-02.md          ✓
damage-control-resuscitation-journal-club-2025-02.md  ✓
massive-transfusion-protocol-2025-02.md          ✓

TBI.md                                            ✗ (too short, no date)
new document.md                                   ✗ (not descriptive)
Document1.md                                      ✗ (meaningless)
```

### Step 4: Verify Quality Standards

Before saving, ensure:

- [ ] Every claim has PMID/DOI citation
- [ ] GRADE ratings for all recommendations
- [ ] 95% CI for effect sizes
- [ ] NNT calculated where applicable
- [ ] Evidence tier labeled
- [ ] Clear section headers
- [ ] Bibliography organized by tier

### Step 5: Update outputs/README.md

Add your new topic to the topic list in `outputs/README.md`.

---

## Creating New Templates

### Step 1: Determine Template Purpose

Ask yourself:
- What gap does this template fill?
- Who is the target user?
- What output will it produce?

### Step 2: Create Template File

```bash
# Create in current/ directory
touch templates/current/[template-name]-v1.0-[YYYY-MM].md
```

### Step 3: Required Template Sections

Every template must include:

```markdown
# [TEMPLATE NAME]

## PURPOSE
[What this template does and who it's for]

## VERSION
Version: X.Y
Date: [YYYY-MM]

## ROLE DEFINITION
[How the AI should behave when using this template]

## WORKFLOW
[Step-by-step instructions]

## OUTPUT FORMAT
[Exact structure of expected output]

## EVIDENCE STANDARDS
[Reference to main evidence standards or custom requirements]

## EXAMPLES
[Sample inputs and outputs if helpful]
```

### Step 4: Test the Template

Before committing:
1. Load template into AI assistant
2. Run through complete workflow
3. Verify output meets quality standards
4. Check for unclear instructions

### Step 5: Document the Template

Add entry to `templates/README.md`:

```markdown
### [Template Name] v[X.Y]
**File:** `current/[filename].md`
**Purpose:** [Brief description]
**Best For:** [Use cases]
```

---

## Updating Existing Templates

### Minor Updates (Bug fixes, clarifications)

1. Edit the template directly
2. Increment minor version (v1.0 → v1.1)
3. Add note to version history section
4. Commit with descriptive message

### Major Updates (New sections, structural changes)

1. **Archive old version:**
   ```bash
   mv templates/current/[template]-v[OLD].md templates/archive/
   ```

2. **Create new version:**
   ```bash
   cp templates/archive/[template]-v[OLD].md templates/current/[template]-v[NEW].md
   ```

3. **Make changes and update version number**

4. **Update templates/README.md**

5. **Commit with detailed message**

---

## Adding EPIC EHR Templates

### Special Requirements

EPIC templates have strict formatting rules:

```
✓ ASCII characters only
✓ Hyphens (-) not em dashes (—)
✓ Straight quotes (") not smart quotes ("")
✓ Spaces, not tabs
✓ SmartList tokens exactly as specified
```

### Validation Checklist

Before saving:

- [ ] No tabs (convert to spaces)
- [ ] No em dashes (replace with hyphens)
- [ ] No smart quotes (replace with straight)
- [ ] SmartList syntax correct `{TOKEN:12345}`
- [ ] Character limits respected
- [ ] Tested in EPIC (if possible)

### File Location

```bash
# Active templates
epic-ehr/current/

# Old versions
epic-ehr/archive/
```

---

## Documentation Standards

### README Files

Every major directory should have a README.md explaining:
- Purpose of the directory
- Contents overview
- How to use/add content
- Special considerations

### Inline Documentation

Templates should include:
- Clear section headers
- Workflow instructions
- Examples where helpful
- Version history

### AI Instructions

When creating content AI assistants will use:
- Be explicit about expected behavior
- Provide examples of good/bad output
- List common mistakes to avoid
- Include quick reference cards

---

## Git Workflow

### Commit Messages

Format: `[Action]: [Brief description]`

**Actions:**
- `Add:` New content
- `Update:` Modified existing content
- `Fix:` Bug fixes
- `Archive:` Moving to archive
- `Docs:` Documentation changes

**Examples:**
```
Add: TBI management comprehensive synthesis
Update: Journal club template v2.0 with ADDIE framework
Fix: SmartList token in SIMU template
Archive: Journal club template v1.0
Docs: Add contributing guidelines
```

### Branching (Optional)

For major changes:
```bash
git checkout -b feature/new-template-name
# Make changes
git add .
git commit -m "Add: New template for X"
git checkout main
git merge feature/new-template-name
```

### Before Pushing

Run through this checklist:
- [ ] All files properly named
- [ ] READMEs updated
- [ ] No sensitive/personal data
- [ ] Quality standards met
- [ ] Tested if applicable

---

## File Naming Convention Summary

| Content Type | Pattern | Example |
|--------------|---------|---------|
| Templates | `[name]-v[X.Y]-[YYYY-MM].md` | `journal-club-template-v2.0-2025-11.md` |
| Topic outputs | `[descriptive-name]-[YYYY-MM].md` | `tbi-management-comprehensive-2025-02.md` |
| Presentations | `[topic]-[length]-[count]slides-[YYYY-MM].md` | `hemorrhage-short-14slides-2025-02.md` |
| EPIC templates | `[descriptive-name]-[YYYY-MM].md` | `simu-progress-note-template-2025-12.md` |

---

## Need Help?

- **AI Guide:** See `/AI_GUIDE.md` for AI assistant instructions
- **Template Guide:** See `/templates/README.md` for template selection
- **Output Guide:** See `/outputs/README.md` for output organization

---

## Author

**Evan Daniel DeCan, MD**
University of Virginia Health System
