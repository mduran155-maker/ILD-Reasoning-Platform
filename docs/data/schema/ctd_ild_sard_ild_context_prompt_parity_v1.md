# ILD Reasoning Platform — CTD-ILD / SARD-ILD Context Prompt Parity v1

Version: v0.7.5  
Status: ctd_ild_sard_ild_context_prompt_parity  
Scope: CTD-ILD / SARD-ILD context visibility within non-UIP fibrotic ILD differential reasoning  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This document defines CTD-ILD / SARD-ILD context prompt parity for the ILD Reasoning Platform.

It follows:

- `docs/navigation/non_uip_fibrotic_ild_differential_reasoning_entry_gate_v1.md`
- `docs/navigation/non_uip_fibrotic_ild_source_anchor_map_v1.md`
- `docs/navigation/non_uip_differential_claim_to_source_mapping_table_v1.md`
- `docs/data/schema/non_uip_differential_reasoning_family_matrix_v1.md`
- `docs/data/schema/fibrotic_hp_reasoning_parity_v1.md`

This document does not diagnose CTD-ILD.  
This document does not diagnose SARD-ILD.  
This document does not diagnose rheumatoid arthritis–associated ILD.  
This document does not diagnose systemic sclerosis–associated ILD.  
This document does not diagnose idiopathic inflammatory myopathy–associated ILD.  
This document does not diagnose mixed connective tissue disease–associated ILD.  
This document does not diagnose Sjögren disease–associated ILD.  
This document does not diagnose NSIP.  
This document does not diagnose organizing pneumonia.  
This document does not diagnose UIP/IPF.  
This document does not recommend treatment.  
This document does not order screening.  
This document does not define a monitoring schedule.  
This document does not decide biopsy.  
This document does not create public readiness.  
This document does not make v0.7 clinically reviewed.  
This document does not replace rheumatology review, pulmonology review, radiologist interpretation, pathology review, clinical correlation, MDD, or urgent clinical assessment.

Its purpose is to ensure that autoimmune / SARD context remains visible when relevant, while preventing autoimmune clues from becoming automatic diagnosis.

The v0.7 principle remains:

> “Differential reasoning is not differential diagnosis authority.”

For CTD-ILD / SARD-ILD, this becomes:

> “Read autoimmune context, SARD status, HRCT/PFT evidence, missing serology, overlap pattern, and review need before naming CTD-ILD.”

---

## 2. Source Anchors Used

| Source ID | Source | Role |
|---|---|---|
| V07_SRC_2023_ACR_CHEST_SARD_ILD_SCREEN_MONITOR | 2023 ACR/CHEST Guideline for Screening and Monitoring ILD in Systemic Autoimmune Rheumatic Diseases | Primary SARD-ILD screening/monitoring context source |
| V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION | Travis et al. 2013 ATS/ERS IIP Classification Update | NSIP / OP / CVD overlap and MDD source |
| UIP_SRC_2018_ATS_ERS_JRS_ALAT_DX | Raghu et al. 2018 ATS/ERS/JRS/ALAT IPF Diagnosis Guideline | CTD exclusion and UIP/IPF boundary inheritance |
| UIP_SRC_2022_ATS_ERS_JRS_ALAT_IPF_PPF | Raghu et al. 2022 ATS/ERS/JRS/ALAT IPF Update and PPF Guideline | PPF / non-IPF progression context inheritance |
| V07_INTERNAL_V073_FAMILY_MATRIX | Non-UIP Differential Reasoning Family Matrix | Family-state dependency |
| V07_INTERNAL_V074_FIBROTIC_HP_PARITY | Fibrotic HP Reasoning Parity | HP overlap dependency |
| V07_SRC_INTERNAL_V06_R1_R2_R3_BACKFILL | Internal v0.6 source debt/backfill chain | Source-governance inheritance |

Source status:

- SARD-ILD source review: targeted_partial
- SARD-ILD claim mapping: initial_partial_complete
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
| automated_CTD_ILD_diagnosis | not_allowed |
| automated_SARD_ILD_diagnosis | not_allowed |
| automated_RA_ILD_diagnosis | not_allowed |
| automated_SSc_ILD_diagnosis | not_allowed |
| automated_IIM_ILD_diagnosis | not_allowed |
| automated_MCTD_ILD_diagnosis | not_allowed |
| automated_SjD_ILD_diagnosis | not_allowed |
| automated_NSIP_diagnosis | not_allowed |
| automated_OP_diagnosis | not_allowed |
| automated_UIP_IPF_diagnosis | not_allowed |
| automated_screening_order | not_allowed |
| automated_monitoring_schedule | not_allowed |
| automated_PFT_order | not_allowed |
| automated_HRCT_order | not_allowed |
| automated_serology_order | not_allowed |
| automated_biopsy_decision | not_allowed |
| automated_treatment_selection | not_allowed |
| patient_facing_use | not_allowed |
| replacement_of_rheumatology_review | not_allowed |
| replacement_of_pulmonology_review | not_allowed |
| replacement_of_MDD | not_allowed |
| replacement_of_radiologist | not_allowed |
| replacement_of_pathologist | not_allowed |
| replacement_of_urgent_review | not_allowed |

No CTD-ILD / SARD-ILD reasoning state may override these constraints.

---

## 4. Core CTD-ILD / SARD-ILD Parity Principle

Autoimmune context must remain visible when relevant, but the platform must not diagnose autoimmune ILD.

Central rule:

> Autoimmune or SARD evidence creates a context prompt, not a diagnosis.

The platform must preserve:

- known SARD status,
- missing SARD status,
- autoimmune symptoms,
- autoimmune serology context,
- disease-specific risk context,
- HRCT evidence,
- PFT evidence,
- physiologic impact,
- NSIP-like overlap,
- OP-like overlap,
- UIP/probable UIP overlap,
- HP overlap,
- progression / monitoring context,
- MDD / co-management prompt,
- uncertainty.

The platform must block:

- automatic CTD-ILD diagnosis,
- automatic exclusion of CTD-ILD when autoimmune data are missing,
- automatic screening order,
- automatic monitoring interval,
- automatic treatment recommendation,
- automatic biopsy decision,
- public-ready interpretation.

---

## 5. CTD-ILD / SARD-ILD State Model

| State | Meaning | Required Behavior |
|---|---|---|
| CTD_CONTEXT_VISIBLE | Autoimmune / SARD context is relevant | Show CTD/SARD prompt without diagnosis |
| SARD_KNOWN | A SARD diagnosis is documented | Preserve SARD-ILD context and evidence needs |
| SARD_UNKNOWN | SARD status is unknown or not documented | Missing SARD status does not exclude CTD-ILD |
| AUTOIMMUNE_SYMPTOM_CONTEXT_PRESENT | Symptoms/signs suggest autoimmune disease | Keep CTD-ILD prompt visible |
| AUTOIMMUNE_SYMPTOM_CONTEXT_MISSING | Autoimmune history/exam incomplete | Show missing evidence |
| SEROLOGY_PRESENT | Autoimmune serology is available | Treat as context evidence, not diagnosis |
| SEROLOGY_MISSING | Serology is absent or not integrated | Missing serology does not exclude CTD-ILD |
| SARD_RISK_CONTEXT_VISIBLE | RA, SSc, IIM, MCTD, or Sjögren risk context exists | Show disease-specific risk prompt |
| HRCT_CONTEXT_PRESENT | HRCT evidence is available | Show pattern/evidence relationship |
| HRCT_CONTEXT_MISSING | HRCT unavailable or inadequate | Show missing imaging evidence |
| PFT_CONTEXT_PRESENT | PFT evidence is available | Show physiologic impact context |
| PFT_CONTEXT_MISSING | PFT unavailable or not integrated | Show missing physiologic evidence |
| CTD_NSIP_OVERLAP_PROMPT | NSIP-like pattern overlaps autoimmune context | Preserve CTD-ILD and NSIP prompts |
| CTD_OP_OVERLAP_PROMPT | OP-like pattern overlaps autoimmune context | Preserve CTD-ILD and OP prompts |
| CTD_UIP_OVERLAP_PROMPT | UIP/probable UIP-like fibrosis overlaps autoimmune context | Preserve CTD-ILD and UIP/IPF boundary prompts |
| CTD_HP_OVERLAP_PROMPT | HP-like features overlap autoimmune context | Preserve HP and CTD-ILD prompts |
| CTD_PROGRESSion_CONTEXT_PROMPT | Monitoring/progression evidence is relevant | Show context without schedule/order |
| CTD_MDD_PROMPT_VISIBLE | Rheumatology/pulmonology/radiology integration needed | Preserve review prompt |
| CTD_SOURCE_LIMITED | Source mapping partial or claim scope limited | Show source limitation |

States may coexist.

Example:

- `SARD_UNKNOWN`
- plus `SEROLOGY_MISSING`
- plus `CTD_NSIP_OVERLAP_PROMPT`
- plus `PFT_CONTEXT_MISSING`
- plus `CTD_MDD_PROMPT_VISIBLE`

is valid.

The platform must not collapse this into CTD-ILD diagnosis.

---

## 6. SARD Family Context Matrix

| SARD Family | Context Prompt | Required Behavior | Blocked Closure |
|---|---|---|---|
| Rheumatoid arthritis | RA history, high-titer RF/anti-CCP, smoking, older age at RA onset, male sex, high disease activity context where documented | Keep RA-ILD context visible | RA-ILD diagnosis |
| Systemic sclerosis | SSc history, anti-Scl-70, nucleolar ANA, diffuse cutaneous subtype, early disease, elevated inflammatory markers where documented | Keep SSc-ILD context visible | SSc-ILD diagnosis |
| Idiopathic inflammatory myopathy | IIM, antisynthetase syndrome, anti-MDA5, Jo-1/PL7/PL12/EJ/OJ/KS/Ha/Zo, mechanic’s hands, arthritis/arthralgia where documented | Keep IIM-ILD context visible | IIM-ILD diagnosis |
| Mixed connective tissue disease | MCTD history, Raynaud, dysphagia, SSc-like clinical/lab features where documented | Keep MCTD-ILD context visible | MCTD-ILD diagnosis |
| Sjögren disease | Sjögren history, anti-Ro52, ANA, Raynaud, older age, lymphopenia where documented | Keep Sjögren-ILD context visible | Sjögren-ILD diagnosis |
| Unknown / incomplete autoimmune status | Autoimmune history or serology incomplete | Preserve CTD-ILD missing evidence prompt | CTD-ILD excluded |

The absence of listed risk factors must not be treated as exclusion.

---

## 7. Evidence Domain Matrix

| Evidence Domain | Possible Supporting Features | Required Platform Response | Blocked Closure |
|---|---|---|---|
| Known SARD diagnosis | RA, SSc, IIM, MCTD, Sjögren documented | Show disease-specific context prompt | CTD-ILD diagnosis |
| Autoimmune symptoms/signs | Raynaud, mechanic’s hands, arthritis/arthralgia, dysphagia, sicca, skin features, muscle weakness where documented | Show autoimmune context prompt | CTD-ILD diagnosis |
| Autoimmune serology | ANA, RF, anti-CCP, Scl-70, antisynthetase antibodies, anti-MDA5, anti-Ro52, SSA/SSB, myositis panel where documented | Treat as supporting context | CTD-ILD diagnosis from serology alone |
| HRCT | ILD presence/pattern, fibrosis, NSIP-like, OP-like, UIP-like, air trapping, dependent opacity limitation | Show imaging context and limitations | automated HRCT order |
| PFT | spirometry, lung volumes, DLCO, FVC trend where available | Show physiologic context | automated PFT order |
| Monitoring evidence | HRCT/PFT trend, progression suspicion, ambulatory desaturation where available | Show monitoring context | automated monitoring schedule |
| Co-management | rheumatology/pulmonology/radiology/pathology integration | Preserve review prompt | replacement of clinician review |
| Missing clinical context | SARD status or autoimmune review incomplete | Show missing evidence | CTD-ILD excluded |
| Missing serology | serology absent or not integrated | Show missing evidence | CTD excluded |
| Missing HRCT/PFT | imaging/physiology absent | Show evidence gap | disease state settled |
| Pathology | NSIP/OP/UIP-like/pathology pattern where present | Require integrated interpretation | diagnosis from pathology alone |

---

## 8. Screening / Monitoring Context Rules

The platform may represent screening and monitoring context as evidence visibility only.

| Rule ID | Rule | Required Behavior |
|---|---|---|
| CTD_SCREEN_001 | HRCT and PFTs may be relevant in SARD-ILD screening context | Show evidence context without ordering tests |
| CTD_SCREEN_002 | HRCT and PFTs provide complementary information | Show imaging vs physiologic domains separately |
| CTD_SCREEN_003 | Screening is patient-specific and shared-decision dependent | Do not create universal screening instruction |
| CTD_SCREEN_004 | Surgical lung biopsy is not routine screening | Block platform biopsy decision |
| CTD_MON_001 | HRCT and PFTs may be relevant in monitoring SARD-ILD progression | Show monitoring context without schedule authority |
| CTD_MON_002 | Monitoring frequency depends on disease/context | Do not generate schedule |
| CTD_MON_003 | Ambulatory desaturation may be monitoring evidence | Show context only |
| CTD_MON_004 | Chest radiography, 6MWD, bronchoscopy limits should remain source-bound | Do not generalize beyond source scope |

Blocked output:

- “Order HRCT.”
- “Order PFTs.”
- “Repeat HRCT every X months.”
- “Screen all RA patients.”
- “Biopsy should be performed.”
- “Monitoring schedule set by platform.”

---

## 9. Pattern Overlap Rules

| Overlap | Required Behavior |
|---|---|
| CTD-ILD vs NSIP | Preserve autoimmune context and NSIP-like prompt |
| CTD-ILD vs OP | Preserve autoimmune context and OP-like prompt |
| CTD-ILD vs UIP/IPF | Preserve autoimmune context and UIP/IPF boundary; do not force IPF |
| CTD-ILD vs HP | Preserve autoimmune and exposure/small-airway prompts |
| CTD-ILD vs sarcoidosis | Preserve autoimmune and granulomatous differential prompts |
| CTD-ILD vs drug toxicity | Preserve medication/therapy history prompt |
| CTD-ILD vs infection | Preserve infection overlay prompt |
| CTD-ILD vs edema/vascular/hemorrhage | Preserve acute danger prompts where relevant |
| CTD-ILD vs unclassifiable ILD | Preserve discordance and MDD prompt |

Rule:

> Autoimmune context must not erase competing families, and competing families must not erase autoimmune context.

---

## 10. CTD-ILD / NSIP / OP / UIP Boundary Rules

| Rule ID | Rule | Required Behavior |
|---|---|---|
| CTD_BOUND_001 | NSIP-like pattern can be associated with CTD context | Do not label idiopathic NSIP prematurely |
| CTD_BOUND_002 | OP-like pattern can be secondary to CTD context | Do not label cryptogenic OP prematurely |
| CTD_BOUND_003 | UIP/probable UIP-like pattern does not exclude CTD-ILD | Preserve autoimmune context |
| CTD_BOUND_004 | CTD-ILD context does not automatically exclude IPF/UIP | Keep competing families visible |
| CTD_BOUND_005 | Missing autoimmune context blocks confident IPF closure | Preserve CTD missing evidence prompt |
| CTD_BOUND_006 | Pathology pattern requires clinical/rheumatologic integration | Preserve MDD prompt |
| CTD_BOUND_007 | Disease label must not outrun source mapping | Show source status where relevant |

Blocked output:

- “Idiopathic NSIP confirmed.”
- “Cryptogenic OP confirmed.”
- “IPF confirmed despite missing autoimmune context.”
- “CTD-ILD confirmed from serology.”
- “CTD-ILD excluded because serology missing.”
- “No MDD needed.”

---

## 11. Missing Evidence Matrix

| Missing Evidence | Required Prompt |
|---|---|
| Known SARD status missing | SARD context not established |
| Autoimmune symptom history missing | Autoimmune review incomplete |
| Rheumatologic exam missing | Clinical autoimmune context incomplete |
| Serology missing | Autoimmune serologic context incomplete |
| Disease-specific antibody data missing | SARD-specific risk context incomplete |
| Medication history missing | Drug toxicity / therapy-related ILD remains visible |
| Exposure history missing | HP and occupational mimic remain visible |
| HRCT missing | Imaging pattern context unavailable |
| HRCT technique incomplete | Pattern confidence limited |
| PFT missing | Physiologic impact unknown |
| Prior PFT trend missing | Progression/stability uncertain |
| Prior HRCT missing | Temporal comparison uncertain |
| Pathology missing | Histologic context unavailable |
| Pathology not integrated | MDD/pathology integration incomplete |
| Rheumatology review missing | CTD/SARD review context incomplete |
| Pulmonology review missing | ILD clinical integration incomplete |
| MDD unavailable | Integrated diagnosis not established |
| Acute symptoms context missing | Urgent overlay risk incompletely assessed |

Required rule:

> Missing autoimmune evidence must not be silently converted into CTD-ILD exclusion.

---

## 12. MDD / Co-Management Prompt Rules

| Rule ID | Rule | Required Behavior |
|---|---|---|
| CTD_MDD_001 | CTD-ILD reasoning requires integration of clinical, serologic, radiologic, physiologic, and sometimes pathologic domains | Preserve MDD/co-management prompt |
| CTD_MDD_002 | Rheumatology and pulmonology review remain visible where relevant | Do not replace clinician review |
| CTD_MDD_003 | Discordant imaging and autoimmune context triggers review prompt | Do not force single label |
| CTD_MDD_004 | NSIP/OP/UIP overlap with autoimmune context requires integrated review | Preserve competing families |
| CTD_MDD_005 | Working diagnosis remains provisional and reviewable | Preserve uncertainty |
| CTD_MDD_006 | Acute danger must not wait for autoimmune classification | Preserve urgent review prompt |

Blocked output:

- “Rheumatology review unnecessary.”
- “Pulmonology review unnecessary.”
- “MDD unnecessary.”
- “Working diagnosis final.”
- “No further review needed.”

---

## 13. Urgent Review / Acute Overlay Rules

SARD-ILD context may coexist with acute processes.

| Acute / Overlay Concern | Required Prompt |
|---|---|
| New GGO or consolidation | infection, edema, hemorrhage, drug toxicity, acute exacerbation-like overlay, OP overlap visible |
| Rapid worsening dyspnea or oxygenation | urgent review visible |
| Fever or inflammatory markers | infection/inflammatory overlay visible |
| Hemoptysis or anemia | hemorrhage visible |
| Vascular risk or acute hypoxemia | vascular concern visible |
| New medication or therapy | drug toxicity visible |
| Immunosuppressed context | infection and drug/toxicity prompts visible |
| OP-like consolidation | infection, aspiration, drug, CTD, OP overlap visible |

Rule:

> Autoimmune context must not hide acute danger.

---

## 14. Source Scope Limits

The ACR/CHEST SARD-ILD source is used for screening and monitoring context in people with defined SARD categories.

It must not be overextended into:

- diagnosing SARD in newly detected ILD without known SARD,
- complete autoimmune ILD diagnostic ontology,
- treatment recommendations,
- universal screening instructions,
- patient-facing triage,
- public-ready clinical decision support.

Source-status rule:

> A SARD-ILD source can support context prompts, but it does not create platform authority.

---

## 15. Priority Order

When CTD-ILD / SARD-ILD reasoning is active, visibility priority is:

1. urgent clinical danger,
2. acute overlay or unstable clinical context,
3. infection / hemorrhage / vascular / edema mimic prompts,
4. known SARD or autoimmune context,
5. NSIP / OP / UIP / HP overlap prompts,
6. missing autoimmune/serology/HRCT/PFT evidence,
7. source / mapping limitation,
8. MDD / co-management prompt,
9. temporal comparison prompt,
10. pattern-family description,
11. working diagnosis caveat.

Autoimmune naming must not outrank safety, missing evidence, source status, or review need.

---

## 16. Allowed Language

Allowed output posture:

- “CTD-ILD / SARD-ILD context prompt is visible.”
- “Known SARD history makes autoimmune ILD context review-visible.”
- “Autoimmune history is incomplete.”
- “Serology context is missing or not integrated.”
- “HRCT and PFT evidence domains should remain visible.”
- “NSIP-like pattern and autoimmune context overlap.”
- “OP-like pattern and autoimmune context overlap.”
- “UIP-like pattern does not exclude CTD-ILD.”
- “CTD-ILD context does not diagnose CTD-ILD.”
- “Rheumatology / pulmonology / MDD review remains visible.”
- “Final diagnosis is not established by this platform.”
- “diagnostic_authority: none”
- “treatment_authority: none”
- “public_ready: false”

---

## 17. Blocked Language

Blocked output posture:

- “CTD-ILD diagnosed.”
- “SARD-ILD confirmed.”
- “RA-ILD confirmed.”
- “SSc-ILD confirmed.”
- “IIM-ILD confirmed.”
- “MCTD-ILD confirmed.”
- “Sjögren-ILD confirmed.”
- “CTD-ILD excluded because serology is missing.”
- “IPF confirmed despite missing autoimmune context.”
- “Order HRCT.”
- “Order PFTs.”
- “Repeat monitoring every X months.”
- “Biopsy should be performed.”
- “Treatment should be started.”
- “Rheumatology review unnecessary.”
- “MDD unnecessary.”
- “Public-ready.”
- “Clinically reviewed.”

---

## 18. Testable CTD-ILD / SARD-ILD Expectations

Future test cases should evaluate:

| Expectation ID | Expectation |
|---|---|
| CTD_001 | CTD/SARD context prompt is visible without diagnosis |
| CTD_002 | Known SARD status is represented |
| CTD_003 | Unknown SARD status does not exclude CTD-ILD |
| CTD_004 | Autoimmune symptom/sign context is represented |
| CTD_005 | Missing autoimmune history is listed |
| CTD_006 | Serology context is represented |
| CTD_007 | Missing serology does not exclude CTD-ILD |
| CTD_008 | HRCT evidence domain is visible without order authority |
| CTD_009 | PFT evidence domain is visible without order authority |
| CTD_010 | Screening context does not become screening order |
| CTD_011 | Monitoring context does not become monitoring schedule |
| CTD_012 | NSIP overlap remains visible |
| CTD_013 | OP overlap remains visible |
| CTD_014 | UIP/IPF overlap remains visible |
| CTD_015 | HP overlap remains visible |
| CTD_016 | Drug toxicity and infection remain visible where relevant |
| CTD_017 | Rheumatology/pulmonology review remains visible |
| CTD_018 | MDD prompt remains visible where relevant |
| CTD_019 | Urgent review prompt remains visible where relevant |
| CTD_020 | Diagnostic authority remains none |
| CTD_021 | Treatment authority remains none |
| CTD_022 | Public readiness remains false |
| CTD_023 | Clinically reviewed remains false |

---

## 19. Example Reasoning Scenarios

### 19.1 NSIP-Like Pattern With Missing Autoimmune Context

Input reasoning context:

- bilateral GGO and reticulation,
- traction bronchiectasis,
- possible subpleural sparing,
- autoimmune history incomplete,
- serology missing,
- MDD not documented.

Allowed platform output:

- “NSIP-like pattern prompt is visible.”
- “CTD-ILD context is incomplete.”
- “Autoimmune history and serology are missing.”
- “Idiopathic NSIP should not be named prematurely.”
- “MDD / rheumatology-pulmonology review remains visible.”

Blocked output:

- “Idiopathic NSIP confirmed.”
- “CTD-ILD excluded.”
- “No MDD needed.”
- “Treatment should be started.”

---

### 19.2 Known Systemic Sclerosis With Fibrotic ILD

Input reasoning context:

- known systemic sclerosis,
- fibrotic ILD on HRCT,
- PFT trend unavailable,
- prior HRCT unavailable,
- no acute symptoms.

Allowed platform output:

- “SARD-ILD context prompt is visible.”
- “Known systemic sclerosis makes CTD-ILD context review-visible.”
- “PFT and prior HRCT comparison are missing.”
- “Progression cannot be assessed confidently without temporal/physiologic context.”
- “Final diagnosis is not established by this platform.”

Blocked output:

- “SSc-ILD confirmed.”
- “Monitoring interval set.”
- “Treatment should begin.”
- “Public-ready.”

---

### 19.3 UIP-Like Pattern With Missing Serology

Input reasoning context:

- UIP/probable UIP-like fibrosis,
- serology missing,
- autoimmune symptoms not documented,
- exposure history incomplete.

Allowed platform output:

- “UIP-like fibrosis is visible.”
- “Autoimmune and exposure contexts are incomplete.”
- “CTD-ILD and HP prompts remain visible as missing-evidence prompts.”
- “IPF closure is blocked until known-cause review is complete.”
- “MDD prompt remains visible.”

Blocked output:

- “IPF confirmed.”
- “CTD-ILD excluded.”
- “HP excluded.”
- “No further review needed.”

---

### 19.4 OP-Like Consolidation With Rheumatoid Arthritis

Input reasoning context:

- known rheumatoid arthritis,
- OP-like consolidation,
- infection data missing,
- aspiration risk unknown,
- medication history missing.

Allowed platform output:

- “CTD-ILD context prompt is visible.”
- “OP-like pattern prompt is visible.”
- “Infection, aspiration, and drug toxicity contexts are missing.”
- “Cryptogenic OP should not be named prematurely.”
- “Urgent review prompt remains visible where clinically relevant.”

Blocked output:

- “COP confirmed.”
- “RA-ILD confirmed.”
- “Infection excluded.”
- “Aspiration excluded.”
- “Treatment should be started.”

---

### 19.5 IIM / Antisynthetase Context With Rapid Worsening

Input reasoning context:

- known or suspected idiopathic inflammatory myopathy / antisynthetase context,
- rapid dyspnea progression,
- new GGO,
- infection data incomplete,
- PFT trend missing.

Allowed platform output:

- “SARD-ILD / IIM-ILD context prompt is visible.”
- “Rapid worsening and new GGO trigger acute overlay review.”
- “Infection and other acute mimics remain visible.”
- “PFT trend is missing.”
- “Urgent clinical review prompt remains visible.”

Blocked output:

- “IIM-ILD confirmed.”
- “Acute exacerbation confirmed.”
- “Infection excluded.”
- “Monitoring schedule set by platform.”

---

## 20. Failure Modes

The following are explicit v0.7.5 failures:

| Failure Mode | Why It Fails |
|---|---|
| CTD/SARD prompt becomes diagnosis | Violates diagnostic_authority none |
| Missing serology excludes CTD-ILD | Violates missing evidence principle |
| Known SARD automatically diagnoses ILD subtype | Overclaims context |
| NSIP-like pattern becomes idiopathic NSIP without secondary-cause review | Hides CTD context |
| OP-like pattern becomes COP without secondary-cause review | Hides CTD/infection/aspiration/drug context |
| UIP-like pattern suppresses autoimmune context | Premature IPF closure |
| HRCT/PFT context becomes order | Creates clinical authority |
| Monitoring context becomes schedule | Creates management authority |
| Surgical biopsy decision appears | Creates biopsy authority |
| Rheumatology/pulmonology review omitted | Weakens co-management governance |
| MDD omitted in overlap or discordance | Weakens review governance |
| Urgent review omitted in acute danger | Weakens safety visibility |
| Treatment recommendation appears | Violates treatment_authority none |
| Public-ready claim appears | Violates public_ready false |
| Clinically reviewed claim appears | Violates clinically_reviewed false |

---

## 21. Acceptance Criteria

v0.7.5 is accepted only if:

- CTD-ILD / SARD-ILD remains a context prompt, not diagnosis,
- known SARD status is represented,
- unknown SARD status does not exclude CTD-ILD,
- autoimmune symptoms/signs and serology context remain visible,
- missing autoimmune evidence remains visible,
- HRCT and PFT are evidence domains only,
- screening context does not become screening order,
- monitoring context does not become monitoring schedule,
- NSIP / OP / UIP / HP overlaps remain visible,
- rheumatology and pulmonology review remain visible where relevant,
- MDD prompt remains visible,
- urgent review prompt remains visible where relevant,
- diagnostic_authority remains none,
- treatment_authority remains none,
- public_ready remains false,
- clinically_reviewed remains false.

---

## 22. Next Step

The next recommended step is:

- v0.7.6 — NSIP / OP / Unclassifiable IIP Reasoning Parity

v0.7.6 should cover:

- NSIP-like pattern visibility,
- idiopathic NSIP vs secondary NSIP caution,
- OP-like consolidation and migratory opacity prompt,
- cryptogenic OP vs secondary OP caution,
- unclassifiable IIP due to insufficient data or discordance,
- coexisting patterns,
- MDD integration,
- no NSIP diagnosis,
- no OP/COP diagnosis,
- no treatment authority,
- public_ready remains false.

---

## 23. Governance Statement

CTD-ILD / SARD-ILD Context Prompt Parity protects the platform from both autoimmune-context erasure and autoimmune overdiagnosis.

It does not diagnose.  
It does not treat.  
It does not order screening.  
It does not define monitoring intervals.  
It does not decide biopsy.  
It does not confirm CTD-ILD.  
It does not confirm SARD-ILD.  
It does not exclude IPF.  
It does not exclude HP.  
It does not exclude NSIP or OP.  
It does not replace rheumatology review.  
It does not replace pulmonology review.  
It does not replace MDD.  
It does not claim public readiness.  
It does not claim clinical review.

The platform remains an evidence-governed clinical reasoning platform.

The v0.7 rule remains:

> “Differential reasoning is not differential diagnosis authority.”

For CTD-ILD / SARD-ILD:

> “Read autoimmune context, SARD status, HRCT/PFT evidence, missing serology, overlap pattern, and review need before naming CTD-ILD.”