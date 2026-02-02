# UVA ATTENDING ATTESTATION SYSTEM v3.1

## SYSTEM OVERVIEW

This document is the single source of truth for the UVA Attending Auto-Attestation and Billing system. All attestations are **MDM-based** except Critical Care (time-based).

---

## MASTER MENU STRUCTURE: EDATT [54319]

```
EDATT [54319]
│
├── EDATTEGS [54320]
│   ├── EGS MDM INITIAL [55645]
│   │   ├── EDATTEGSMDMINITLOW [984709] → 99221
│   │   ├── EDATTEGSMDMINITMOD [984710] → 99222
│   │   └── EDATTEGSMDMINITHIGH [984711] → 99223
│   │
│   └── EGS MDM SUBSEQUENT [55646]
│       ├── EDATTEGSMDMSUBLOW [984712] → 99231
│       ├── EDATTEGSMDMSUBMOD [984713] → 99232
│       └── EDATTEGSMDMSUBHIGH [984714] → 99233
│
├── EDATTTRAUMAMDM [54321]
│   ├── TRAUMA ACTIVATIONS
│   │   ├── EDATTTRAUMAALPHA [984736] → 99223
│   │   ├── EDATTTRAUMABETA [984735] → 99223
│   │   └── EDATTTRAUMAGAMMA [984734] → 99222
│   │
│   ├── TRAUMA INITIAL LOW
│   │   └── EDATTTRAUMAMDMINITLOW [984719] → 99221
│   │
│   └── TRAUMA SUBSEQUENT
│       ├── EDATTTRAUMAMDMSUBLOW [984722] → 99231
│       ├── EDATTTRAUMAMDMSUBMOD [984723] → 99232
│       └── EDATTTRAUMAMDMSUBHIGH [984724] → 99233
│
├── EDATTCCSPLITSIMU [55649]
│   ├── EDATTCC [976294] → 99291/99292 (TIME)
│   ├── EDATTCCSPLITSHARE [984739] → 99291/99292 (TIME)
│   └── EDATTSIMU [984738] → 99232 (MDM)
│
├── EDATTDC → 99239 (TIME)
│
└── EDATTOPERATIVE → CPT-based (unchanged)
```

---

## ROUTING LOGIC

| Note Type | Template | Code | Billing Basis |
|-----------|----------|------|---------------|
| EGS consult/H&P - low | EDATTEGSMDMINITLOW | 99221 | MDM |
| EGS consult/H&P - moderate | EDATTEGSMDMINITMOD | 99222 | MDM |
| EGS consult/H&P - high | EDATTEGSMDMINITHIGH | 99223 | MDM |
| EGS floor daily - low | EDATTEGSMDMSUBLOW | 99231 | MDM |
| EGS floor daily - moderate | EDATTEGSMDMSUBMOD | 99232 | MDM |
| EGS floor daily - high | EDATTEGSMDMSUBHIGH | 99233 | MDM |
| Trauma Alpha | EDATTTRAUMAALPHA | 99223 | MDM |
| Trauma Beta | EDATTTRAUMABETA | 99223 | MDM |
| Trauma Gamma | EDATTTRAUMAGAMMA | 99222 | MDM |
| Trauma initial low | EDATTTRAUMAMDMINITLOW | 99221 | MDM |
| Trauma floor daily - low | EDATTTRAUMAMDMSUBLOW | 99231 | MDM |
| Trauma floor daily - moderate | EDATTTRAUMAMDMSUBMOD | 99232 | MDM |
| Trauma floor daily - high | EDATTTRAUMAMDMSUBHIGH | 99233 | MDM |
| ICU critical care | EDATTCC | 99291/99292 | TIME |
| ICU split/share | EDATTCCSPLITSHARE | 99291/99292 | TIME |
| SIMU step-down | EDATTSIMU | 99232 | MDM |
| SIMU with systems note | EDATTCCSIMUSYSTEMS | 99232 | MDM |
| Discharge (>30 min) | EDATTDC | 99239 | TIME |
| Operative | EDATTOPERATIVE | CPT | Procedure |

---

## SMARTLISTS REFERENCE

| SmartList | ID | Purpose |
|-----------|-----|---------|
| {EDATTCCDX:54798} | 54798 | Critical care diagnoses |
| {EDATTCCSVCS:54356} | 54356 | Critical care services rendered |
| {EDBILLCCMENU:54470} | 54470 | Critical care time buckets (99291/99292) |
| {MRN trauma diagnoses:50834} | 50834 | Trauma injury list |
| {mrn response time:50839} | 50839 | Trauma response time (Alpha/Beta only) |
| {does or does not:50840} | 50840 | Boolean for hospitalization/OR/admission |
| {N/APOSTOP:55824} | 55824 | POD/HOD selector |

---

## HARD RULES

1. **No em dashes** - Use only standard hyphens
2. **No tabs** - ASCII only, left-justified
3. **Preserve SmartLinks/SmartLists exactly** - Do not alter token names or IDs
4. **Source of truth** - Only use information explicitly in the pasted note
5. **Never fabricate** - Do not invent diagnoses, labs, vitals, or events
6. **Respect user billing constraints** - If user specifies time/code, use exactly that
7. **EDATTCCSIMUSYSTEMS first section** - MUST be <1500 characters total
8. **Conditional data bullets** - Only include "independently reviewed and interpreted imaging studies" when imaging is present in the source note. Do not include imaging review language for notes without imaging.
9. **CC time bucket selection** - 30-74 min = 99291 only; 75-104 min = 99291 + one 99292; 105-134 min = 99291 + two 99292; each additional 30 min = +1 unit 99292

---

## PHRASE TEMPLATES

---

### EGS INITIAL

---

#### EDATTEGSMDMINITLOW [984709] - 99221

```
ATTENDING ATTESTATION

I independently evaluated the patient today and reviewed the resident/APP documentation. I agree with the documented history, physical examination, assessment, and plan with the following additions/clarifications:

MEDICAL DECISION MAKING

1. Problem(s) Addressed:
See above for problems and plan

2. Data Reviewed and Analyzed:
I reviewed laboratory results and imaging studies obtained during this encounter. I reviewed the nursing assessment and vital sign trends.

3. Risk of Complications/Morbidity:
Low risk.

MDM Summary: Low complexity MDM based on acute uncomplicated illness or stable chronic condition with limited data review and low-risk management.

Hospitalization is medically necessary for monitoring, diagnostic workup, and treatment of the above condition(s).

From a surgical standpoint, the patient {does or does not 50840:"does"} require hospitalization, {does or does not 50840:"does not"} emergent operative intervention and {does or does not 50840:"does not"} require admission under the EGS service; admission location/discharge disposition per plan.

I discussed the diagnosis, treatment options, and expected clinical course with the patient and/or family.

E/M Billing: 99221 - Initial hospital care, low MDM

@EDSIG@
```

---

#### EDATTEGSMDMINITMOD [984710] - 99222

```
ATTENDING ATTESTATION

I independently evaluated the patient today and reviewed the resident/APP documentation. I agree with the documented history, physical examination, assessment, and plan with the following additions/clarifications:

MEDICAL DECISION MAKING

1. Problem(s) Addressed:
See above for problems and plan

2. Data Reviewed and Analyzed:
I independently reviewed and interpreted laboratory results. I independently reviewed and interpreted imaging studies. I reviewed prior medical records and external documentation. I discussed findings and management plan with consulting services.

3. Risk of Complications/Morbidity:
Moderate risk.

MDM Summary: Moderate complexity MDM based on acute illness with systemic symptoms requiring moderate data analysis and moderate-risk management decisions.

Hospitalization is medically necessary for monitoring, diagnostic workup, and treatment of the above condition(s).

From a surgical standpoint, the patient {does or does not 50840:"does"} require hospitalization, {does or does not 50840:"does not"} emergent operative intervention and {does or does not 50840:"does not"} require admission under the EGS service; admission location/discharge disposition per plan.

I discussed the diagnosis, treatment options, risks and benefits of surgical vs non-operative management, and expected clinical course with the patient and/or family.

E/M Billing: 99222 - Initial hospital care, moderate MDM

@EDSIG@
```

---

#### EDATTEGSMDMINITHIGH [984711] - 99223

```
ATTENDING ATTESTATION

I independently evaluated the patient today and reviewed the resident/APP documentation. I agree with the documented history, physical examination, assessment, and plan with the following additions/clarifications:

MEDICAL DECISION MAKING

1. Problem(s) Addressed:
See above for problems and plan

2. Data Reviewed and Analyzed:
I independently reviewed and interpreted laboratory results. I independently reviewed and interpreted imaging studies. I reviewed prior medical records, external documentation, and OSH records. I discussed findings, diagnosis, and management with anesthesiology, critical care, and relevant consulting services.

3. Risk of Complications/Morbidity:
High risk.

MDM Summary: High complexity MDM based on acute illness posing threat to life or bodily function requiring extensive data analysis and high-risk management.

Hospitalization is medically necessary for monitoring, diagnostic workup, and treatment of the above condition(s).

From a surgical standpoint, the patient {does or does not 50840:"does"} require hospitalization, {does or does not 50840:"does not"} emergent operative intervention and {does or does not 50840:"does not"} require admission under the EGS service; admission location/discharge disposition per plan.

I discussed the diagnosis, need for surgery, surgical risks including bleeding, infection, injury to adjacent structures, need for ostomy, and possibility of death, as well as alternative treatments with the patient and/or family. Informed consent obtained.

E/M Billing: 99223 - Initial hospital care, high MDM

@EDSIG@
```

---

### EGS SUBSEQUENT

---

#### EDATTEGSMDMSUBLOW [984712] - 99231

```
ATTENDING ATTESTATION

I examined the patient today and reviewed the resident/APP note, interval labs, imaging, and overnight events. I agree with the documented assessment and plan with the following additions/clarifications:

MEDICAL DECISION MAKING

1. Problem(s) Addressed:
See above for problems and plan

2. Data Reviewed and Analyzed:
I reviewed interval laboratory results and vital sign trends. I reviewed nursing documentation and patient-reported symptoms.

3. Risk of Complications/Morbidity:
Low risk.

MDM Summary: Low complexity MDM for stable or improving condition with limited data review and low-risk management.

Continued hospitalization {does or does not 50840:"does"} remain medically necessary for ongoing monitoring and treatment.

E/M Billing: 99231 - Subsequent hospital care, low MDM

@EDSIG@
```

---

#### EDATTEGSMDMSUBMOD [984713] - 99232

```
ATTENDING ATTESTATION

I examined the patient today and reviewed the resident/APP note, interval labs, imaging, and overnight events. I agree with the documented assessment and plan with the following additions/clarifications:

MEDICAL DECISION MAKING

1. Problem(s) Addressed:
See above for problems and plan

2. Data Reviewed and Analyzed:
I independently reviewed and interpreted interval laboratory results. I independently reviewed and interpreted new or repeat imaging studies. I reviewed nursing documentation, I/Os, and vital sign trends. I discussed patient status and care coordination with consulting services and/or primary team.

3. Risk of Complications/Morbidity:
Moderate risk.

MDM Summary: Moderate complexity MDM for acute illness with systemic symptoms requiring moderate data analysis and ongoing moderate-risk management decisions.

Continued hospitalization {does or does not 50840:"does"} remain medically necessary for ongoing monitoring and treatment.

E/M Billing: 99232 - Subsequent hospital care, moderate MDM

@EDSIG@
```

---

#### EDATTEGSMDMSUBHIGH [984714] - 99233

```
ATTENDING ATTESTATION

I examined the patient today and reviewed the resident/APP note, interval labs, imaging, and overnight events. I agree with the documented assessment and plan with the following additions/clarifications:

MEDICAL DECISION MAKING

1. Problem(s) Addressed:
See above for problems and plan

2. Data Reviewed and Analyzed:
I independently reviewed and interpreted interval laboratory results. I independently reviewed and interpreted new or repeat imaging studies. I reviewed nursing documentation, hemodynamic parameters, and resuscitation endpoints. I discussed patient status and management with critical care, anesthesiology, and relevant consulting services.

3. Risk of Complications/Morbidity:
High risk.

MDM Summary: High complexity MDM for acute illness posing threat to life or bodily function requiring extensive data analysis and high-risk management decisions.

Continued hospitalization {does or does not 50840:"does"} remain medically necessary for ongoing monitoring and treatment.

E/M Billing: 99233 - Subsequent hospital care, high MDM

@EDSIG@
```

---

### TRAUMA ACTIVATIONS

---

#### EDATTTRAUMAALPHA [984736] - 99223

```
TRAUMA ATTENDING ATTESTATION - ALPHA ACTIVATION

{mrn response time 50839:"I was present prior to patient arrival to the trauma bay"}
I independently evaluated this trauma patient and directed the resuscitation. I was present for and directed the primary and secondary survey, reviewed imaging and laboratory studies, and confirmed the documented injuries and management plan.

Injuries identified:
{MRN trauma diagnoses:50834}

MEDICAL DECISION MAKING

1. Problem(s) Addressed:
See above for problems and plan

2. Data Reviewed and Analyzed:
I independently reviewed and interpreted laboratory results including point-of-care testing and blood gas analysis. I independently reviewed and interpreted all imaging studies. I reviewed EMS documentation, field vitals, prehospital interventions, mechanism of injury, and OSH records. I discussed injury pattern, resuscitation strategy, operative planning, and resource mobilization with anesthesiology, critical care, blood bank, OR staff, and relevant surgical subspecialties. Massive transfusion protocol and/or emergent OR resources coordinated as indicated.

3. Risk of Complications/Morbidity:
High risk.

MDM Summary: High complexity MDM based on severe traumatic injuries with immediate threat to life requiring extensive data analysis, rapid decision-making, and high-risk emergent interventions.

Emergent hospitalization and intensive monitoring required for life threatening traumatic injuries with high risk of decompensation, hemorrhage, and multi organ failure.

From a trauma standpoint, the patient {does or does not 50840:"does"} require hospitalization or emergent operative intervention and {does or does not 50840:"does"} require admission under the trauma service; admission location/discharge disposition per plan.

I discussed the critical nature of injuries, need for emergent intervention, high risk of morbidity and mortality, and prognosis with the patient and/or family as able.

E/M Billing: 99223 - Initial hospital care, high MDM

@EDSIG@
```

---

#### EDATTTRAUMABETA [984735] - 99223

```
TRAUMA ATTENDING ATTESTATION - BETA ACTIVATION

{mrn response time 50839:"I was present prior to patient arrival to the trauma bay"}
I independently evaluated this trauma patient and directed the resuscitation. I was present for and directed the primary and secondary survey, reviewed imaging and laboratory studies, and confirmed the documented injuries and management plan.

Injuries identified:
{MRN trauma diagnoses:50834}

MEDICAL DECISION MAKING

1. Problem(s) Addressed:
See above for problems and plan

2. Data Reviewed and Analyzed:
I independently reviewed and interpreted laboratory results. I independently reviewed and interpreted imaging studies. I reviewed EMS documentation, field vitals, mechanism of injury, and OSH records if applicable. I discussed injury pattern, resuscitation, and management with anesthesiology, critical care, and relevant surgical subspecialties.

3. Risk of Complications/Morbidity:
High risk.

MDM Summary: High complexity MDM based on traumatic injuries posing threat to life or bodily function requiring extensive data analysis and high risk management.

Hospitalization is medically necessary for monitoring, diagnostic workup, and treatment of the above condition(s).

From a trauma standpoint, the patient {does or does not 50840:"does"} require hospitalization or emergent operative intervention and {does or does not 50840:"does"} require admission under the trauma service; admission location/discharge disposition per plan.

I discussed the injury severity, need for surgery and/or ICU admission, risks including bleeding, organ failure, and death, and prognosis with the patient and/or family.

E/M Billing: 99223 - Initial hospital care, high MDM

@EDSIG@
```

---

#### EDATTTRAUMAGAMMA [984734] - 99222

```
TRAUMA ATTENDING ATTESTATION - GAMMA ACTIVATION

I independently evaluated this trauma patient and reviewed the resident/APP documentation. I was present for or performed the primary and secondary survey, reviewed imaging and laboratory studies, and confirmed the documented injuries and management plan.

Injuries identified:
{MRN trauma diagnoses:50834}

MEDICAL DECISION MAKING

1. Problem(s) Addressed:
See above for problems and plan

2. Data Reviewed and Analyzed:
I independently reviewed and interpreted laboratory results. I independently reviewed and interpreted imaging studies. I reviewed EMS documentation, mechanism of injury, and OSH records if applicable. I discussed injury pattern and management with consulting services.

3. Risk of Complications/Morbidity:
Moderate risk.

MDM Summary: Moderate complexity MDM based on acute complicated traumatic injury requiring moderate data analysis and moderate-risk management decisions.

Hospitalization is medically necessary for monitoring, diagnostic workup, and treatment of the above condition(s).

From a trauma standpoint, the patient {does or does not 50840:"does"} require hospitalization, {does or does not 50840:"does not"} emergent operative intervention and {does or does not 50840:"does"} require admission under the Trauma service; admission location/discharge disposition per plan.

I discussed the injury pattern, treatment plan, potential need for surgery, and expected clinical course with the patient and/or family.

E/M Billing: 99222 - Initial hospital care, moderate MDM

@EDSIG@
```

---

#### EDATTTRAUMAMDMINITLOW [984719] - 99221

```
ATTENDING ATTESTATION

I independently evaluated this trauma patient and reviewed the resident/APP documentation. I was present for or performed the primary and secondary survey, reviewed imaging and laboratory studies, and confirmed the documented injuries and management plan.

MEDICAL DECISION MAKING

1. Problem(s) Addressed:
See above for problems and plan

2. Data Reviewed and Analyzed:
I reviewed laboratory results and imaging studies obtained during trauma evaluation. I reviewed EMS documentation and mechanism of injury.

3. Risk of Complications/Morbidity:
Low risk.

MDM Summary: Low complexity MDM based on minor traumatic injury with limited data review and low-risk management.

Hospitalization is medically necessary for monitoring, diagnostic workup, and treatment of the above condition(s).

From a trauma standpoint, the patient {does or does not 50840:"does"} require hospitalization, {does or does not 50840:"does not"} emergent operative intervention and {does or does not 50840:"does"} require admission under the Trauma service; admission location/discharge disposition per plan.

I discussed the injury pattern, expected clinical course, and discharge criteria with the patient and/or family.

E/M Billing: 99221 - Initial hospital care, low MDM

@EDSIG@
```

---

### TRAUMA SUBSEQUENT

---

#### EDATTTRAUMAMDMSUBLOW [984722] - 99231

```
ATTENDING ATTESTATION

I examined the patient today and reviewed the resident/APP note, interval labs, imaging, and overnight events. I agree with the documented assessment and plan with the following additions/clarifications:

MEDICAL DECISION MAKING

1. Problem(s) Addressed:
See above for problems and plan

2. Data Reviewed and Analyzed:
I reviewed interval laboratory results and vital sign trends. I reviewed nursing documentation, pain scores, and mobility status.

3. Risk of Complications/Morbidity:
Low risk.

MDM Summary: Low complexity MDM for stable minor traumatic injury with limited data review and low-risk management.

Continued hospitalization {does or does not 50840:"does"} remain medically necessary for ongoing monitoring and treatment.

Tertiary survey: Complete/negative for additional injuries.
VTE prophylaxis: Per protocol.
PT/OT: As indicated.

E/M Billing: 99231 - Subsequent hospital care, low MDM

@EDSIG@
```

---

#### EDATTTRAUMAMDMSUBMOD [984723] - 99232

```
ATTENDING ATTESTATION

I examined the patient today and reviewed the resident/APP note, interval labs, imaging, and overnight events. I agree with the documented assessment and plan with the following additions/clarifications:

MEDICAL DECISION MAKING

1. Problem(s) Addressed:
See above for problems and plan

2. Data Reviewed and Analyzed:
I independently reviewed and interpreted interval laboratory results. I independently reviewed and interpreted follow-up imaging studies. I reviewed nursing documentation, hemodynamic trends, and clinical trajectory. I discussed patient status and care coordination with consulting services.

3. Risk of Complications/Morbidity:
Moderate risk.

MDM Summary: Moderate complexity MDM for acute complicated traumatic injury requiring moderate data analysis and ongoing assessment for clinical trajectory.

Continued hospitalization {does or does not 50840:"does"} remain medically necessary for ongoing monitoring and treatment.

Tertiary survey: Complete/findings addressed.
VTE prophylaxis: Per protocol.
PT/OT: Following, progressing mobility as tolerated.

E/M Billing: 99232 - Subsequent hospital care, moderate MDM

@EDSIG@
```

---

#### EDATTTRAUMAMDMSUBHIGH [984724] - 99233

```
ATTENDING ATTESTATION

I examined the patient today and reviewed the resident/APP note, interval labs, imaging, and overnight events. I agree with the documented assessment and plan with the following additions/clarifications:

MEDICAL DECISION MAKING

1. Problem(s) Addressed:
See above for problems and plan

2. Data Reviewed and Analyzed:
I independently reviewed and interpreted interval laboratory results. I independently reviewed and interpreted new or repeat imaging studies. I reviewed nursing documentation, hemodynamic parameters, resuscitation endpoints, and ventilator data. I discussed patient status and management with critical care, anesthesiology, blood bank, and relevant surgical subspecialties.

3. Risk of Complications/Morbidity:
High risk.

MDM Summary: High complexity MDM for traumatic injuries posing ongoing threat to life or bodily function requiring extensive data analysis and high-risk management decisions.

Continued hospitalization {does or does not 50840:"does"} remain medically necessary for ongoing monitoring and treatment.

E/M Billing: 99233 - Subsequent hospital care, high MDM

@EDSIG@
```

---

### CRITICAL CARE (TIME-BASED)

---

#### EDATTCC [976294] - 99291/99292

```
ICU ATTENDING PROGRESS NOTE

@NAME@ - MRN @MRN@ - @AGE@ @GENDERID@ @HOSPITALDAY@ for*** {N/APOSTOP:55824}

N: ***
CV: ***
P: ***
GI: ***
R: ***
H: ***
ID: ***
Lines: ***
Dispo: ICU, ***

ATTENDING ATTESTATION - CRITICAL CARE

I saw the patient on @TODAYDATE@***

The patient was critically ill due to {EDATTCCDX:54798}.

Time reflects my independent, non-overlapping critical care on the unit/floor, excluding time for separately reportable procedures and general teaching.

Diagnoses under active critical care: {EDATTCCDX:54798}.

Services included today: {EDATTCCSVCS:54356}

E/M time billing: Critical care (99291/99292 - select by time): {EDBILLCCMENU:54470}

Medical Decision Making Summary:
@MDMCODING@

@EDSIG@
```

---

#### EDATTCCSPLITSHARE [984739] - 99291/99292

```
ATTENDING ATTESTATION - CRITICAL CARE SPLIT/SHARE

I personally saw and examined the patient with the APP. I DID perform the substantive portion of the critical care services. I reviewed and edited as needed the above note, and agree with the documented findings and plan of care.

I contributed to patient care in the following way: ***

I saw the patient on @TODAYDATE@***

The patient was critically ill due to {EDATTCCDX:54798}.

Time reflects my independent, non-overlapping critical care on the unit/floor, excluding time for separately reportable procedures and general teaching.

Diagnoses under active critical care: {EDATTCCDX:54798}.

Services included today: {EDATTCCSVCS:54356}

MEDICAL DECISION MAKING

1. Problem(s) Addressed:
See above for problems and plan

2. Data Reviewed and Analyzed:
I independently reviewed and interpreted interval laboratory results. I independently reviewed and interpreted imaging studies. I reviewed nursing documentation, hemodynamic parameters, and resuscitation endpoints. I discussed patient status and management with critical care, anesthesiology, and relevant consulting services.

3. Risk of Complications/Morbidity:
High risk.

MDM Summary: High complexity MDM for critically ill patient posing ongoing threat to life or bodily function requiring extensive data analysis and high-risk management decisions.

Physician Critical Care Time: *** min
Total Critical Care Time: *** min

E/M time billing: Critical care (99291/99292 - select by time): {EDBILLCCMENU:54470}

@EDSIG@
```

---

### SIMU (MDM-BASED)

---

#### EDATTSIMU [984738] - 99232

```
ATTENDING ATTESTATION - SIMU

I saw the patient on @TODAYDATE@

I examined the patient today and reviewed the resident/APP note, interval labs, imaging, and overnight events. I agree with the documented assessment and plan with the following additions/clarifications:

The patient is on the surgical intermediate unit for close monitoring of ***

MEDICAL DECISION MAKING

1. Problem(s) Addressed:
See above for problems and plan

2. Data Reviewed and Analyzed:
I independently reviewed and interpreted interval laboratory results. I independently reviewed and interpreted imaging studies. I reviewed nursing documentation, vital sign trends, and clinical trajectory. I discussed patient status and care coordination with consulting services as indicated.

3. Risk of Complications/Morbidity:
Moderate risk.

MDM Summary: Moderate complexity MDM for surgical patient requiring intermediate-level monitoring with moderate-risk management decisions.

Continued hospitalization {does or does not 50840:"does"} remain medically necessary for ongoing monitoring and treatment.

E/M Billing: 99232 - Subsequent hospital care, moderate MDM

@EDSIG@
```

---

#### EDATTCCSIMUSYSTEMS (CUSTOM TEMPLATE) - 99232

**HARD RULE: First section (one-liner + systems) MUST be <1500 characters total**

```
SICU ATTENDING PROGRESS NOTE

[Name] - MRN [MRN] - [Age][Sex] [HOD/POD] s/p [procedure(s)] [date] for [indication]; c/b [complications]. [Location/status].

N: [Neuro, pain, delirium]
CV: [Hemodynamics, rhythm, pressors]
P: [O2/vent status]
GI: [Diet, bowel, drains]
R: [Renal, UOP, dialysis]
H: [Hgb, anticoag]
ID: [Temp, WBC, abx]
Endo: [If relevant]
Lines: [Active lines/drains]
Dispo: [Unit, barriers, plan]

(END FIRST SECTION - MUST BE <1500 CHARACTERS)

ATTENDING ATTESTATION - SIMU

I saw the patient on [DATE]

I examined the patient today and reviewed the resident/APP note, interval labs, imaging, and overnight events. I agree with the documented assessment and plan with the following additions and clarifications:

The patient is on the surgical intermediate unit for close monitoring of: [specific clinical issues].

MEDICAL DECISION MAKING

1. Problem(s) Addressed: [Concise list]

2. Data Reviewed and Analyzed: I independently reviewed and interpreted interval laboratory results. I independently reviewed and interpreted imaging studies. I reviewed nursing documentation, vital sign trends, and clinical trajectory. I discussed patient status and care coordination with consulting services as indicated.

3. Risk of Complications/Morbidity: Moderate risk.

MDM Summary: Moderate complexity MDM for surgical patient requiring intermediate-level monitoring with moderate-risk management decisions.

Continued hospitalization does remain medically necessary for ongoing monitoring and treatment.

E/M Billing: 99232 - Subsequent hospital care, moderate MDM

Evan DeCan MD
Assistant Professor: University of Virginia School of Medicine
Trauma surgery, Emergency General Surgery, Surgical Critical Care
```

---

### DISCHARGE

---

#### EDATTDC - 99239

```
ATTENDING ATTESTATION - DISCHARGE

I independently evaluated the patient today, reviewed the hospital course, and performed the discharge assessment. I reviewed and agree with the discharge summary, medication reconciliation, and follow-up plan with the following additions/clarifications:

Hospital Course Summary: ***

Discharge condition: ***

Time spent on discharge day activities: *** min
Activities included: final examination, review of pending results, medication reconciliation, discharge instructions and counseling, coordination of follow-up care, and communication with patient/family.

Total physician time on discharge: >30 minutes

E/M Billing: 99239 - Hospital discharge day management, >30 minutes

@EDSIG@
```

---

## OUTPUT STRUCTURE

For every attestation request, respond with:

1. **Attestation Text - Ready for EPIC**
   - Template label at top: "Attestation template used: [TEMPLATE NAME]"
   - Exactly formatted attestation with SmartLinks intact

2. **Billing Summary (for you, not for chart)**
   - Setting and service
   - Template used
   - Code and billing basis
   - 2-4 bullet justification

3. **Character count** (for EDATTCCSIMUSYSTEMS only - verify <1500)

---

## SIGNATURE BLOCK

@EDSIG@ resolves to:
```
Evan DeCan MD
Assistant Professor: University of Virginia School of Medicine
Trauma surgery, Emergency General Surgery, Surgical Critical Care
```

---

## TOTAL ACTIVE TEMPLATES: 18

| Category | Count | Templates |
|----------|-------|-----------|
| EGS Initial | 3 | LOW, MOD, HIGH |
| EGS Subsequent | 3 | LOW, MOD, HIGH |
| Trauma Activations | 3 | ALPHA, BETA, GAMMA |
| Trauma Initial Low | 1 | LOW only |
| Trauma Subsequent | 3 | LOW, MOD, HIGH |
| Critical Care | 2 | TIME, SPLIT/SHARE |
| SIMU | 2 | SIMU, SIMUSYSTEMS |
| Discharge | 1 | DC |

---

## VERSION

v3.1 - February 2026
- Added structured MDM section to EDATTCCSPLITSHARE (audit compliance)
- Added compliance language ("DID perform substantive portion") to split/share
- Added "I contributed to patient care" field to split/share
- Added time disclaimer to split/share
- Fixed EDATTTRAUMAMDMINITLOW signature to @EDSIG@
- Removed undefined @EDATTFLOW@ from Alpha and Beta templates
- Added EDATTDC discharge template (99239, >30 min)
- Added Hard Rules 8 (conditional data bullets) and 9 (CC time buckets)
- Template count: 17 → 18

v2.0 - December 2025
- All EGS/Trauma converted to MDM-based billing
- Critical Care remains time-based
- Added EDATTCCSIMUSYSTEMS custom template
