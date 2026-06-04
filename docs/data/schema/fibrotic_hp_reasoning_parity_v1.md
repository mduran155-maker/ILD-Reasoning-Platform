# ILD Reasoning Platform — Fibrotic HP Reasoning Parity v1

Version: v0.7.4  
Status: fibrotic_hp_reasoning_parity  
Scope: Fibrotic hypersensitivity pneumonitis reasoning parity within non-UIP fibrotic ILD differential expansion  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This document defines Fibrotic Hypersensitivity Pneumonitis reasoning parity for the ILD Reasoning Platform.

It follows:

- `docs/navigation/non_uip_fibrotic_ild_differential_reasoning_entry_gate_v1.md`
- `docs/navigation/non_uip_fibrotic_ild_source_anchor_map_v1.md`
- `docs/navigation/non_uip_differential_claim_to_source_mapping_table_v1.md`
- `docs/data/schema/non_uip_differential_reasoning_family_matrix_v1.md`

This document does not diagnose hypersensitivity pneumonitis.  
This document does not diagnose fibrotic hypersensitivity pneumonitis.  
This document does not diagnose nonfibrotic hypersensitivity pneumonitis.  
This document does not diagnose IPF.  
This document does not diagnose NSIP.  
This document does not diagnose CTD-ILD.  
This document does not recommend treatment.  
This document does not decide BAL, biopsy, serum IgG testing, antigen testing, or exposure remediation.  
This document does not create public readiness.  
This document does not make v0.7 clinically reviewed.  
This document does not replace radiologist interpretation, pathology review, clinical correlation, pulmonology, occupational/environmental exposure review, MDD, or urgent clinical assessment.

Its purpose is to ensure that fibrotic HP remains visible as a differential reasoning pathway when relevant, while preventing HP-like features from becoming automatic diagnosis.

The v0.7 principle remains:

> “Differential reasoning is not differential diagnosis authority.”

For fibrotic HP, this becomes:

> “Read exposure, small-airway features, fibrosis pattern, missing evidence, overlap, and MDD need before naming fibrotic HP.”

---

## 2. Source Anchors Used

| Source ID | Source | Role |
|---|---|---|
| V07_SRC_2020_ATS_JRS_ALAT_HP_GUIDELINE | Raghu et al. 2020 ATS/JRS/ALAT Diagnosis of Hypersensitivity Pneumonitis in Adults | Primary HP reasoning source |
| V07_SRC_2020_HP_CLINICIAN_SUMMARY | Koster et al. 2021 clinician summary of 2020 HP guideline | Auxiliary HP summary source |
| V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION | Travis et al. 2013 ATS/ERS IIP Classification Update | IIP / NSIP / OP / unclassifiable overlap source |
| UIP_SRC_2018_ATS_ERS_JRS_ALAT_DX | Raghu et al. 2018 ATS/ERS/JRS/ALAT IPF Diagnosis Guideline | UIP/IPF boundary inheritance |
| UIP_SRC_2022_ATS_ERS_JRS_ALAT_IPF_PPF | Raghu et al. 2022 ATS/ERS/JRS/ALAT IPF Update and PPF Guideline | PPF / progression context inheritance |
| V07_SRC_INTERNAL_V06_R1_R2_R3_BACKFILL | Internal v0.6 source debt/backfill chain | Source-governance inheritance |
| V07_INTERNAL_V073_FAMILY_MATRIX | Non-UIP Differential Reasoning Family Matrix | Family-state dependency |

Source status:

- HP source review: targeted_partial
- HP claim mapping: initial_partial_complete
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
| automated_HP_diagnosis | not_allowed |
| automated_fibrotic_HP_diagnosis | not_allowed |
| automated_nonfibrotic_HP_diagnosis | not_allowed |
| automated_IPF_exclusion | not_allowed |
| automated_NSIP_exclusion | not_allowed |
| automated_CTD_ILD_exclusion | not_allowed |
| automated_BAL_decision | not_allowed |
| automated_serum_IgG_decision | not_allowed |
| automated_biopsy_decision | not_allowed |
| automated_treatment_selection | not_allowed |
| exposure_remediation_instruction | not_allowed |
| patient_facing_use | not_allowed |
| replacement_of_MDD | not_allowed |
| replacement_of_radiologist | not_allowed |
| replacement_of_pathologist | not_allowed |
| replacement_of_pulmonologist | not_allowed |
| replacement_of_exposure_review | not_allowed |
| replacement_of_urgent_review | not_allowed |

No HP reasoning state may override these constraints.

---

## 4. Core Fibrotic HP Parity Principle

Fibrotic HP must remain visible when evidence suggests possible HP, but the platform must not diagnose it.

Central rule:

> HP-like evidence creates a visibility prompt, not a diagnosis.

The platform must preserve:

- exposure context,
- missing exposure evidence,
- small-airway features,
- mosaic attenuation,
- air trapping,
- three-density pattern,
- centrilobular nodules,
- fibrotic distribution,
- UIP/IPF overlap,
- NSIP/OP overlap,
- BAL / serum IgG / pathology evidence gaps,
- MDD need,
- uncertainty.

The platform must block:

- automatic HP diagnosis,
- automatic HP exclusion,
- automatic IPF closure when HP-supporting features exist,
- automatic biopsy/BAL/IgG decisions,
- treatment recommendations,
- public-ready interpretation.

---

## 5. Fibrotic HP State Model

| State | Meaning | Required Behavior |
|---|---|---|
| FHP_VISIBLE | Fibrotic HP remains a visible differential reasoning family | Show HP prompt without diagnosis |
| FHP_SUPPORTING_FEATURES_PRESENT | Imaging, exposure, BAL, pathology, or clinical features support HP-like reasoning | List supporting features and limits |
| FHP_WEAKENING_FEATURES_PRESENT | Features weaken HP likelihood or support other families | Keep competing families visible |
| FHP_EXPOSURE_KNOWN | Potential inciting antigen or exposure context is present | Show exposure-support prompt; do not diagnose |
| FHP_EXPOSURE_UNKNOWN | No culprit exposure identified or history incomplete | Missing exposure must not exclude HP |
| FHP_EXPOSURE_HISTORY_INCOMPLETE | Home/work/recreational/environmental exposure review incomplete | Show missing evidence |
| FHP_SMALL_AIRWAY_FEATURE_PROMPT | Mosaic attenuation, air trapping, centrilobular nodules, or three-density pattern present | Keep HP-like prompt visible |
| FHP_FIBROSIS_PATTERN_PROMPT | Fibrotic abnormality present with HP-compatible distribution or overlap | Show pattern prompt without diagnosis |
| FHP_UIP_OVERLAP_PROMPT | UIP/probable UIP-like fibrosis coexists with HP-like features | Preserve HP/IPF boundary and MDD prompt |
| FHP_NSIP_OP_OVERLAP_PROMPT | NSIP-like or OP-like pattern overlaps HP-like features | Preserve HP/NSIP/OP visibility |
| FHP_BAL_CONTEXT_MISSING | BAL lymphocyte data absent or not integrated | Show evidence gap; do not order BAL |
| FHP_SERUM_IGG_CONTEXT_MISSING | Serum IgG / antigen evidence absent or not integrated | Show evidence gap; do not order testing |
| FHP_PATHOLOGY_CONTEXT_MISSING | Pathology unavailable or not integrated | Preserve pathology uncertainty |
| FHP_MDD_PROMPT_VISIBLE | Multidisciplinary integration needed | Keep review prompt visible |
| FHP_INDETERMINATE_FOR_HP | Features neither typical nor compatible enough for HP confidence | Preserve uncertainty and competing families |
| FHP_SOURCE_LIMITED | Source mapping partial or claim scope limited | Show source limitation |

States may coexist.

Example:

- `FHP_VISIBLE`
- plus `FHP_EXPOSURE_HISTORY_INCOMPLETE`
- plus `FHP_SMALL_AIRWAY_FEATURE_PROMPT`
- plus `FHP_UIP_OVERLAP_PROMPT`
- plus `FHP_MDD_PROMPT_VISIBLE`

is valid.

The platform must not collapse this into HP diagnosis.

---

## 6. Evidence Domain Matrix

Fibrotic HP reasoning uses multiple evidence domains.

| Evidence Domain | Possible Supporting Features | Required Platform Response | Blocked Closure |
|---|---|---|---|
| Exposure history | birds, mold, humidifier, agricultural, occupational, home, recreational, water-damage, antigen source, or suspected inciting agent | Keep exposure prompt visible | HP diagnosis |
| Missing exposure history | exposure not asked, incomplete, unavailable, or no culprit found | Missing exposure does not exclude HP | HP excluded |
| Serum IgG / antigen evidence | positive or missing serum IgG against potential antigens | Treat as exposure-supporting evidence or evidence gap | HP diagnosis from IgG alone |
| BAL lymphocytosis | BAL lymphocyte data supportive, absent, equivocal, or not integrated | Treat as evidence domain; preserve limitations | BAL ordered by platform |
| HRCT small-airway features | mosaic attenuation, air trapping, centrilobular nodules, three-density pattern | Keep HP-like imaging prompt visible | HP diagnosis |
| Fibrotic HRCT pattern | reticulation, architectural distortion, traction bronchiectasis, honeycombing, mid/lower/random distribution, basal sparing, variant distribution | Show FHP-compatible pattern prompt | HP or IPF closure |
| UIP-like fibrosis | UIP/probable UIP pattern with HP-like ancillary features | Preserve HP/IPF overlap and MDD | IPF confirmed while HP hidden |
| NSIP-like fibrosis | GGO, reticulation, traction bronchiectasis, subpleural sparing or NSIP-like pattern | Preserve HP/NSIP overlap | idiopathic NSIP diagnosis |
| OP-like pattern | consolidation, organizing pneumonia-like process | Preserve HP/OP/infection/aspiration/drug overlap | COP diagnosis |
| Histopathology | bronchiolocentric inflammation, airway-centered fibrosis, poorly formed granulomas, UIP/NSIP overlap | Preserve pathology integration prompt | HP diagnosis from isolated feature |
| Clinical course | insidious or chronic pulmonary symptoms; acute/recurrent exposure-related symptoms if present | Show clinical timeline prompt | chronic label without context |
| MDD | discordant or incomplete clinical-radiologic-pathologic data | Preserve MDD prompt | MDD omitted |

---

## 7. Exposure Reasoning Rules

| Rule ID | Rule | Required Behavior |
|---|---|---|
| FHP_EXP_001 | Exposure history is central to HP reasoning | Show exposure status explicitly |
| FHP_EXP_002 | Missing exposure history is not HP exclusion | Preserve HP visibility when other features support it |
| FHP_EXP_003 | Identified exposure is not HP diagnosis | Require HRCT/evidence/MDD context |
| FHP_EXP_004 | No culprit exposure identified does not eliminate fibrotic HP | Preserve uncertainty |
| FHP_EXP_005 | Home, work, recreational, environmental, water-damage, avian, mold, and organic/inorganic exposures should remain review-visible where relevant | Show missing exposure categories |
| FHP_EXP_006 | Exposure evidence must not suppress competing families | Keep IPF, NSIP, CTD-ILD, sarcoidosis, infection, and OP visible where relevant |

Blocked output:

- “HP excluded because no exposure was identified.”
- “HP confirmed because exposure exists.”
- “Exposure review complete” when evidence is missing.
- “No MDD needed.”

---

## 8. HRCT Reasoning Rules

| Rule ID | Rule | Required Behavior |
|---|---|---|
| FHP_HRCT_001 | Mosaic attenuation and air trapping must not be used interchangeably | Preserve technique-specific meaning |
| FHP_HRCT_002 | Air trapping requires expiratory imaging context | Mark expiratory imaging missing where relevant |
| FHP_HRCT_003 | Three-density pattern supports fibrotic HP suspicion | Show HP prompt without diagnosis |
| FHP_HRCT_004 | Small-airway features plus fibrosis strengthen HP-like reasoning | Preserve FHP visibility |
| FHP_HRCT_005 | Fibrosis alone without HP-supporting features may be indeterminate for HP | Do not force HP diagnosis |
| FHP_HRCT_006 | UIP/probable UIP pattern can overlap fibrotic HP | Preserve HP/IPF boundary |
| FHP_HRCT_007 | NSIP or OP-like patterns may overlap HP | Preserve competing family prompts |
| FHP_HRCT_008 | HRCT technique limitations must remain visible | Show missing inspiratory/expiratory/prone/quality limitations where relevant |
| FHP_HRCT_009 | Pattern is not disease | No HP diagnosis from HRCT alone |

Blocked output:

- “HP diagnosed from mosaic attenuation.”
- “HP diagnosed from air trapping.”
- “HP diagnosed from three-density pattern.”
- “UIP excludes HP.”
- “No expiratory imaging needed” when air trapping is relevant.
- “Pattern alone confirms disease.”

---

## 9. BAL / Serum IgG / Pathology Reasoning Rules

| Rule ID | Rule | Required Behavior |
|---|---|---|
| FHP_EVID_001 | Serum IgG can support exposure investigation | Do not diagnose HP from serum IgG alone |
| FHP_EVID_002 | Missing serum IgG does not exclude HP | Show evidence gap |
| FHP_EVID_003 | BAL lymphocytosis can support HP evaluation | Do not order BAL or diagnose HP |
| FHP_EVID_004 | Missing BAL data does not exclude HP | Show evidence gap |
| FHP_EVID_005 | Pathology may support HP but must be integrated | Preserve pathology/MDD prompt |
| FHP_EVID_006 | Poorly formed granulomas, bronchiolocentric inflammation, and airway-centered fibrosis support HP-like reasoning | Do not diagnose HP from isolated histologic feature |
| FHP_EVID_007 | UIP-like or NSIP-like pathology can overlap fibrotic HP | Keep competing families visible |
| FHP_EVID_008 | Pathology features suggesting alternative diagnosis must remain visible | Do not hide sarcoid, infection, aspiration, CTD, or drug reaction prompts |
| FHP_EVID_009 | No single feature is sufficient alone | Require multi-domain reasoning visibility |

Blocked output:

- “BAL confirms HP.”
- “IgG confirms HP.”
- “Granulomas confirm HP.”
- “Pathology alone settles HP.”
- “Biopsy should be performed.”
- “BAL should be performed.”

---

## 10. HP / IPF / UIP Boundary Rules

| Rule ID | Rule | Required Behavior |
|---|---|---|
| FHP_UIP_001 | Fibrotic HP may mimic IPF or other IIP | Keep HP visible when supporting features exist |
| FHP_UIP_002 | UIP pattern alone does not automatically exclude HP | Preserve exposure and small-airway review |
| FHP_UIP_003 | HP-supporting ancillary features should block premature IPF closure | Trigger MDD prompt |
| FHP_UIP_004 | Mosaic attenuation or air trapping can occur in other ILDs | Avoid overconfident HP labeling |
| FHP_UIP_005 | Probable UIP / UIP pattern with HP clues requires differential visibility | Keep both IPF/UIP and HP pathways visible |
| FHP_UIP_006 | Final diagnosis remains outside platform authority | diagnostic_authority: none |

Blocked output:

- “IPF confirmed; HP irrelevant.”
- “HP confirmed; IPF excluded.”
- “UIP pattern rules out HP.”
- “HP features rule out IPF.”
- “No multidisciplinary review needed.”

---

## 11. HP / NSIP / OP / CTD-ILD Overlap Rules

| Overlap | Required Behavior |
|---|---|
| HP vs NSIP | Preserve HP and NSIP-like prompts; show secondary-cause uncertainty |
| HP vs OP | Preserve HP, OP, infection, aspiration, drug toxicity, and CTD prompts where relevant |
| HP vs CTD-ILD | Preserve autoimmune/SARD context and HP exposure/small-airway context |
| HP vs sarcoidosis | Preserve granulomatous differential and infection/beryllium/drug mimics where relevant |
| HP vs smoking-related disease | Preserve smoking/emphysema and HP small-airway/exposure context |
| HP vs acute overlay | Preserve acute infection/edema/hemorrhage/vascular/acute exacerbation-like prompts where relevant |

Rule:

> HP visibility must not erase competing families, and competing families must not erase HP visibility.

---

## 12. Missing Evidence Matrix

| Missing Evidence | Required Prompt |
|---|---|
| Exposure history missing | HP exposure review incomplete |
| Home/work/recreational/environmental history missing | HP inciting-agent review incomplete |
| Avian/mold/water-damage/humidifier/occupational context missing | HP trigger context incomplete |
| Serum IgG context missing | Antigen-supporting evidence not assessed or not integrated |
| BAL lymphocyte context missing | BAL evidence unavailable or not integrated |
| HRCT expiratory imaging missing | Air trapping assessment limited |
| HRCT inspiratory quality limited | Mosaic/attenuation/fibrosis assessment limited |
| Prior imaging missing | Progression/stability uncertain |
| Pathology unavailable | Histologic support unavailable |
| Pathology not integrated | MDD/pathology integration incomplete |
| Autoimmune context missing | CTD-ILD competing family remains visible |
| Medication history missing | Drug toxicity competing family remains visible |
| Infection data missing | Infection overlay remains visible |
| Aspiration risk missing | Aspiration/OP overlap remains visible |
| MDD unavailable | Integrated diagnosis not established |

Required rule:

> Missing evidence must not be silently converted into exclusion.

---

## 13. MDD and Review Prompt Rules

| Rule ID | Rule | Required Behavior |
|---|---|---|
| FHP_MDD_001 | HP diagnosis is multi-domain and review-dependent | Preserve MDD prompt |
| FHP_MDD_002 | Discordant exposure, HRCT, BAL, pathology, or clinical course triggers MDD visibility | Do not force label |
| FHP_MDD_003 | HP/IPF/NSIP/OP overlap requires integrated review | Keep all families visible |
| FHP_MDD_004 | A low-confidence pathway must remain reviewable | Do not convert into final diagnosis |
| FHP_MDD_005 | Working diagnosis remains provisional | Keep confidence/re-review visible |
| FHP_MDD_006 | Urgent clinical danger must not wait for differential label | Preserve urgent review prompt where relevant |

Blocked output:

- “MDD unnecessary.”
- “HP diagnosis final.”
- “Working diagnosis permanent.”
- “No further review needed.”

---

## 14. Priority Order

When fibrotic HP reasoning is active, visibility priority is:

1. urgent clinical danger,
2. acute overlay or unstable clinical context,
3. infection / edema / hemorrhage / vascular mimic prompts,
4. HP-supporting small-airway or exposure prompt,
5. competing family prompts,
6. missing evidence,
7. source / mapping limitation,
8. MDD prompt,
9. temporal comparison prompt,
10. pattern-family description,
11. working diagnosis caveat.

HP naming must not outrank safety, missing evidence, source status, or MDD need.

---

## 15. Allowed Language

Allowed output posture:

- “Fibrotic HP-like differential prompt is visible.”
- “Exposure history is incomplete; HP cannot be excluded by missing exposure evidence.”
- “Mosaic attenuation / air trapping / three-density pattern supports HP-like reasoning but does not diagnose HP.”
- “UIP-like fibrosis and HP-like small-airway features may overlap.”
- “BAL lymphocyte context is missing or not integrated.”
- “Serum IgG context is missing or not integrated.”
- “Pathology context is missing or not integrated.”
- “MDD prompt remains visible.”
- “Final diagnosis is not established by this platform.”
- “diagnostic_authority: none”
- “treatment_authority: none”
- “public_ready: false”

---

## 16. Blocked Language

Blocked output posture:

- “HP diagnosed.”
- “Fibrotic HP confirmed.”
- “HP excluded because no exposure is known.”
- “IPF confirmed despite HP-supporting features.”
- “Mosaic attenuation confirms HP.”
- “Air trapping confirms HP.”
- “Three-density pattern confirms HP.”
- “BAL confirms HP.”
- “Serum IgG confirms HP.”
- “Biopsy should be performed.”
- “BAL should be performed.”
- “Treatment should be started.”
- “Exposure remediation should be prescribed.”
- “MDD unnecessary.”
- “Public-ready.”
- “Clinically reviewed.”

---

## 17. Testable Fibrotic HP Expectations

Future test cases should evaluate:

| Expectation ID | Expectation |
|---|---|
| FHP_001 | HP-like prompt is visible without HP diagnosis |
| FHP_002 | Exposure status is explicitly represented |
| FHP_003 | Missing exposure does not exclude HP |
| FHP_004 | Identified exposure does not diagnose HP |
| FHP_005 | Mosaic attenuation is visible without diagnostic closure |
| FHP_006 | Air trapping requires expiratory context |
| FHP_007 | Three-density pattern supports HP prompt without diagnosis |
| FHP_008 | Fibrosis plus small-airway features triggers HP visibility |
| FHP_009 | UIP/probable UIP-like fibrosis does not erase HP prompt |
| FHP_010 | HP-like features do not automatically exclude IPF/UIP |
| FHP_011 | NSIP/OP overlap remains visible |
| FHP_012 | CTD-ILD competing context remains visible |
| FHP_013 | Serum IgG evidence is treated as supportive, not diagnostic |
| FHP_014 | BAL evidence is treated as supportive, not diagnostic |
| FHP_015 | Pathology evidence requires integration |
| FHP_016 | MDD prompt remains visible |
| FHP_017 | Missing evidence is listed |
| FHP_018 | Urgent review prompt remains visible where relevant |
| FHP_019 | Diagnostic authority remains none |
| FHP_020 | Treatment authority remains none |
| FHP_021 | Public readiness remains false |
| FHP_022 | Clinically reviewed remains false |

---

## 18. Example Reasoning Scenarios

### 18.1 Fibrosis With Mosaic Attenuation and Missing Exposure History

Input reasoning context:

- fibrotic ILD pattern,
- mosaic attenuation,
- expiratory imaging incomplete,
- exposure history missing,
- no BAL data,
- MDD not documented.

Allowed platform output:

- “Fibrotic HP-like differential prompt is visible.”
- “Exposure history is missing.”
- “Mosaic attenuation supports HP-like reasoning but does not diagnose HP.”
- “Air trapping cannot be fully assessed without expiratory context.”
- “BAL context is missing.”
- “MDD prompt remains visible.”

Blocked output:

- “Fibrotic HP confirmed.”
- “HP excluded because exposure is unknown.”
- “IPF confirmed.”
- “No MDD needed.”

---

### 18.2 UIP-Like Fibrosis With Three-Density Pattern

Input reasoning context:

- basal/subpleural honeycombing or UIP-like fibrosis,
- three-density pattern present,
- exposure history incomplete,
- autoimmune context incomplete.

Allowed platform output:

- “UIP-like fibrosis and HP-like small-airway features overlap.”
- “Three-density pattern supports HP-like reasoning but does not diagnose HP.”
- “Exposure and autoimmune contexts are incomplete.”
- “HP, IPF/UIP, and CTD-ILD prompts remain visible.”
- “MDD prompt remains visible.”

Blocked output:

- “IPF confirmed; HP irrelevant.”
- “HP confirmed.”
- “CTD-ILD excluded.”
- “Treatment should be started.”

---

### 18.3 Fibrotic HP Suspected With Known Bird Exposure

Input reasoning context:

- bird exposure reported,
- fibrotic ILD,
- centrilobular nodules and air trapping,
- BAL not available,
- pathology not available.

Allowed platform output:

- “Exposure supports HP-like reasoning.”
- “Small-airway features support HP-like reasoning.”
- “BAL and pathology contexts are missing.”
- “Final HP diagnosis is not established by this platform.”
- “MDD prompt remains visible.”

Blocked output:

- “Bird exposure confirms HP.”
- “BAL should be ordered.”
- “Biopsy should be performed.”
- “Treatment should begin.”

---

### 18.4 Fibrosis Alone Without HP-Supporting Features

Input reasoning context:

- fibrotic ILD,
- UIP/probable UIP or NSIP-like pattern,
- no small-airway features,
- no exposure history documented.

Allowed platform output:

- “Fibrosis alone is not sufficient for fibrotic HP diagnosis.”
- “Exposure history is missing.”
- “HP may remain visible as a missing-evidence prompt if exposure review is incomplete.”
- “IPF/UIP or NSIP family prompts may remain visible depending on pattern.”
- “MDD prompt remains visible where uncertainty remains.”

Blocked output:

- “HP excluded.”
- “HP confirmed.”
- “IPF confirmed.”
- “No further review needed.”

---

### 18.5 OP-Like Consolidation With HP Concern

Input reasoning context:

- fibrotic abnormality,
- OP-like consolidation,
- possible exposure,
- infection data missing,
- aspiration risk missing.

Allowed platform output:

- “HP-like and OP-like prompts both remain visible.”
- “Infection and aspiration contexts are missing.”
- “Consolidation should not be collapsed into HP diagnosis.”
- “MDD and urgent review prompts remain visible where clinically relevant.”

Blocked output:

- “HP confirmed.”
- “COP confirmed.”
- “Infection excluded.”
- “Aspiration excluded.”

---

## 19. Failure Modes

The following are explicit v0.7.4 failures:

| Failure Mode | Why It Fails |
|---|---|
| HP prompt becomes HP diagnosis | Violates diagnostic_authority none |
| Missing exposure excludes HP | Violates missing evidence principle |
| Identified exposure diagnoses HP | Overclaims single evidence domain |
| Mosaic attenuation diagnoses HP | Pattern becomes disease |
| Air trapping diagnoses HP | Pattern becomes disease |
| Three-density pattern diagnoses HP | Pattern becomes disease |
| UIP-like fibrosis suppresses HP prompt | Hides mimic/overlap |
| HP-like features suppress IPF/UIP/NSIP/CTD prompts | Hides competing families |
| BAL/serum IgG/pathology becomes automatic decision | Creates clinical authority |
| MDD omitted in overlap or discordance | Weakens review governance |
| Urgent review omitted in acute danger | Weakens safety visibility |
| Treatment recommendation appears | Violates treatment_authority none |
| Public-ready claim appears | Violates public_ready false |
| Clinically reviewed claim appears | Violates clinically_reviewed false |

---

## 20. Acceptance Criteria

v0.7.4 is accepted only if:

- fibrotic HP remains a reasoning prompt, not diagnosis,
- exposure status is represented,
- missing exposure does not exclude HP,
- small-airway features are represented,
- mosaic attenuation, air trapping, and three-density pattern are visible without diagnostic closure,
- UIP/IPF overlap remains visible,
- NSIP/OP/CTD-ILD overlap remains visible,
- BAL, serum IgG, and pathology are evidence prompts only,
- MDD prompt remains visible,
- missing evidence remains visible,
- urgent review prompt remains visible where relevant,
- diagnostic_authority remains none,
- treatment_authority remains none,
- public_ready remains false,
- clinically_reviewed remains false.

---

## 21. Next Step

The next recommended step is:

- v0.7.5 — CTD-ILD / SARD-ILD Context Prompt Parity

v0.7.5 should cover:

- autoimmune/SARD context visibility,
- RA, systemic sclerosis, IIM, MCTD, and Sjögren risk context,
- HRCT/PFT evidence prompts without ordering authority,
- NSIP/OP/UIP overlap with CTD-ILD,
- missing serology/history prompts,
- rheumatology/pulmonology review visibility,
- no CTD-ILD diagnosis,
- no screening order,
- no monitoring schedule,
- no treatment authority,
- public_ready remains false.

---

## 22. Governance Statement

Fibrotic HP Reasoning Parity protects the platform from both HP erasure and HP overdiagnosis.

It does not diagnose.  
It does not treat.  
It does not decide BAL.  
It does not decide serum IgG testing.  
It does not decide biopsy.  
It does not confirm fibrotic HP.  
It does not exclude IPF.  
It does not exclude NSIP.  
It does not exclude CTD-ILD.  
It does not replace MDD.  
It does not replace clinical, radiologic, pathologic, or exposure review.  
It does not claim public readiness.  
It does not claim clinical review.

The platform remains an evidence-governed clinical reasoning platform.

The v0.7 rule remains:

> “Differential reasoning is not differential diagnosis authority.”

For fibrotic HP:

> “Read exposure, small-airway features, fibrosis pattern, missing evidence, overlap, and MDD need before naming fibrotic HP.”