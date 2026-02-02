# UVA GROUP ATTESTATION SYSTEM - TAS v1.0

## OVERVIEW

Minimal shareable SmartPhrase set for Trauma Acute Surgery (TAS) partner deployment. Uses SmartLists for variable content (MDM level, service type) to minimize total phrases.

**Total items to share: 12** (8 SmartPhrases + 4 SmartLists)

Partners create their own `@SIG@` with personal credentials. Type `.TAS` in any note to begin.

---

## MENU TREE

```
TAS [root menu]
├── TASEGS_INIT    → EGS initial (99221/99222/99223 via {TASMDMINIT})
├── TASEGS_SUB     → EGS subsequent (99231/99232/99233 via {TASMDMSUB})
├── TASTRAUMA_ACT  → Trauma activation (Alpha/Beta/Gamma via {TASTIER})
├── TASTRAUMA_SUB  → Trauma subsequent (99231/99232/99233 via {TASMDMSUB})
├── TASCC          → Critical care solo (99291/99292)
├── TASSPLIT       → Critical care split/share (99291/99292)
├── TASSIMU        → SIMU step-down (99232 fixed)
└── TASDC          → Discharge (99239)
```

---

## SHARED EXISTING SMARTLISTS (no creation needed)

These already exist at department level - verify partner has access:

| SmartList | ID | Purpose |
|-----------|-----|---------|
| {EDATTCCDX:54798} | 54798 | Critical care diagnoses |
| {EDATTCCSVCS:54356} | 54356 | Critical care services rendered |
| {EDBILLCCMENU:54470} | 54470 | Critical care time buckets (99291/99292) |
| {does or does not:50840} | 50840 | Boolean for hospitalization/OR/admission |
| {MRN trauma diagnoses:50834} | 50834 | Trauma injury list |
| {mrn response time:50839} | 50839 | Trauma response time (Alpha/Beta only) |
| {N/APOSTOP:55824} | 55824 | POD/HOD selector |

---

## NEW SMARTLIST DEFINITIONS (4)

### {TASMDMINIT} - EGS Initial MDM Level

**Option 1: Low**
```
2. Data Reviewed and Analyzed:
I reviewed laboratory results and imaging studies obtained during this encounter. I reviewed the nursing assessment and vital sign trends.

3. Risk of Complications/Morbidity:
Low risk.

MDM Summary: Low complexity MDM based on acute uncomplicated illness or stable chronic condition with limited data review and low-risk management.

Hospitalization is medically necessary for monitoring, diagnostic workup, and treatment of the above condition(s).

From a surgical standpoint, the patient {does or does not 50840:"does"} require hospitalization, {does or does not 50840:"does not"} emergent operative intervention and {does or does not 50840:"does not"} require admission under the EGS service; admission location/discharge disposition per plan.

I discussed the diagnosis, treatment options, and expected clinical course with the patient and/or family.

E/M Billing: 99221 - Initial hospital care, low MDM
```

**Option 2: Moderate**
```
2. Data Reviewed and Analyzed:
I independently reviewed and interpreted laboratory results. I independently reviewed and interpreted imaging studies. I reviewed prior medical records and external documentation. I discussed findings and management plan with consulting services.

3. Risk of Complications/Morbidity:
Moderate risk.

MDM Summary: Moderate complexity MDM based on acute illness with systemic symptoms requiring moderate data analysis and moderate-risk management decisions.

Hospitalization is medically necessary for monitoring, diagnostic workup, and treatment of the above condition(s).

From a surgical standpoint, the patient {does or does not 50840:"does"} require hospitalization, {does or does not 50840:"does not"} emergent operative intervention and {does or does not 50840:"does not"} require admission under the EGS service; admission location/discharge disposition per plan.

I discussed the diagnosis, treatment options, risks and benefits of surgical vs non-operative management, and expected clinical course with the patient and/or family.

E/M Billing: 99222 - Initial hospital care, moderate MDM
```

**Option 3: High**
```
2. Data Reviewed and Analyzed:
I independently reviewed and interpreted laboratory results. I independently reviewed and interpreted imaging studies. I reviewed prior medical records, external documentation, and OSH records. I discussed findings, diagnosis, and management with anesthesiology, critical care, and relevant consulting services.

3. Risk of Complications/Morbidity:
High risk.

MDM Summary: High complexity MDM based on acute illness posing threat to life or bodily function requiring extensive data analysis and high-risk management.

Hospitalization is medically necessary for monitoring, diagnostic workup, and treatment of the above condition(s).

From a surgical standpoint, the patient {does or does not 50840:"does"} require hospitalization, {does or does not 50840:"does not"} emergent operative intervention and {does or does not 50840:"does not"} require admission under the EGS service; admission location/discharge disposition per plan.

I discussed the diagnosis, need for surgery, surgical risks including bleeding, infection, injury to adjacent structures, need for ostomy, and possibility of death, as well as alternative treatments with the patient and/or family. Informed consent obtained.

E/M Billing: 99223 - Initial hospital care, high MDM
```

---

### {TASMDMSUB} - Subsequent MDM Level

**Option 1: Low**
```
2. Data Reviewed and Analyzed:
I reviewed interval laboratory results and vital sign trends. I reviewed nursing documentation and patient-reported symptoms.

3. Risk of Complications/Morbidity:
Low risk.

MDM Summary: Low complexity MDM for stable or improving condition with limited data review and low-risk management.

Continued hospitalization {does or does not 50840:"does"} remain medically necessary for ongoing monitoring and treatment.

E/M Billing: 99231 - Subsequent hospital care, low MDM
```

**Option 2: Moderate**
```
2. Data Reviewed and Analyzed:
I independently reviewed and interpreted interval laboratory results. I independently reviewed and interpreted new or repeat imaging studies. I reviewed nursing documentation, I/Os, and vital sign trends. I discussed patient status and care coordination with consulting services and/or primary team.

3. Risk of Complications/Morbidity:
Moderate risk.

MDM Summary: Moderate complexity MDM for acute illness with systemic symptoms requiring moderate data analysis and ongoing moderate-risk management decisions.

Continued hospitalization {does or does not 50840:"does"} remain medically necessary for ongoing monitoring and treatment.

E/M Billing: 99232 - Subsequent hospital care, moderate MDM
```

**Option 3: High**
```
2. Data Reviewed and Analyzed:
I independently reviewed and interpreted interval laboratory results. I independently reviewed and interpreted new or repeat imaging studies. I reviewed nursing documentation, hemodynamic parameters, and resuscitation endpoints. I discussed patient status and management with critical care, anesthesiology, and relevant consulting services.

3. Risk of Complications/Morbidity:
High risk.

MDM Summary: High complexity MDM for acute illness posing threat to life or bodily function requiring extensive data analysis and high-risk management decisions.

Continued hospitalization {does or does not 50840:"does"} remain medically necessary for ongoing monitoring and treatment.

E/M Billing: 99233 - Subsequent hospital care, high MDM
```

---

### {TASTIER} - Trauma Activation Tier

**Option 1: Alpha**
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
```

**Option 2: Beta**
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
```

**Option 3: Gamma**
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
```

---

### {TASCCTIME} - Critical Care Time Buckets

Same options as {EDBILLCCMENU:54470}. If partner has access to {EDBILLCCMENU:54470}, use that instead. Otherwise create with these options:

**Option 1:** 99291 x1 (30-74 min critical care)
**Option 2:** 99291 x1, 99292 x1 (75-104 min critical care)
**Option 3:** 99291 x1, 99292 x2 (105-134 min critical care)
**Option 4:** 99291 x1, 99292 x3 (135-164 min critical care)
**Option 5:** 99291 x1, 99292 x4 (165-194 min critical care)

---

## SMARTPHRASE TEMPLATES (8)

---

### 1. TAS - Root Menu

```
Select encounter type:

{TAS MENU:
TASEGS_INIT - EGS Initial (consult/H&P)
TASEGS_SUB - EGS Subsequent (floor daily)
TASTRAUMA_ACT - Trauma Activation
TASTRAUMA_SUB - Trauma Subsequent (floor daily)
TASCC - Critical Care (solo)
TASSPLIT - Critical Care Split/Share
TASSIMU - SIMU Step-Down
TASDC - Discharge}
```

---

### 2. TASEGS_INIT - EGS Initial

```
ATTENDING ATTESTATION

I independently evaluated the patient today and reviewed the resident/APP documentation. I agree with the documented history, physical examination, assessment, and plan with the following additions/clarifications:

MEDICAL DECISION MAKING

1. Problem(s) Addressed:
See above for problems and plan

{TASMDMINIT}

@SIG@
```

---

### 3. TASEGS_SUB - EGS Subsequent

```
ATTENDING ATTESTATION

I examined the patient today and reviewed the resident/APP note, interval labs, imaging, and overnight events. I agree with the documented assessment and plan with the following additions/clarifications:

MEDICAL DECISION MAKING

1. Problem(s) Addressed:
See above for problems and plan

{TASMDMSUB}

@SIG@
```

---

### 4. TASTRAUMA_ACT - Trauma Activation

```
{TASTIER}

@SIG@
```

Note: The {TASTIER} SmartList contains the COMPLETE template text for each activation tier (Alpha/Beta/Gamma), including the attestation header, injury list, MDM section, and billing line.

---

### 5. TASTRAUMA_SUB - Trauma Subsequent

```
ATTENDING ATTESTATION

I examined the patient today and reviewed the resident/APP note, interval labs, imaging, and overnight events. I agree with the documented assessment and plan with the following additions/clarifications:

MEDICAL DECISION MAKING

1. Problem(s) Addressed:
See above for problems and plan

{TASMDMSUB}

Tertiary survey: ***
VTE prophylaxis: Per protocol.
PT/OT: ***

@SIG@
```

---

### 6. TASCC - Critical Care (Solo)

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
***

@SIG@
```

---

### 7. TASSPLIT - Critical Care Split/Share

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

@SIG@
```

---

### 8. TASSIMU - SIMU Step-Down

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

@SIG@
```

---

### 9. TASDC - Discharge

```
ATTENDING ATTESTATION - DISCHARGE

I independently evaluated the patient today, reviewed the hospital course, and performed the discharge assessment. I reviewed and agree with the discharge summary, medication reconciliation, and follow-up plan with the following additions/clarifications:

Hospital Course Summary: ***

Discharge condition: ***

Time spent on discharge day activities: *** min
Activities included: final examination, review of pending results, medication reconciliation, discharge instructions and counseling, coordination of follow-up care, and communication with patient/family.

Total physician time on discharge: >30 minutes

E/M Billing: 99239 - Hospital discharge day management, >30 minutes

@SIG@
```

---

## PARTNER ONBOARDING INSTRUCTIONS

### Step 1: Create Your Signature

Create a personal SmartPhrase called `@SIG@` containing:
```
[Your Name] MD
[Your Title]: University of Virginia School of Medicine
[Your Division/Specialties]
```

### Step 2: Receive Shared Items

You will receive 12 shared items from the system owner:
- 8 SmartPhrases: TAS, TASEGS_INIT, TASEGS_SUB, TASTRAUMA_ACT, TASTRAUMA_SUB, TASCC, TASSPLIT, TASSIMU, TASDC
- 4 SmartLists: {TASMDMINIT}, {TASMDMSUB}, {TASTIER}, {TASCCTIME}

Accept all shared items in Epic SmartPhrase Manager.

### Step 3: Verify Department SmartLists

Confirm you have access to these existing department-level SmartLists:
- [ ] {EDATTCCDX:54798} - Critical care diagnoses
- [ ] {EDATTCCSVCS:54356} - Critical care services
- [ ] {EDBILLCCMENU:54470} - CC time buckets
- [ ] {does or does not:50840} - Boolean
- [ ] {MRN trauma diagnoses:50834} - Trauma injuries
- [ ] {mrn response time:50839} - Response time
- [ ] {N/APOSTOP:55824} - POD/HOD selector

If any are missing, contact Epic support to request access.

### Step 4: Test

1. Open a test note in Epic
2. Type `.TAS` - root menu should appear
3. Select any encounter type
4. Verify SmartLists populate correctly
5. Verify `@SIG@` resolves to your signature

---

## QUICK REFERENCE CARD

| Encounter | Type `.TAS` then select | Code(s) | Billing |
|-----------|------------------------|---------|---------|
| EGS consult/H&P | TASEGS_INIT → pick MDM | 99221/222/223 | MDM |
| EGS floor daily | TASEGS_SUB → pick MDM | 99231/232/233 | MDM |
| Trauma activation | TASTRAUMA_ACT → pick tier | 99222/223 | MDM |
| Trauma floor daily | TASTRAUMA_SUB → pick MDM | 99231/232/233 | MDM |
| ICU critical care | TASCC | 99291/292 | TIME |
| ICU split/share | TASSPLIT | 99291/292 | TIME |
| SIMU step-down | TASSIMU | 99232 | MDM |
| Discharge >30 min | TASDC | 99239 | TIME |

### MDM Quick Guide

| Element | Low | Moderate | High |
|---------|-----|----------|------|
| Problem | Minor/self-limited | Acute + systemic | Threat to life |
| Data | Labs OR imaging | Labs AND imaging + consults | Extensive multi-source |
| Risk | OTC management | Rx drugs, minor surgery | Emergent major surgery |

**MDM Level = highest 2 of 3 elements**

---

## DESIGN NOTES

- **Why 8+4 instead of 17**: MDM-level variants collapsed into SmartLists. One phrase handles all levels.
- **@SIG@ vs @EDSIG@**: TAS uses generic @SIG@ so each partner creates their own. EDATT uses @EDSIG@ (personal to system owner).
- **{TASTIER} contains full template**: Unlike other SmartLists that insert partial sections, {TASTIER} outputs the complete activation attestation because Alpha/Beta/Gamma differ in structure, not just MDM level.
- **Reuse existing SmartLists**: Department-level lists (diagnoses, services, time buckets, booleans) are shared infrastructure - no duplication needed.

---

## VERSION

v1.0 - February 2026
- Initial release: 8 SmartPhrases + 4 SmartLists
- Template text matches EDATT v3.1 exactly
- Designed for partner deployment via Epic SmartPhrase sharing
