```table-of-contents
title: 
style: nestedList # TOC style (nestedList|nestedOrderedList|inlineFirstLevel)
minLevel: 0 # Include headings from the specified level
maxLevel: 0 # Include headings up to the specified level
include: 
exclude: 
includeLinks: true # Make headings clickable
hideWhenEmpty: false # Hide TOC if no headings are found
debugInConsole: false # Print debug info in Obsidian console
```
# **AI WORKFLOW TEMPLATE Journal Club & Chalk Talk Development with OpenEvidence Integration**

## **PURPOSE**

This workflow instructs AI assistants to create comprehensive, evidence-based journal club presentations and chalk talks using real-time literature synthesis via OpenEvidence.com, with output directly into Google Docs.

---

## **PHASE 1: INITIAL SETUP**

## **Step 1: Create Working Document**

- Open Google Docs and create new document
    
- Title format: "[Topic] - Journal Club & Chalk Talk - [Date]"
    
- Set up document structure with headings
    

## **Step 2: Identify Primary Article & Topic**

- Primary citation provided by user
    
- Article URL/PDF location
    
- Topic/clinical question to address
    
- Target audience level (residents, attendings, mixed)
    

---

## **PHASE 2: PRIMARY ARTICLE ANALYSIS**

## **Step 2A: Read Full Primary Article**

**CRITICAL INSTRUCTION: READ THE COMPLETE ARTICLE FIRST**

Before beginning any analysis or OpenEvidence queries, the AI must:

1. **Navigate to the primary article** (PDF, ReadCube, PubMed, journal website)
    
2. **Read the ENTIRE article thoroughly** using `get_page_text` tool
    
3. **Extract all content** including:
    
    - Abstract
        
    - Full methods section
        
    - Complete results with all tables/figures
        
    - Discussion and limitations
        
    - Supplementary materials (if accessible)
        
    - References
        
4. **Document article details:**
    
    - Full citation
        
    - DOI/URL
        
    - Study design specifics
        
    - All numerical data
        
    - Statistical methods
        
    - Key findings with exact values
        

**Do NOT proceed to template completion until the full article has been read and comprehended.**

## **Step 2B: Identify Knowledge Gaps**

After reading the primary article:

- Identify clinical questions needing additional evidence
    
- Note guideline references mentioned that need verification
    
- List specific management details requiring clarification
    
- Determine mechanistic concepts needing deeper explanation
    

**These gaps will guide OpenEvidence queries in Phase 3.**

---

## **PHASE 3: OPENEVIDENCE.COM RESEARCH & SYNTHESIS**

## **Step 3: Conduct OpenEvidence Queries**

**Critical Instructions:**

- Go to OpenEvidence.com
    
- Perform **real-time queries** to answer clinical questions
    
- **Expand search iteratively** - don't stop at first query
    
- Query types to perform:
    
    1. **Primary question** (main clinical topic)
        
    2. **Specific management details** (dosing, monitoring, timing)
        
    3. **Guideline synthesis** (current recommendations from major societies)
        
    4. **Supporting evidence** (systematic reviews, meta-analyses)
        
    5. **Mechanistic understanding** (pathophysiology)
        
    6. **Related clinical questions** identified from primary article
        

**Query Examples for VTE/TBI Topic:**

- "What is the evidence for early VTE prophylaxis in traumatic brain injury?"
    
- "What is the evidence for anti-Xa monitoring in TBI patients receiving enoxaparin prophylaxis?"
    
- "What are current ACS-TQIP and WTA guidelines for VTE prophylaxis timing in TBI?"
    
- "What is the risk of ICH progression with early LMWH in mild TBI?"
    

**Documentation Requirements:**

- Document date queries performed
    
- Synthesize findings (don't just copy)
    
- Integrate OpenEvidence synthesis directly into relevant template sections
    
- Use format: "OPENEVIDENCE SYNTHESIS: [key findings]"
    

---

## **PHASE 4: COMPLETE JOURNAL CLUB ANALYSIS**

## **Template Structure: Part I - Journal Club**

**1. PRESENTER INFORMATION**

- Presenter: [Name]
    
- Date: [Presentation Date]
    
- Institution: [Institution Name]
    
- Journal Club Title: [Full Article Title]
    
- Level of Evidence: [Type/Level]
    

**2. STUDY BACKGROUND AND OBJECTIVES**

**A. Clinical Problem / Knowledge Gap**

- What clinical problem exists?
    
- Current practice patterns
    
- Gaps in evidence
    
- **INSERT: OpenEvidence synthesis on current state of evidence**
    

**B. Rationale for Study**

- Why this study needed?
    
- Mechanistic rationale
    
- **INSERT: OpenEvidence synthesis on biological plausibility**
    

**C. Primary Objectives/Hypothesis**

- Primary hypothesis
    
- Primary aims
    
- Secondary aims
    

**3. STUDY DESIGN AND METHODOLOGY**

**A. Study Type**

- Design (RCT, cohort, case-control, etc.)
    
- Evidence level
    
- Setting
    
- Study period
    
- Reporting standards (CONSORT, STROBE, etc.)
    

**B. Population**

- Inclusion/exclusion criteria
    
- Sample size and groups
    
- Demographics (age, sex, injury severity)
    
- Key baseline characteristics
    

**C. Intervention / Exposure**

- Detailed intervention description
    
- **INSERT: OpenEvidence synthesis on standard protocols**
    
- Timing, dosing, monitoring
    

**D. Comparator / Control**

- Control/comparison group details
    
- Standard of care description
    

**E. Outcomes**

- Primary outcome(s) with definitions
    
- Secondary outcomes
    
- How measured
    

**F. Statistical Analyses**

- Tests used
    
- Adjustments for confounders
    
- Alpha level
    
- Software
    

**4. KEY RESULTS**

**A. Primary Outcome**

- Results with statistics
    
- Tables with clear formatting
    
- Effect sizes and confidence intervals
    
- **Use exact numbers from primary article**
    

**B. Secondary Outcomes**

- All secondary outcomes reported
    
- Clinical significance noted
    
- **Include all data from primary article tables**
    

**C. Major Statistical Findings**

- Adjusted vs unadjusted results
    
- Subgroup analyses
    
- Key statistics (OR, RR, HR, p-values, CI)
    

**5. CRITICAL APPRAISAL**

**A. Strengths**

- 7-10 specific strengths
    
- Reference OpenEvidence support for methods
    
- Note alignment with best practices
    

**B. Limitations**

- 7-10 specific limitations
    
- Study design limitations
    
- Generalizability concerns
    
- Potential biases
    
- Missing data issues
    

**C. Quality of Evidence**

- Level of evidence rating
    
- Risk of bias assessment
    
- **INSERT: Comparison to guideline recommendations from OpenEvidence**
    

**6. BIOLOGICAL PLAUSIBILITY**

- Mechanistic rationale
    
- Pathophysiology review
    
- **INSERT: OpenEvidence synthesis on mechanisms**
    
- Link between intervention and outcomes
    

**7. CLINICAL RELEVANCE & APPLICATION**

**A. Applicability to Practice**

- Who can use these findings?
    
- Practice change implications
    
- Patient population considerations
    

**B. Comparison to Guidelines/Standard Care**

- **INSERT: Comprehensive OpenEvidence guideline synthesis**
    
- How results align with or differ from guidelines
    
- Current recommendations from major societies (with years)
    
- Implications for existing protocols
    

**C. Barriers to Implementation**

- Cost, resource, training barriers
    
- Institutional considerations
    
- Cultural/practice barriers
    

**8. FUTURE RESEARCH DIRECTIONS**

- Unanswered questions from primary article
    
- Next research priorities
    
- Guideline change potential
    
- **INSERT: Research gaps identified via OpenEvidence**
    

**9. DISCUSSION QUESTIONS**

- 3-5 thought-provoking questions
    
- Application scenarios
    
- Controversial points
    
- Ethical considerations
    

---

## **PHASE 5: CHALK TALK DEVELOPMENT (ADDIE-I9 Framework)**

## **Part II Template Structure**

**PHASE 1: ANALYZE (Learning Needs)**

- **Audience:** [Level: medical students/interns/residents/fellows/attendings; clinical context]
    
- **General needs assessment:** [Core clinical/practice needs for this context]
    
- **Targeted needs assessment:** [Recent cases, questions, struggles on service]
    
- **Topic selection & scope:** [Narrow focus: diagnosis, management, procedure, trial]
    

**PHASE 2: DESIGN (Objectives & Board Map)**

**1. SMART Objectives** (1 per 5 minutes; max 5)

- Objective 1: [Specific, measurable, achievable, relevant, time-bound]
    
- Objective 2: [...]
    
- Objective 3: [...]
    
- Objective 4: [...]
    
- Objective 5: [...]
    

**2. Board Map Creation (Two-Panel Visual)**

**Panel 1 (Before/Scaffold):**

- What will be on the board at START of talk?
    
- Blank? Or pre-drawn complex diagrams/scaffolds?
    
- Consider: axes, tables, flowchart boxes, anatomic structures difficult to draw live
    
- List specific pre-drawn elements
    

**Panel 2 (After/Complete):**

- What will be on board at END of talk?
    
- All information recorded during session
    
- Graphics: diagrams, flowcharts, tables, annotations, abbreviations
    
- Consider: sequence, timing, memorable visuals central to learning goals
    
- Ask: Will learners photograph this for review?
    

**3. Board Map Design Questions:**

- How will graphics build and anchor discussion?
    
- What can be drawn spontaneously vs. must be pre-drawn?
    
- Does board layout match order of learning objectives?
    
- Is information organized (e.g., differential diagnoses grouped/ordered)?
    
- Too much text? Too little? Legible from distance?
    
- Color coding strategy?
    
- Flow direction (left-to-right, top-to-bottom)?
    

**PHASE 3: DEVELOPMENT (Prep & Practice)**

**1. Talking Points:**

- Link each point to board visuals
    
- Plan discussion-leading questions
    
- Interactive prompts
    
- Case-based scenarios
    

**2. Contingency Plans:**

- Abridged material if time short or more discussion needed
    
- Extra material to fill unexpected time
    
- Backup examples
    

**3. Practice:**

- Run-through timing (aim for target time)
    
- Video record if possible
    
- Self-review checklist
    
- Refinement based on review
    

**PHASE 4: IMPLEMENTATION (Gagné's Nine Events)**

1. **Gain Attention:** Clinical case hook or provocative question
    
2. **Inform Objectives:** State clearly, write on board if helpful
    
3. **Stimulate Recall:** "Has anyone seen [condition]? What was hard?"
    
4. **Present Content:** Build board interactively; record learner input strategically; face audience (not board); avoid erasing
    
5. **Provide Guidance:** Use discussion-leading questions; scaffold reasoning; fill gaps
    
6. **Elicit Performance:** Walk through new case or "How would you approach this now?"
    
7. **Provide Feedback:** Specific, actionable: "You said___," "You chose___"
    
8. **Assess Performance:** Apply to next similar case; explicitly reconnect to session objectives
    
9. **Enhance Retention/Transfer:** Summarize while reviewing final board; photograph board; relate to patient care tomorrow
    

**PHASE 5: EVALUATION**

- Collect feedback: useful? suggestions? unanswered questions?
    
- Save board map & script for teaching portfolio
    
- Iterate for future sessions
    
- Document learner outcomes
    

---

## **PHASE 6: CORE TEACHING ELEMENTS (Required Every Time)**

**1. Key Message/Punchline**

- Single-sentence clinical headline
    
- Memorable and actionable
    
- Example: "Early VTE prophylaxis (<24h) in BIG 1/2 TBI patients is SAFE (0% ICH progression in 634 patients) and EFFECTIVE (66% DVT reduction). Use weight-based enoxaparin with anti-Xa monitoring. Don't delay - START EARLY, PREVENT CLOTS, DON'T FEAR BLEEDS!"
    

**2. Mnemonic**

- Short, relevant, memorable acronym
    
- Ties to key teaching points
    
- Example: "BIG SAFE" for early VTE prophylaxis
    
    - **B**IG 1/2 classification
        
    - **I**nitiate early (<24h)
        
    - **G**uideline-supported
        
    - **S**afe (no ICH progression)
        
    - **A**nti-Xa monitoring
        
    - **F**ewer DVTs
        
    - **E**noxaparin weight-based
        

**3. Common Pitfalls & Misconceptions**

- Top 3-5 diagnostic/management errors
    
- **Use OpenEvidence to identify common practice gaps**
    
- Examples:
    
    - Delaying VTE prophylaxis due to bleeding fear
        
    - Not using weight-based dosing
        
    - Forgetting anti-Xa monitoring
        
    - Applying to wrong patient population
        

**4. Q&A or Roleplay Scenario**

- Interactive clinical scenario for application
    
- Decision-making prompts
    
- "What would you do next?" moments
    
- Error recognition exercises
    

**5. Top Pearls (3-5)**

- High-yield, actionable clinical tips
    
- Specific and practical
    
- Include dosing tables, protocols, algorithms
    
- Example format:
    
    - Pearl 1: Enoxaparin 0.5 mg/kg q12h for prophylaxis
        
    - Pearl 2: Target anti-Xa 0.2-0.4 IU/mL
        
    - Pearl 3: Start within 24h if stable repeat imaging
        

**6. Implementation Tips**

- Daily workflow checklist
    
- EHR integration notes (order sets, smart phrases)
    
- Rounds workflow integration
    
- Communication templates
    
- Practical "tomorrow on rounds" guidance
    

**7. Research Gaps & Future Directions**

- Unanswered questions from OpenEvidence synthesis
    
- Research priorities for the field
    
- Ongoing trials
    
- Guideline development areas
    

**8. References**

- Numbered citations matching in-text superscripts
    
- Include full URLs
    
- Date of OpenEvidence queries performed
    
- Primary article with DOI
    
- Key guidelines cited
    
- Format:
    
    1. Primary article full citation with PMID/DOI
        
    2. OpenEvidence queries [Date performed]
        
    3. Guidelines (ACS-TQIP, WTA, etc.) with year
        

---

## **PHASE 7: GOOGLE DOCS WORKFLOW**

## **AI Instructions for Document Creation:**

**Step 1: Navigate to Google Docs**

- Open existing document URL OR create new document
    
- Confirm editing mode (not suggesting or viewing mode)
    
- Check toolbar shows "Editing" dropdown
    

**Step 2: Structure Document**

- Insert all content directly into doc
    
- Use proper heading hierarchy:
    
    - Heading 1: Major sections (PART I, PART II)
        
    - Heading 2: Main subsections (1. PRESENTER INFORMATION)
        
    - Heading 3: Sub-subsections (A. Clinical Problem)
        
- Format tables clearly with borders
    
- Bold key findings and statistics
    

**Step 3: Progressive Content Building**

- Work section by section sequentially
    
- Don't ask permission for each section
    
- Complete entire template exhaustively
    
- Fill in all bracketed placeholders with actual content
    

**Step 4: Formatting Requirements**

- Use `═══════════` for major section dividers
    
- Use `───────────` for subsection dividers
    
- Use ★ for critical findings
    
- Bold all statistical findings (p-values, ORs, CIs, percentages)
    
- Create tables for comparative data using Google Docs table tool
    
- Use bullet points (- ) for lists
    
- Highlight "OPENEVIDENCE SYNTHESIS:" in bold
    
- Use | for table borders in text format when needed
    

**Step 5: Tables and Data Formatting**

- Create actual tables for comparative data
    
- Include:
    
    - Column headers with units
        
    - Row labels
        
    - All numerical data from primary article
        
    - P-values and confidence intervals
        
    - Effect sizes (OR, RR, HR)
        
- Example table structure:
    

text

`| Outcome | EARLY (≤24h) | LATE (>24h) | p-value | aOR (95% CI) |`

**Step 6: Final Review**

- Ensure all sections complete (no [placeholders] remaining)
    
- Check for consistency in formatting
    
- Verify OpenEvidence integrations documented with dates
    
- Add full date and authorship at top
    
- Proofread statistics match primary article exactly
    

---

## **KEY WORKFLOW PRINCIPLES**

## **For AI Execution:**

1. **Read Primary Source First:** Always read the complete PDF/article indicated by user using `get_page_text` before beginning any analysis
    
2. **Be Exhaustive:** Complete every section fully - no partial completion, no placeholders left unfilled
    
3. **Expand Searches:** Don't stop at first OpenEvidence query - iterate and expand with multiple related queries
    
4. **Synthesize, Don't Copy:** Integrate findings meaningfully, explain significance, connect to primary article
    
5. **Use Current Evidence:** Date all queries, use most recent guidelines (2024-2025)
    
6. **Quantify When Possible:** Include specific numbers, percentages, effect sizes, confidence intervals from primary article
    
7. **Direct Output:** Work directly in Google Docs without multiple confirmations for each section
    
8. **# **KEY WORKFLOW PRINCIPLES** (continued)

## **For AI Execution:**

1. **Read Primary Source First:** Always read the complete PDF/article indicated by user using `get_page_text` before beginning any analysis
    
2. **Be Exhaustive:** Complete every section fully - no partial completion, no placeholders left unfilled
    
3. **Expand Searches:** Don't stop at first OpenEvidence query - iterate and expand with multiple related queries
    
4. **Synthesize, Don't Copy:** Integrate findings meaningfully, explain significance, connect to primary article
    
5. **Use Current Evidence:** Date all queries, use most recent guidelines (2024-2025)
    
6. **Quantify When Possible:** Include specific numbers, percentages, effect sizes, confidence intervals from primary article
    
7. **Direct Output:** Work directly in Google Docs without multiple confirmations for each section
    
8. **Real-Time Research:** Actually query OpenEvidence.com - don't simulate or make up responses
    
9. **Document Sources:** Note all OpenEvidence queries performed with dates
    
10. **Sequential Process:**
    
    - First: Read primary article completely using `get_page_text`
        
    - Second: Perform OpenEvidence queries to expand evidence base
        
    - Third: Synthesize all sources into comprehensive template
        
    - Never skip step 1
        
11. **Extract Complete Data:** From primary article, extract ALL:
    
    - Sample sizes for each group
        
    - Baseline demographics
        
    - Primary and secondary outcomes with exact numbers
        
    - P-values, confidence intervals, effect sizes
        
    - Subgroup analyses
        
    - Figures and tables (describe content)
        
12. **No Assumptions:** If data not in primary article or OpenEvidence, note as "not reported" rather than guessing
    

## **Quality Standards:**

- **Comprehensive:** All template sections completed with substantive content
    
- **Evidence-based:** OpenEvidence synthesis integrated in minimum 5 sections
    
- **Quantitative:** Specific statistics and effect sizes throughout (no vague statements like "significantly different")
    
- **Current:** Most recent guidelines (2024-2025) from major organizations
    
- **Practical:** Implementation guidance that can be used tomorrow on rounds
    
- **Interactive:** Discussion questions that provoke critical thinking
    
- **Visual:** Board map specifications detailed enough to recreate
    
- **Referenced:** Complete citation list with URLs and query dates
    
- **Accurate:** All numbers verified against primary source
    

## **Minimum Integration Points for OpenEvidence:**

Must include OpenEvidence synthesis in at least these sections:

1. Study Background - current state of evidence
    
2. Rationale for Study - biological plausibility
    
3. Intervention description - standard protocols
    
4. Critical Appraisal - comparison to guidelines
    
5. Biological Plausibility - mechanistic understanding
    
6. Clinical Relevance - guideline recommendations
    
7. Future Research - identified gaps
    

---

## **EXAMPLE EXECUTION COMMAND**

**Simple Version:**  
"Using this workflow template, create a complete Journal Club and Chalk Talk presentation for [ARTICLE CITATION/URL]. Use OpenEvidence.com to expand the evidence base, synthesize current guidelines, and quantify the best available evidence. Work directly in Google Docs. Be exhaustive - complete all sections."

**Detailed Version:**  
"Execute full workflow for article: [ARTICLE CITATION/URL]

Instructions:

1. Read the complete article first using get_page_text
    
2. Create Google Doc titled '[Topic] - Journal Club & Chalk Talk - [Today's Date]'
    
3. Query OpenEvidence.com iteratively on:
    
    - Main clinical question
        
    - Management specifics (dosing, timing, monitoring)
        
    - Current guidelines (ACS-TQIP, WTA, BTF, etc.)
        
    - Supporting systematic reviews
        
    - Mechanistic understanding
        
4. Complete entire template:
    
    - Part I: Journal Club Analysis (all 9 sections)
        
    - Part II: Chalk Talk Development (all 5 phases)
        
    - Core Teaching Elements (all 8 components)
        
5. Include exact statistics from primary article
    
6. Document all OpenEvidence queries with dates
    
7. Create tables for comparative data
    
8. Format with proper headings, bold key findings
    
9. No placeholders - fill everything in completely
    

Target audience: [Residents/Fellows/Mixed]  
Institution: University of Virginia Health System, Trauma Surgery"

---

## **COMMON PITFALLS TO AVOID**

## **For AI Assistants:**

❌ **DON'T:**

- Skip reading the full primary article
    
- Stop after one OpenEvidence query
    
- Leave placeholder text like [Insert here]
    
- Use vague language ("there was a difference")
    
- Forget to document query dates
    
- Ask permission for each section
    
- Copy/paste without synthesis
    
- Make up statistics or guidelines
    
- Stop before template is complete
    

✅ **DO:**

- Read entire primary article first
    
- Perform 5-10 OpenEvidence queries minimum
    
- Fill in all sections completely
    
- Use specific numbers ("66% reduction, p=0.043")
    
- Date all OpenEvidence queries
    
- Work through entire template continuously
    
- Synthesize and explain significance
    
- Verify all data against sources
    
- Complete every section exhaustively
    

---

## **SECTION-BY-SECTION CHECKLIST**

## **Part I: Journal Club Analysis**

-  **Presenter Information:** All fields filled
    
-  **Clinical Problem:** 3-5 bullet points with OpenEvidence synthesis
    
-  **Rationale:** Mechanistic explanation with OpenEvidence support
    
-  **Objectives:** Primary and secondary aims clearly stated
    
-  **Study Type:** Complete design details from article
    
-  **Population:** Full inclusion/exclusion, demographics with N
    
-  **Intervention:** Detailed protocol with OpenEvidence comparison
    
-  **Comparator:** Control group fully described
    
-  **Outcomes:** All primary and secondary with definitions
    
-  **Statistics:** All tests, adjustments, alpha noted
    
-  **Primary Results:** Complete data with exact numbers
    
-  **Secondary Results:** All outcomes reported
    
-  **Statistical Findings:** ORs, RRs, CIs, p-values all included
    
-  **Strengths:** 7-10 specific strengths listed
    
-  **Limitations:** 7-10 specific limitations listed
    
-  **Quality of Evidence:** Level rating with guideline comparison
    
-  **Biological Plausibility:** Mechanism explained with OpenEvidence
    
-  **Clinical Relevance:** Application guidance specific
    
-  **Guideline Comparison:** OpenEvidence synthesis comprehensive
    
-  **Implementation Barriers:** 3-5 barriers identified
    
-  **Future Research:** Specific unanswered questions
    
-  **Discussion Questions:** 3-5 thought-provoking questions
    

## **Part II: Chalk Talk Development**

-  **Audience Analysis:** Specific level and context
    
-  **Needs Assessment:** General and targeted completed
    
-  **Topic Scope:** Narrowly focused
    
-  **SMART Objectives:** 3-5 objectives listed
    
-  **Board Map Panel 1:** Before state detailed
    
-  **Board Map Panel 2:** After state detailed
    
-  **Design Questions:** All 7 questions answered
    
-  **Talking Points:** Linked to visuals
    
-  **Contingency Plans:** Both scenarios planned
    
-  **Practice Plan:** Strategy outlined
    
-  **Gagné's 9 Events:** All events with specific examples
    
-  **Evaluation Plan:** Feedback method described
    

## **Core Teaching Elements**

-  **Key Message:** One-sentence punchline created
    
-  **Mnemonic:** Acronym developed and explained
    
-  **Pitfalls:** 3-5 errors identified with OpenEvidence support
    
-  **Q&A Scenario:** Interactive prompt written
    
-  **Top Pearls:** 3-5 actionable tips with specifics
    
-  **Implementation Tips:** Workflow integration detailed
    
-  **Research Gaps:** From OpenEvidence synthesis
    
-  **References:** Numbered with URLs and dates
    

---

## **OUTPUT FORMAT SPECIFICATIONS**

## **Google Docs Formatting:**

**Headings:**

text

`Heading 1: PART I: JOURNAL CLUB ANALYSIS Heading 2: 1. PRESENTER INFORMATION Heading 3: A. Clinical Problem / Knowledge Gap`

**Dividers:**

text

`═══════════════════════════════════════════════════════ PART I: JOURNAL CLUB ANALYSIS ═══════════════════════════════════════════════════════`

**Key Findings:**

text

`★ CRITICAL FINDING: Early prophylaxis reduces DVT by 66% (aOR 0.341, 95% CI 0.121-0.783, p=0.043)`

**OpenEvidence Integration:**

text

`OPENEVIDENCE SYNTHESIS: ACS-TQIP 2024 recommends VTE prophylaxis within 24h for BIG 1, 24-48h for BIG 2 with stable repeat imaging. Early chemoprophylaxis reduces VTE without increasing ICH progression (Date queried: November 12, 2025).`

**Tables:**

text

`| Outcome | EARLY (≤24h) | LATE (>24h) | p-value | aOR (95% CI) | |---------|-------------|-------------|---------|--------------| | DVT     | 4/393 (1.0%)| 12/241 (4.9%)| 0.020  | 0.341 (0.121-0.783) | | PE      | 2/393 (0.5%)| 3/241 (1.2%) | 0.309  | Not significant |`

**Statistics Format:**

text

`- Always include: numerator/denominator (percentage) - Always include: p-values - Always include: confidence intervals when available - Always include: effect sizes (OR, RR, HR, ARR, NNT) - Example: 4/393 (1.0%) vs 12/241 (4.9%), p=0.020, aOR 0.341 (95% CI 0.121-0.783)`

text

`1. Villarin Ayala S, et al. Early Venous Thromboembolism Prophylaxis in Brain Injury Guidelines 1 and Brain Injury Guidelines 2 Traumatic Brain Injury Patients: A 5-Year Analysis. J Trauma Acute Care Surg. 2025;99:709-714. PMID: 39012683. DOI: 10.1097/TA.0000000000004508 2. OpenEvidence.com queries performed November 12, 2025:    - "Early VTE prophylaxis traumatic brain injury evidence"   - "Anti-Xa monitoring TBI enoxaparin"   - "ACS-TQIP WTA guidelines VTE prophylaxis timing TBI" 3. ACS-TQIP Guidelines for VTE Prophylaxis in Trauma Patients. 2024. https://www.facs.org/quality-programs/trauma/tqip/`

---

## **SPECIAL INSTRUCTIONS FOR COMPLEX ARTICLES**

## **For Multi-Arm Studies:**

- Create separate tables for each comparison
    
- Report all pairwise comparisons
    
- Note which comparisons were pre-specified
    

## **For Meta-Analyses:**

- Extract data from forest plots
    
- Report heterogeneity (I², Q-test)
    
- Note fixed vs random effects
    
- Report publication bias assessment
    
- Describe subgroup analyses
    

## **For RCTs:**

- Report randomization method
    
- Note allocation concealment
    
- Report blinding (participants, providers, assessors)
    
- Include CONSORT flow diagram description
    
- Report intention-to-treat vs per-protocol
    
- Note stopping rules if early termination
    

## **For Systematic Reviews:**

- Report search strategy databases
    
- Note inclusion/exclusion criteria
    
- Report quality assessment tool used
    
- Describe certainty of evidence (GRADE)
    
- Note funding sources and conflicts
    

---

## **ADAPTATION FOR DIFFERENT SPECIALTIES**

## **Trauma Surgery (Default):**

- Emphasize injury severity scores (ISS, AIS)
    
- Include mechanism of injury
    
- Note trauma center level
    
- Reference EAST, ACS-TQIP, WTA guidelines
    
- Include ICU and operative details
    

## **Critical Care:**

- Emphasize APACHE/SOFA scores
    
- Include ventilator parameters
    
- Note vasoactive medications
    
- Reference SCCM guidelines
    
- Include mortality outcomes
    

## **Emergency Medicine:**

- Emphasize ED-relevant outcomes
    
- Include disposition decisions
    
- Note diagnostic accuracy
    
- Reference ACEP guidelines
    
- Include risk stratification tools
    

## **General Surgery:**

- Emphasize operative details
    
- Include Clavien-Dindo classification
    
- Note surgical technique specifics
    
- Reference ACS NSQIP data
    
- Include complications and reoperation rates
    

---

## **FINAL CHECKLIST BEFORE COMPLETION**

-  Primary article read completely via `get_page_text`
    
-  Minimum 5 OpenEvidence queries performed and documented
    
-  All 9 Journal Club sections completed
    
-  All 5 ADDIE-I9 phases completed
    
-  All 8 Core Teaching Elements included
    
-  All statistics verified against primary article
    
-  All tables properly formatted with data
    
-  All OpenEvidence syntheses dated
    
-  All references numbered and linked
    
-  No placeholder text remaining
    
-  Document titled appropriately
    
-  Proper heading hierarchy throughout
    
-  Key findings bolded/marked with ★
    
-  Tables have borders and are legible
    
-  Statistics include numerators, denominators, percentages, p-values, CIs
    
-  Implementation guidance specific and actionable
    
-  Board map panels both detailed
    
-  Mnemonic created and explained
    
-  Discussion questions thought-provoking
    
-  Word count substantial (typically 5,000-8,000 words for complete template)
    

---

## **END OF WORKFLOW TEMPLATE**

**Version:** 2.0  
**Last Updated:** November 12, 2025  
**Created For:** University of Virginia Health System, Department of Surgery  
**Author:** Trauma and Acute Care Surgery Education

---

**TEMPLATE READY FOR AI EXECUTION**

This template is designed for comprehensive, evidence-based medical education content creation with integration of real-time literature synthesis and direct output to collaborative documents.