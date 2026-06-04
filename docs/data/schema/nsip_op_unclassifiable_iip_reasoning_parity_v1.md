# ILD Reasoning Platform — NSIP / OP / Unclassifiable IIP Reasoning Parity v1

Version: v0.7.6  
Status: nsip_op_unclassifiable_iip_reasoning_parity  
Scope: NSIP-like, OP-like, and unclassifiable IIP reasoning within non-UIP fibrotic ILD differential expansion  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This document defines NSIP / OP / Unclassifiable IIP reasoning parity for the ILD Reasoning Platform.

It follows:

- `docs/navigation/non_uip_fibrotic_ild_differential_reasoning_entry_gate_v1.md`
- `docs/navigation/non_uip_fibrotic_ild_source_anchor_map_v1.md`
- `docs/navigation/non_uip_differential_claim_to_source_mapping_table_v1.md`
- `docs/data/schema/non_uip_differential_reasoning_family_matrix_v1.md`
- `docs/data/schema/fibrotic_hp_reasoning_parity_v1.md`
- `docs/data/schema/ctd_ild_sard_ild_context_prompt_parity_v1.md`

This document does not diagnose NSIP.  
This document does not diagnose idiopathic NSIP.  
This document does not diagnose organizing pneumonia.  
This document does not diagnose cryptogenic organizing pneumonia.  
This document does not diagnose unclassifiable IIP.  
This document does not diagnose IPF.  
This document does not diagnose CTD-ILD.  
This document does not diagnose hypersensitivity pneumonitis.  
This document does not diagnose drug toxicity.  
This document does not diagnose infection or aspiration.  
This document does not recommend treatment.  
This document does not decide biopsy.  
This document does not create public readiness.  
This document does not make v0.7 clinically reviewed.  
This document does not replace radiologist interpretation, pathology review, clinical correlation, pulmonology, rheumatology, MDD, microbiology, exposure review, or urgent clinical assessment.

Its purpose is to ensure that NSIP-like, OP-like, mixed-pattern, and unclassifiable reasoning states remain visible without becoming automatic diagnoses.

The v0.7 principle remains:

> “Differential reasoning is not differential diagnosis authority.”

For NSIP / OP / unclassifiable IIP, this becomes:

> “Read pattern, secondary causes, mixed injury, missing evidence, discordance, and MDD need before naming NSIP, OP, or unclassifiable IIP.”

---

## 2. Source Anchors Used

| Source ID | Source | Role |
|---|---|---|
| V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION | Travis et al. 2013 ATS/ERS Update of the International Multidisciplinary Classification of the Idiopathic Interstitial Pneumonias | Primary IIP / NSIP / OP / unclassifiable IIP source |
| V07_SRC_2020_ATS_JRS_ALAT_HP_GUIDELINE | Raghu et al. 2020 ATS/JRS/ALAT Diagnosis of Hypersensitivity Pneumonitis in Adults | HP overlap and mimic source |
| V07_SRC_2023_ACR_CHEST_SARD_ILD_SCREEN_MONITOR | 2023 ACR/CHEST SARD-ILD Screening and Monitoring Guideline | CTD/SARD overlap source |
| UIP_SRC_2018_ATS_ERS_JRS_ALAT_DX | Raghu et al. 2018 ATS/ERS/JRS/ALAT IPF Diagnosis Guideline | UIP/IPF boundary inheritance |
| UIP_SRC_2022_ATS_ERS_JRS_ALAT_IPF_PPF | Raghu et al. 2022 ATS/ERS/JRS/ALAT IPF Update and PPF Guideline | PPF / progression context inheritance |
| V07_INTERNAL_V073_FAMILY_MATRIX | Non-UIP Differential Reasoning Family Matrix | Family-state dependency |
| V07_INTERNAL_V074_FIBROTIC_HP_PARITY | Fibrotic HP Reasoning Parity | HP overlap dependency |
| V07_INTERNAL_V075_CTD_ILD_PARITY | CTD-ILD / SARD-ILD Context Prompt Parity | CTD overlap dependency |
| V07_SRC_INTERNAL_V06_R1_R2_R3_BACKFILL | Internal v0.6 source debt/backfill chain | Source-governance inheritance |

Source status:

- IIP source review: targeted_partial
- IIP / NSIP / OP / unclassifiable claim mapping: initial_partial_complete
- clinically_reviewed: false
- public_ready: false

---

## 3. Authority Constraints

The following constraints are mandatory.

| Constraint | Required State |
|---|---|
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| clinically_reviewed | false |
| automated_NSIP_diagnosis | not_allowed |
| automated_idiopathic_NSIP_diagnosis | not_allowed |
| automated_OP_diagnosis | not_allowed |
| automated_COP_diagnosis | not_allowed |
| automated_unclassifiable_IIP_diagnosis | not_allowed |
| automated_IPF_diagnosis | not_allowed |
| automated_CTD_ILD_diagnosis | not_allowed |
| automated_HP_diagnosis | not_allowed |
| automated_drug_toxicity_diagnosis | not_allowed |
| automated_infection_diagnosis | not_allowed |
| automated_aspiration_diagnosis | not_allowed |
| automated_biopsy_decision | not_allowed |
| automated_treatment_selection | not_allowed |
| patient_facing_use | not_allowed |
| replacement_of_MDD | not_allowed |
| replacement_of_clinician | not_allowed |
| replacement_of_radiologist | not_allowed |
| replacement_of_pathologist | not_allowed |
| replacement_of_pulmonologist | not_allowed |
| replacement_of_rheumatologist | not_allowed |
| replacement_of_microbiology | not_allowed |
| replacement_of_exposure_review | not_allowed |
| replacement_of_urgent_review | not_allowed |

No NSIP / OP / unclassifiable IIP reasoning state may override these constraints.

---

## 4. Core NSIP / OP / Unclassifiable IIP Parity Principle

NSIP-like and OP-like patterns must remain visible when relevant, but the platform must not diagnose them.

Central rule:

> A morphologic or imaging pattern is not automatically an idiopathic disease.

The platform must preserve:

- NSIP-like pattern visibility,
- OP-like pattern visibility,
- secondary-cause prompts,
- CTD-ILD context,
- HP context,
- drug toxicity context,
- infection context,
- aspiration context,
- UIP/IPF overlap,
- mixed HRCT/pathology patterns,
- inadequate data,
- clinical-radiologic-pathologic discordance,
- MDD need,
- uncertainty.

The platform must block:

- idiopathic NSIP diagnosis,
- COP diagnosis,
- forced unclassifiable IIP diagnosis,
- treatment recommendations,
- biopsy decisions,
- public-ready interpretation.

---

## 5. State Model

| State | Meaning | Required Behavior |
|---|---|---|
| NSIP_LIKE_PATTERN_VISIBLE | NSIP-like imaging or pathology pattern is present or suspected | Show NSIP-like prompt without diagnosis |
| NSIP_SECONDARY_CAUSE_VISIBLE | CTD, HP, drug toxicity, familial fibrosis, or exposure-related cause may explain NSIP-like pattern | Preserve secondary-cause visibility |
| NSIP_IDIOPATHIC_CLOSURE_BLOCKED | Idiopathic NSIP cannot be named because secondary-cause review is incomplete | Block idiopathic NSIP closure |
| OP_LIKE_PATTERN_VISIBLE | OP-like imaging or pathology pattern is present or suspected | Show OP-like prompt without diagnosis |
| OP_SECONDARY_CAUSE_VISIBLE | Infection, aspiration, CTD, drug toxicity, therapy-related injury, or HP may explain OP-like pattern | Preserve secondary-cause visibility |
| COP_CLOSURE_BLOCKED | Cryptogenic OP cannot be named because secondary causes are not reviewed | Block COP closure |
| FIBROTIC_OP_OVERLAP_VISIBLE | OP-like process coexists with fibrotic abnormality | Preserve fibrotic OP overlap prompt |
| UIP_NSIP_BOUNDARY_VISIBLE | UIP-like and NSIP-like features overlap or conflict | Preserve boundary uncertainty |
| NSIP_OP_OVERLAP_VISIBLE | NSIP-like and OP-like patterns coexist | Keep both visible |
| MIXED_PATTERN_VISIBLE | Multiple HRCT or pathologic patterns coexist | Preserve mixed-pattern reasoning |
| UNCLASSIFIABLE_INADEQUATE_DATA | Clinical, radiologic, or pathologic data are insufficient | Preserve uncertainty; do not force label |
| UNCLASSIFIABLE_DISCORDANCE | Clinical, radiologic, and pathologic domains are discordant | Trigger MDD / re-review prompt |
| DISEASE_BEHAVIOR_VISIBLE | Disease behavior pattern may help review | Do not convert behavior into treatment plan |
| MDD_PROMPT_VISIBLE | Integrated review is needed | Preserve review prompt |
| SOURCE_LIMITED | Source mapping partial or claim scope limited | Show source limitation |

States may coexist.

Example:

- `NSIP_LIKE_PATTERN_VISIBLE`
- plus `NSIP_SECONDARY_CAUSE_VISIBLE`
- plus `CTD_CONTEXT_MISSING`
- plus `UNCLASSIFIABLE_DISCORDANCE`
- plus `MDD_PROMPT_VISIBLE`

is valid.

The platform must not collapse this into idiopathic NSIP diagnosis.

---

## 6. NSIP Reasoning Matrix

| Evidence / Pattern Domain | Possible Supporting Features | Required Platform Response | Blocked Closure |
|---|---|---|---|
| HRCT NSIP-like pattern | bilateral GGO, reticulation, traction bronchiectasis, lower-lobe predominance, possible subpleural sparing | Show NSIP-like prompt | idiopathic NSIP diagnosis |
| Pathology NSIP-like pattern | temporally uniform fibrosis/inflammation, preserved architecture, limited honeycombing/fibroblastic foci | Show pathology prompt | NSIP diagnosis from pathology alone |
| CTD context | autoimmune symptoms, known SARD, serology, rheumatologic features | Keep CTD-ILD visible | idiopathic NSIP closure |
| HP context | exposure history, small-airway features, mosaic attenuation, air trapping, BAL/pathology support | Keep HP visible | HP exclusion |
| Drug toxicity context | medication or therapy history missing or suggestive | Keep drug toxicity visible | drug toxicity exclusion |
| Familial fibrosis context | family history or genetic context relevant | Keep familial ILD prompt visible | idiopathic closure |
| UIP overlap | honeycombing, subpleural/basal fibrosis, UIP/probable UIP features | Preserve UIP/NSIP boundary | UIP or NSIP forced label |
| Temporal behavior | stable, progressive, improving, acute overlay | Show temporal uncertainty | treatment inference |
| Missing evidence | clinical, serologic, exposure, medication, pathology, prior imaging, MDD gaps | List missing evidence | exclusion from absence |

---

## 7. NSIP Rules

| Rule ID | Rule | Required Behavior |
|---|---|---|
| NSIP_001 | NSIP-like pattern is not idiopathic NSIP diagnosis | Show pattern prompt only |
| NSIP_002 | Secondary causes must remain visible | Keep CTD, HP, drug toxicity, familial, and exposure prompts visible |
| NSIP_003 | CTD context is especially important in NSIP-like patterns | Preserve CTD/SARD prompt where relevant |
| NSIP_004 | HP can mimic or overlap NSIP-like reasoning | Preserve HP prompt where relevant |
| NSIP_005 | Drug toxicity can contribute to NSIP-like pattern | Preserve medication history prompt |
| NSIP_006 | UIP-like features can coexist or conflict with NSIP-like features | Preserve boundary uncertainty |
| NSIP_007 | Histologic NSIP pattern requires clinical-radiologic integration | Preserve MDD prompt |
| NSIP_008 | Missing evidence must not become secondary-cause exclusion | List evidence gaps |
| NSIP_009 | Disease behavior does not create treatment authority | Block treatment recommendation |
| NSIP_010 | Final diagnosis remains outside platform authority | diagnostic_authority: none |

Blocked output:

- “Idiopathic NSIP diagnosed.”
- “CTD-ILD excluded.”
- “HP excluded.”
- “Drug toxicity excluded.”
- “UIP excluded.”
- “Treatment should be started.”
- “No MDD needed.”

---

## 8. OP / COP Reasoning Matrix

| Evidence / Pattern Domain | Possible Supporting Features | Required Platform Response | Blocked Closure |
|---|---|---|---|
| OP-like HRCT pattern | patchy or migratory consolidation, subpleural, peribronchial, bandlike, perilobular, reverse halo where relevant | Show OP-like prompt | COP diagnosis |
| OP-like pathology | organizing pneumonia pattern | Show pathology prompt | OP/COP diagnosis from pathology alone |
| Infection context | fever, microbiology missing, inflammatory markers, acute symptoms | Keep infection visible | infection exclusion |
| Aspiration context | aspiration risk, dependent consolidation, swallowing/reflux context missing | Keep aspiration visible | aspiration exclusion |
| CTD context | RA, myositis, antisynthetase, SARD features | Keep CTD-ILD / secondary OP visible | COP closure |
| Drug / therapy context | medication, chemotherapy, radiation, immunotherapy context | Keep drug/therapy-related OP visible | drug toxicity exclusion |
| HP context | exposure, bronchiolar features, granulomatous clues | Keep HP visible | HP exclusion |
| Fibrotic overlap | consolidation plus reticulation/fibrosis | Show fibrotic OP overlap | pure OP/COP closure |
| Acute overlay | new consolidation/GGO with symptoms | Show urgent review where relevant | chronic label only |
| Missing evidence | infection, aspiration, medication, autoimmune, exposure, pathology, MDD gaps | List missing evidence | secondary cause exclusion |

---

## 9. OP / COP Rules

| Rule ID | Rule | Required Behavior |
|---|---|---|
| OP_001 | OP-like pattern is not COP diagnosis | Show OP-like prompt only |
| OP_002 | Secondary causes must remain visible | Preserve infection, aspiration, CTD, drug, therapy, HP prompts |
| OP_003 | Cryptogenic OP closure requires secondary-cause review outside platform authority | Block COP diagnosis |
| OP_004 | OP-like consolidation may represent acute overlay | Preserve urgent/mimic review where relevant |
| OP_005 | Fibrotic OP overlap must remain visible | Do not force simple OP label |
| OP_006 | OP-like pattern may overlap NSIP | Keep NSIP/OP coexistence visible |
| OP_007 | OP-like pattern may overlap CTD-ILD | Keep autoimmune context visible |
| OP_008 | OP-like pattern may overlap HP | Keep exposure and HP prompts visible |
| OP_009 | Infection and aspiration must not be hidden | Preserve missing evidence prompts |
| OP_010 | Treatment logic is blocked | No steroid or therapy recommendation |

Blocked output:

- “COP diagnosed.”
- “OP confirmed.”
- “Infection excluded.”
- “Aspiration excluded.”
- “Drug toxicity excluded.”
- “CTD-ILD excluded.”
- “Treatment should be started.”
- “No urgent review needed” when acute danger exists.

---

## 10. Unclassifiable / Mixed Pattern Reasoning Matrix

| Reasoning Domain | Trigger | Required Platform Response | Blocked Closure |
|---|---|---|---|
| Inadequate clinical data | clinical context missing | Show insufficient data prompt | forced diagnosis |
| Inadequate radiologic data | HRCT unavailable, incomplete, limited quality, incomplete technique | Show imaging gap | confident family label |
| Inadequate pathology data | biopsy unavailable, inadequate, not integrated | Show pathology gap | pathology-based closure |
| Clinical-radiologic discordance | clinical and imaging domains conflict | Trigger MDD/re-review | single-label closure |
| Radiologic-pathologic discordance | HRCT and pathology conflict | Trigger MDD/re-review | forced label |
| Multiple HRCT patterns | UIP, NSIP, OP, HP, sarcoid, emphysema, acute overlay patterns coexist | Keep all visible | dominant label hides others |
| Multiple pathology patterns | UIP plus NSIP, OP, DAD, granulomas, bronchiolocentric injury, etc. | Keep mixed pattern prompt | single pathology label |
| Prior therapy alters pattern | treatment may modify imaging/pathology | Show limitation | overconfident classification |
| New or unusual variant | pattern not well characterized | Show unclassifiable / source-limited prompt | invented diagnosis |
| Disease behavior context | progression/stability/reversibility may guide review | Show behavior prompt only | treatment plan |

---

## 11. Unclassifiable IIP Rules

| Rule ID | Rule | Required Behavior |
|---|---|---|
| UNC_001 | Unclassifiable means classification is not safely resolved | Preserve uncertainty |
| UNC_002 | Inadequate data must remain visible | List missing clinical/radiologic/pathologic data |
| UNC_003 | Discordance must trigger MDD/re-review prompt | Do not force label |
| UNC_004 | Mixed HRCT/pathology patterns may coexist | Preserve all relevant families |
| UNC_005 | Prior therapy can alter patterns | Preserve interpretation limitation |
| UNC_006 | Disease behavior may inform review | Do not create treatment plan |
| UNC_007 | Working diagnosis remains provisional | Keep confidence and re-review visible |
| UNC_008 | Source-limited or unusual variants require caution | Do not invent new diagnosis |
| UNC_009 | Unclassifiable label must not become a final diagnostic shortcut | Preserve reviewability |
| UNC_010 | Public readiness remains false | No patient-facing output |

Blocked output:

- “Unclassifiable IIP diagnosed definitively.”
- “Mixed pattern resolved automatically.”
- “MDD unnecessary.”
- “Disease behavior determines treatment.”
- “No further review needed.”
- “Public-ready.”

---

## 12. Coexisting Pattern Rules

| Coexisting Pattern | Required Behavior |
|---|---|
| UIP plus NSIP | Preserve UIP/NSIP boundary; MDD visible |
| NSIP plus OP | Preserve both NSIP-like and OP-like prompts |
| OP plus fibrosis | Preserve fibrotic OP overlap |
| UIP plus OP | Preserve UIP and OP prompts; secondary causes visible |
| NSIP plus CTD | Preserve autoimmune context |
| OP plus CTD | Preserve autoimmune context |
| NSIP plus HP | Preserve exposure/small-airway context |
| OP plus HP | Preserve exposure/OP/infection/aspiration overlap |
| Fibrosis plus emphysema | Preserve smoking/CPFE context |
| Fibrosis plus acute GGO/consolidation | Preserve acute overlay and urgent review prompts |
| Granulomatous features plus NSIP/OP | Preserve sarcoid/HP/infection/drug mimics |

Rule:

> Coexisting patterns must be represented as coexistence, not silently ranked into one winner.

---

## 13. Missing Evidence Matrix

| Missing Evidence | Families Protected |
|---|---|
| Autoimmune history/serology missing | CTD-ILD; secondary NSIP; secondary OP |
| Exposure history missing | HP; occupational ILD; secondary NSIP/OP |
| Medication/therapy history missing | drug toxicity; therapy-related OP/NSIP |
| Infection data missing | infection mimic; OP-like consolidation; acute overlay |
| Aspiration risk missing | aspiration-related OP/ILD |
| Smoking history missing | RB-ILD/DIP; smoking-related fibrosis; CPFE |
| HRCT technique incomplete | NSIP/UIP boundary; OP consolidation; dependent opacity; air trapping |
| Prior imaging missing | progression/stability; acute vs chronic change |
| Pathology unavailable | NSIP/OP/UIP/unclassifiable boundary |
| Pathology not integrated | MDD/pathology uncertainty |
| Clinical timeline missing | acute/subacute/chronic separation |
| Prior therapy history missing | pattern alteration / unclassifiable risk |
| MDD unavailable | integrated diagnosis not established |
| Urgent clinical status missing | acute overlay danger incompletely assessed |

Required rule:

> Missing evidence must remain visible and must not be converted into exclusion.

---

## 14. MDD and Review Rules

| Rule ID | Rule | Required Behavior |
|---|---|---|
| IIP_MDD_001 | IIP classification requires dynamic multidisciplinary integration | Preserve MDD prompt |
| IIP_MDD_002 | NSIP-like pattern requires clinical and secondary-cause review | Preserve CTD/HP/drug/familial prompts |
| IIP_MDD_003 | OP-like pattern requires secondary-cause review | Preserve infection/aspiration/CTD/drug/HP prompts |
| IIP_MDD_004 | Mixed or coexisting patterns require MDD | Preserve all visible patterns |
| IIP_MDD_005 | Discordance requires re-review | Do not force classification |
| IIP_MDD_006 | Working diagnosis remains provisional | Preserve confidence and re-review |
| IIP_MDD_007 | Acute danger must not wait for IIP classification | Preserve urgent review prompt |

Blocked output:

- “MDD unnecessary.”
- “Pathology settles diagnosis alone.”
- “Imaging settles diagnosis alone.”
- “Working diagnosis final.”
- “No further review needed.”

---

## 15. Acute Overlay Rules

NSIP-like, OP-like, and unclassifiable cases may coexist with acute processes.

| Acute / Overlay Concern | Required Prompt |
|---|---|
| New GGO | infection, edema, hemorrhage, drug toxicity, acute exacerbation-like overlay |
| New consolidation | infection, aspiration, OP-like process, urgent review |
| Rapid oxygen worsening | urgent clinical review |
| Fever / inflammatory marker context | infection or inflammatory overlay |
| Hemoptysis / anemia | hemorrhage |
| Acute dyspnea / hypoxemia | vascular concern |
| New medication or therapy | drug toxicity / therapy-related injury |
| Immunosuppressed context | infection risk visibility |
| Prior fibrotic baseline plus new opacity | mixed chronic-acute prompt |

Rule:

> Acute overlay must not be collapsed into NSIP progression, OP diagnosis, or unclassifiable label.

---

## 16. Priority Order

When NSIP / OP / unclassifiable reasoning is active, visibility priority is:

1. urgent clinical danger,
2. acute overlay or unstable clinical context,
3. infection / aspiration / hemorrhage / vascular / edema prompts,
4. secondary-cause prompts,
5. CTD-ILD / HP / drug / exposure / smoking prompts,
6. mixed or coexisting pattern prompt,
7. missing evidence,
8. source / mapping limitation,
9. MDD / re-review prompt,
10. temporal comparison prompt,
11. NSIP-like or OP-like pattern-family description,
12. working diagnosis caveat.

Pattern-family naming must not outrank safety, secondary causes, missing evidence, source status, or MDD need.

---

## 17. Allowed Language

Allowed output posture:

- “NSIP-like pattern prompt is visible.”
- “Idiopathic NSIP should not be named before secondary causes are reviewed.”
- “OP-like pattern prompt is visible.”
- “Cryptogenic OP should not be named before secondary causes are reviewed.”
- “Mixed-pattern / unclassifiable reasoning remains visible.”
- “Clinical-radiologic-pathologic discordance triggers MDD prompt.”
- “CTD-ILD, HP, drug toxicity, infection, and aspiration contexts remain visible where relevant.”
- “Missing evidence limits confidence.”
- “Final diagnosis is not established by this platform.”
- “diagnostic_authority: none”
- “treatment_authority: none”
- “public_ready: false”
- “clinically_reviewed: false”

---

## 18. Blocked Language

Blocked output posture:

- “NSIP diagnosed.”
- “Idiopathic NSIP confirmed.”
- “OP diagnosed.”
- “COP confirmed.”
- “Unclassifiable IIP definitively diagnosed.”
- “CTD-ILD excluded.”
- “HP excluded.”
- “Drug toxicity excluded.”
- “Infection excluded.”
- “Aspiration excluded.”
- “UIP/IPF excluded.”
- “MDD unnecessary.”
- “Biopsy should be performed.”
- “Treatment should be started.”
- “Public-ready.”
- “Clinically reviewed.”

---

## 19. Testable NSIP / OP / Unclassifiable IIP Expectations

Future test cases should evaluate:

| Expectation ID | Expectation |
|---|---|
| NOP_001 | NSIP-like prompt is visible without NSIP diagnosis |
| NOP_002 | Idiopathic NSIP closure is blocked when secondary causes are incomplete |
| NOP_003 | CTD-ILD context remains visible in NSIP-like pattern |
| NOP_004 | HP context remains visible in NSIP-like pattern |
| NOP_005 | Drug toxicity context remains visible in NSIP-like pattern |
| NOP_006 | OP-like prompt is visible without OP/COP diagnosis |
| NOP_007 | Infection remains visible in OP-like consolidation |
| NOP_008 | Aspiration remains visible in OP-like consolidation |
| NOP_009 | CTD-ILD remains visible in OP-like pattern |
| NOP_010 | Drug toxicity remains visible in OP-like pattern |
| NOP_011 | Fibrotic OP overlap remains visible |
| NOP_012 | Mixed HRCT/pathology patterns remain visible |
| NOP_013 | Unclassifiable state preserves uncertainty |
| NOP_014 | Inadequate data are listed |
| NOP_015 | Discordance triggers MDD/re-review prompt |
| NOP_016 | Disease behavior does not become treatment plan |
| NOP_017 | Urgent review prompt remains visible where relevant |
| NOP_018 | Diagnostic authority remains none |
| NOP_019 | Treatment authority remains none |
| NOP_020 | Public readiness remains false |
| NOP_021 | Clinically reviewed remains false |

---

## 20. Example Reasoning Scenarios

### 20.1 NSIP-Like Pattern With Missing Autoimmune and Exposure Context

Input reasoning context:

- bilateral GGO and reticulation,
- traction bronchiectasis,
- possible subpleural sparing,
- autoimmune history missing,
- exposure history missing,
- medication history missing,
- MDD not documented.

Allowed platform output:

- “NSIP-like pattern prompt is visible.”
- “Idiopathic NSIP should not be named prematurely.”
- “Autoimmune, exposure, and medication contexts are incomplete.”
- “CTD-ILD, HP, and drug toxicity prompts remain visible.”
- “MDD prompt remains visible.”

Blocked output:

- “Idiopathic NSIP confirmed.”
- “CTD-ILD excluded.”
- “HP excluded.”
- “Drug toxicity excluded.”
- “No MDD needed.”

---

### 20.2 OP-Like Consolidation With Infection and Aspiration Gaps

Input reasoning context:

- patchy consolidation,
- possible subpleural or peribronchial distribution,
- infection data missing,
- aspiration risk unknown,
- medication history missing.

Allowed platform output:

- “OP-like pattern prompt is visible.”
- “Cryptogenic OP should not be named before secondary causes are reviewed.”
- “Infection, aspiration, and drug toxicity contexts are incomplete.”
- “Urgent review prompt remains visible where clinically relevant.”
- “Final diagnosis is not established by this platform.”

Blocked output:

- “COP confirmed.”
- “Infection excluded.”
- “Aspiration excluded.”
- “Treatment should be started.”

---

### 20.3 Fibrotic OP Overlap With CTD Context

Input reasoning context:

- consolidation plus reticulation/fibrosis,
- known or suspected autoimmune disease,
- infection data incomplete,
- prior imaging unavailable.

Allowed platform output:

- “Fibrotic OP overlap prompt is visible.”
- “CTD-ILD context remains visible.”
- “Infection context is incomplete.”
- “Prior imaging is unavailable, limiting temporal interpretation.”
- “MDD prompt remains visible.”

Blocked output:

- “COP diagnosed.”
- “CTD-ILD confirmed.”
- “Infection excluded.”
- “No further review needed.”

---

### 20.4 Mixed UIP and NSIP Patterns

Input reasoning context:

- UIP-like features in one domain,
- NSIP-like features in another,
- clinical context incomplete,
- pathology/imaging discordance.

Allowed platform output:

- “Mixed-pattern reasoning remains visible.”
- “UIP/NSIP boundary is unresolved.”
- “Clinical-radiologic-pathologic discordance triggers MDD prompt.”
- “Final diagnosis is not established by this platform.”

Blocked output:

- “UIP confirmed.”
- “NSIP confirmed.”
- “Discordance resolved automatically.”
- “MDD unnecessary.”

---

### 20.5 Unclassifiable IIP Due to Inadequate Data

Input reasoning context:

- fibrotic ILD present,
- HRCT incomplete,
- pathology unavailable,
- clinical data incomplete,
- multiple differentials possible.

Allowed platform output:

- “Unclassifiable / insufficient-data reasoning remains visible.”
- “Clinical, radiologic, and pathology evidence gaps are listed.”
- “Working diagnosis, if considered, remains provisional and reviewable.”
- “MDD prompt remains visible.”

Blocked output:

- “Unclassifiable IIP definitively diagnosed.”
- “No further data needed.”
- “Treatment should be started.”
- “Public-ready.”

---

## 21. Failure Modes

The following are explicit v0.7.6 failures:

| Failure Mode | Why It Fails |
|---|---|
| NSIP-like prompt becomes NSIP diagnosis | Violates diagnostic_authority none |
| Idiopathic NSIP named before secondary-cause review | Hides CTD/HP/drug/familial context |
| OP-like prompt becomes COP diagnosis | Hides infection/aspiration/CTD/drug/HP context |
| Mixed pattern forced into one label | Violates coexisting pattern logic |
| Unclassifiable state treated as final diagnosis | Converts uncertainty into label |
| Disease behavior becomes treatment plan | Violates treatment_authority none |
| Missing evidence hidden | Creates false confidence |
| Secondary causes excluded without evidence | Violates missing evidence principle |
| MDD omitted in discordance | Weakens review governance |
| Acute overlay hidden | Weakens urgent review visibility |
| Biopsy decision appears | Creates clinical authority |
| Treatment recommendation appears | Violates treatment_authority none |
| Public-ready claim appears | Violates public_ready false |
| Clinically reviewed claim appears | Violates clinically_reviewed false |

---

## 22. Acceptance Criteria

v0.7.6 is accepted only if:

- NSIP-like pattern remains a prompt, not diagnosis,
- idiopathic NSIP closure is blocked until secondary causes are reviewed,
- OP-like pattern remains a prompt, not OP/COP diagnosis,
- cryptogenic OP closure is blocked until secondary causes are reviewed,
- CTD-ILD, HP, drug toxicity, infection, aspiration, and exposure contexts remain visible where relevant,
- fibrotic OP overlap remains visible,
- mixed/coexisting patterns remain visible,
- unclassifiable reasoning preserves uncertainty,
- inadequate data and discordance remain visible,
- MDD prompt remains visible,
- urgent review prompt remains visible where relevant,
- diagnostic_authority remains none,
- treatment_authority remains none,
- public_ready remains false,
- clinically_reviewed remains false.

---

## 23. Next Step

The next recommended step is:

- v0.7.7 — Sarcoidosis / Granulomatous Differential Prompt Parity

v0.7.7 should cover:

- sarcoid-like differential prompt,
- compatible clinical/radiologic/extrapulmonary context,
- nonnecrotizing granulomatous inflammation as supportive but non-diagnostic alone,
- alternative granulomatous causes,
- infection, berylliosis, HP, malignancy, drug reaction, immune disorder mimics,
- lymphadenopathy / perilymphatic pattern prompts,
- tissue sampling uncertainty without biopsy decision authority,
- no sarcoidosis diagnosis,
- no treatment authority,
- public_ready remains false.

---

## 24. Governance Statement

NSIP / OP / Unclassifiable IIP Reasoning Parity protects the platform from pattern-to-diagnosis collapse.

It does not diagnose.  
It does not treat.  
It does not decide biopsy.  
It does not confirm NSIP.  
It does not confirm idiopathic NSIP.  
It does not confirm OP.  
It does not confirm COP.  
It does not confirm unclassifiable IIP.  
It does not exclude CTD-ILD.  
It does not exclude HP.  
It does not exclude infection.  
It does not exclude aspiration.  
It does not exclude drug toxicity.  
It does not replace MDD.  
It does not replace clinical, radiologic, pathologic, microbiologic, or exposure review.  
It does not claim public readiness.  
It does not claim clinical review.

The platform remains an evidence-governed clinical reasoning platform.

The v0.7 rule remains:

> “Differential reasoning is not differential diagnosis authority.”

For NSIP / OP / unclassifiable IIP:

> “Read pattern, secondary causes, mixed injury, missing evidence, discordance, and MDD need before naming NSIP, OP, or unclassifiable IIP.”