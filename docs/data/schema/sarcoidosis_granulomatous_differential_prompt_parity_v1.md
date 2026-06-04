# ILD Reasoning Platform — Sarcoidosis / Granulomatous Differential Prompt Parity v1

Version: v0.7.7  
Status: sarcoidosis_granulomatous_differential_prompt_parity  
Scope: Sarcoidosis-like and granulomatous differential prompt visibility within non-UIP fibrotic ILD differential expansion  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This document defines Sarcoidosis / Granulomatous Differential Prompt Parity for the ILD Reasoning Platform.

It follows:

- `docs/navigation/non_uip_fibrotic_ild_differential_reasoning_entry_gate_v1.md`
- `docs/navigation/non_uip_fibrotic_ild_source_anchor_map_v1.md`
- `docs/navigation/non_uip_differential_claim_to_source_mapping_table_v1.md`
- `docs/data/schema/non_uip_differential_reasoning_family_matrix_v1.md`
- `docs/data/schema/fibrotic_hp_reasoning_parity_v1.md`
- `docs/data/schema/ctd_ild_sard_ild_context_prompt_parity_v1.md`
- `docs/data/schema/nsip_op_unclassifiable_iip_reasoning_parity_v1.md`

This document does not diagnose sarcoidosis.  
This document does not diagnose pulmonary sarcoidosis.  
This document does not diagnose granulomatous ILD.  
This document does not diagnose tuberculosis.  
This document does not diagnose nontuberculous mycobacterial infection.  
This document does not diagnose fungal infection.  
This document does not diagnose berylliosis.  
This document does not diagnose malignancy.  
This document does not diagnose hypersensitivity pneumonitis.  
This document does not diagnose drug-induced granulomatous disease.  
This document does not recommend treatment.  
This document does not decide tissue sampling.  
This document does not decide lymph node sampling.  
This document does not create public readiness.  
This document does not make v0.7 clinically reviewed.  
This document does not replace radiologist interpretation, pathology review, clinical correlation, microbiology, pulmonology, rheumatology, occupational medicine, MDD, or urgent clinical assessment.

Its purpose is to ensure that sarcoid-like and granulomatous differential prompts remain visible without becoming automatic sarcoidosis diagnosis.

The v0.7 principle remains:

> “Differential reasoning is not differential diagnosis authority.”

For sarcoidosis / granulomatous differential reasoning, this becomes:

> “Read compatible presentation, granuloma context, alternative causes, infection risk, exposure history, source limits, and review need before naming sarcoidosis.”

---

## 2. Source Anchors Used

| Source ID | Source | Role |
|---|---|---|
| V07_SRC_2020_ATS_SARCOIDOSIS_GUIDELINE | Crouser et al. 2020 ATS Diagnosis and Detection of Sarcoidosis Guideline | Primary sarcoidosis / granulomatous differential source |
| V07_SRC_2020_ATS_JRS_ALAT_HP_GUIDELINE | Raghu et al. 2020 ATS/JRS/ALAT HP Guideline | HP granulomatous mimic / overlap source |
| V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION | Travis et al. 2013 ATS/ERS IIP Classification Update | IIP / OP / NSIP / unclassifiable overlap source |
| V07_SRC_2023_ACR_CHEST_SARD_ILD_SCREEN_MONITOR | 2023 ACR/CHEST SARD-ILD Screening and Monitoring Guideline | CTD/SARD overlap source |
| UIP_SRC_2018_ATS_ERS_JRS_ALAT_DX | Raghu et al. 2018 ATS/ERS/JRS/ALAT IPF Diagnosis Guideline | UIP/IPF boundary inheritance |
| V07_INTERNAL_V073_FAMILY_MATRIX | Non-UIP Differential Reasoning Family Matrix | Family-state dependency |
| V07_INTERNAL_V074_FIBROTIC_HP_PARITY | Fibrotic HP Reasoning Parity | HP overlap dependency |
| V07_INTERNAL_V075_CTD_ILD_PARITY | CTD-ILD / SARD-ILD Context Prompt Parity | CTD overlap dependency |
| V07_INTERNAL_V076_NSIP_OP_UNCLASSIFIABLE_PARITY | NSIP / OP / Unclassifiable IIP Reasoning Parity | mixed-pattern dependency |
| V07_SRC_INTERNAL_V06_R1_R2_R3_BACKFILL | Internal v0.6 source debt/backfill chain | Source-governance inheritance |

Source status:

- sarcoidosis source review: targeted_partial
- sarcoidosis claim mapping: initial_partial_complete
- infection mimic source: broader_source_needed
- berylliosis source: source_needed_for_dedicated_parity
- occupational granulomatous disease source: source_needed_for_dedicated_parity
- drug-induced granulomatous disease source: source_needed_for_dedicated_parity
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
| automated_sarcoidosis_diagnosis | not_allowed |
| automated_pulmonary_sarcoidosis_diagnosis | not_allowed |
| automated_granulomatous_ILD_diagnosis | not_allowed |
| automated_TB_diagnosis | not_allowed |
| automated_NTM_diagnosis | not_allowed |
| automated_fungal_infection_diagnosis | not_allowed |
| automated_berylliosis_diagnosis | not_allowed |
| automated_malignancy_diagnosis | not_allowed |
| automated_HP_diagnosis | not_allowed |
| automated_drug_reaction_diagnosis | not_allowed |
| automated_tissue_sampling_decision | not_allowed |
| automated_lymph_node_sampling_decision | not_allowed |
| automated_microbiology_order | not_allowed |
| automated_treatment_selection | not_allowed |
| patient_facing_use | not_allowed |
| replacement_of_MDD | not_allowed |
| replacement_of_clinician | not_allowed |
| replacement_of_radiologist | not_allowed |
| replacement_of_pathologist | not_allowed |
| replacement_of_pulmonologist | not_allowed |
| replacement_of_microbiology | not_allowed |
| replacement_of_occupational_medicine_review | not_allowed |
| replacement_of_urgent_review | not_allowed |

No sarcoidosis or granulomatous differential reasoning state may override these constraints.

---

## 4. Core Sarcoidosis / Granulomatous Differential Principle

Sarcoid-like features must remain visible when relevant, but the platform must not diagnose sarcoidosis.

Central rule:

> Sarcoid-like evidence creates a granulomatous differential prompt, not a diagnosis.

The platform must preserve:

- compatible clinical / radiologic context,
- lymphadenopathy context,
- perilymphatic distribution context,
- extrapulmonary clue context,
- granuloma context,
- nonnecrotizing granulomatous inflammation context,
- infection mimic visibility,
- berylliosis / occupational mimic visibility,
- malignancy / sarcoid-like reaction visibility,
- HP mimic visibility,
- drug reaction visibility,
- immune disorder mimic visibility,
- tissue sampling uncertainty,
- close follow-up prompt where relevant,
- MDD / integrated review need,
- source-needed status for dedicated mimic domains,
- uncertainty.

The platform must block:

- automatic sarcoidosis diagnosis,
- automatic exclusion of infection,
- automatic exclusion of malignancy,
- automatic exclusion of HP,
- automatic exclusion of berylliosis or occupational disease,
- automatic lymph node/tissue sampling decisions,
- treatment recommendations,
- public-ready interpretation.

---

## 5. Sarcoidosis / Granulomatous State Model

| State | Meaning | Required Behavior |
|---|---|---|
| SARCOID_PROMPT_VISIBLE | Sarcoid-like reasoning remains visible | Show prompt without diagnosis |
| COMPATIBLE_PRESENTATION_PROMPT | Clinical, radiologic, or extrapulmonary context is compatible | Show compatibility as prompt only |
| PRESENTATION_INCOMPLETE | Clinical presentation data are incomplete | Show missing evidence |
| LYMPHADENOPATHY_PROMPT | Bilateral hilar or mediastinal lymphadenopathy is present or suspected | Keep sarcoid-like prompt visible |
| PERILYMPHATIC_PATTERN_PROMPT | Perilymphatic nodules / lymphatic distribution suspected | Keep sarcoid-like prompt visible |
| EXTRAPULMONARY_CLUE_PROMPT | Ocular, skin, cardiac, renal, neurologic, calcium, or systemic clue relevant | Show extrapulmonary context prompt |
| GRANULOMA_CONTEXT_PRESENT | Granulomatous inflammation reported | Show granulomatous differential prompt |
| NONNECROTIZING_GRANULOMA_PROMPT | Nonnecrotizing granulomatous inflammation reported | Support sarcoid-like prompt without diagnosis |
| GRANULOMA_CONTEXT_MISSING | Tissue/pathology not available or not integrated | Show missing evidence |
| ALTERNATIVE_GRANULOMATOUS_CAUSE_VISIBLE | Alternative granulomatous causes possible | Block sarcoidosis closure |
| INFECTION_MIMIC_VISIBLE | TB, NTM, fungal, parasitic, or other infectious mimic possible | Preserve microbiology/infection prompt |
| NONINFECTIOUS_MIMIC_VISIBLE | Malignancy, berylliosis, HP, drug reaction, immune disorder, or other noninfectious mimic possible | Preserve mimic prompt |
| SAMPLING_DECISION_UNCERTAIN | Tissue or lymph node sampling context exists | Show uncertainty; do not decide sampling |
| CLOSE_FOLLOWUP_PROMPT | Observation / follow-up context relevant | Show follow-up prompt without schedule |
| SARCOID_MDD_PROMPT_VISIBLE | Integrated review needed | Preserve MDD/review prompt |
| SARCOID_SOURCE_LIMITED | Source mapping partial or dedicated mimic source absent | Show source limitation |

States may coexist.

Example:

- `SARCOID_PROMPT_VISIBLE`
- plus `LYMPHADENOPATHY_PROMPT`
- plus `GRANULOMA_CONTEXT_MISSING`
- plus `INFECTION_MIMIC_VISIBLE`
- plus `SAMPLING_DECISION_UNCERTAIN`
- plus `SARCOID_MDD_PROMPT_VISIBLE`

is valid.

The platform must not collapse this into sarcoidosis diagnosis.

---

## 6. Diagnostic Criteria Prompt Matrix

The ATS sarcoidosis source frames sarcoidosis diagnosis around three major criteria. In platform terms, these are prompt domains, not authority domains.

| Criterion Domain | Platform Prompt | Required Behavior | Blocked Closure |
|---|---|---|---|
| Compatible clinical presentation | compatible presentation prompt | Show compatible context and limitations | sarcoidosis diagnosis |
| Nonnecrotizing granulomatous inflammation | granuloma context prompt | Show tissue/pathology context and limitations | sarcoidosis diagnosis from pathology alone |
| Exclusion of alternative granulomatous causes | alternative cause visibility | Preserve infection/noninfectious mimics | alternative causes excluded by platform |

Required rule:

> The platform may represent the three criteria as review prompts, but it cannot confirm that the criteria are satisfied.

---

## 7. Clinical / Radiologic Context Matrix

| Context Domain | Possible Prompt | Required Platform Response | Blocked Closure |
|---|---|---|---|
| Bilateral hilar lymphadenopathy | lymphadenopathy prompt | Keep sarcoid-like differential visible | sarcoidosis diagnosis |
| Mediastinal lymphadenopathy | lymphadenopathy prompt | Preserve malignancy / infection / sarcoid-like differential | sarcoidosis diagnosis |
| Perilymphatic nodules | perilymphatic pattern prompt | Keep sarcoid-like prompt visible | sarcoidosis diagnosis |
| Upper-lung or perihilar fibrosis | sarcoid-like fibrotic prompt | Preserve sarcoidosis vs HP vs pneumoconiosis vs UIP/NSIP visibility | sarcoidosis diagnosis |
| Extrapulmonary signs | extrapulmonary clue prompt | Preserve multi-organ context and missing evidence | sarcoidosis diagnosis |
| Highly suggestive syndromic context | high-suspicion presentation prompt | Preserve follow-up and alternative review | diagnosis / sampling decision by platform |
| Atypical presentation | atypical sarcoid prompt | Elevate alternative cause visibility | sarcoidosis closure |
| Progressive fibrotic disease | fibrotic sarcoid-like prompt | Preserve temporal comparison and differential visibility | treatment decision |
| Acute systemic symptoms | infection / malignancy / inflammatory mimic prompt | Preserve urgent review where relevant | sarcoidosis closure |

---

## 8. Granuloma / Pathology Reasoning Rules

| Rule ID | Rule | Required Behavior |
|---|---|---|
| SARC_PATH_001 | Granulomatous inflammation is not sarcoidosis diagnosis | Show granulomatous differential prompt |
| SARC_PATH_002 | Nonnecrotizing granulomas support sarcoid-like reasoning but are not specific enough alone | Preserve alternative causes |
| SARC_PATH_003 | Histopathology alone cannot distinguish sarcoidosis from all granulomatous diseases | Require clinical / microbiologic / exposure / occupational integration |
| SARC_PATH_004 | Necrosis, organisms, dirty necrosis, palisading granulomas, strong inflammatory infiltrate, or alternative pathology features should weaken sarcoidosis closure | Show alternative prompt |
| SARC_PATH_005 | Microorganism stains/cultures context must remain visible where relevant | Do not exclude infection |
| SARC_PATH_006 | Berylliosis and HP may share granulomatous features | Preserve exposure and HP prompts |
| SARC_PATH_007 | Pathology must be integrated with clinical and radiologic context | Preserve MDD prompt |
| SARC_PATH_008 | Missing pathology does not exclude sarcoidosis | Show missing evidence |
| SARC_PATH_009 | Pathology context does not decide sampling | Block biopsy/sampling authority |

Blocked output:

- “Nonnecrotizing granulomas confirm sarcoidosis.”
- “Granulomas confirm sarcoidosis.”
- “Histology rules out infection.”
- “Berylliosis excluded.”
- “HP excluded.”
- “Tissue sampling should be performed.”
- “Sampling is unnecessary” without clinical context.

---

## 9. Alternative Granulomatous Cause Matrix

| Alternative Cause Family | Visibility Trigger | Required Platform Response | Dedicated Source Status |
|---|---|---|---|
| Tuberculosis | granulomatous disease, necrosis, exposure risk, endemic context, systemic symptoms, microbiology missing | Keep TB mimic visible | broader infection source needed for dedicated parity |
| Nontuberculous mycobacteria | granulomatous disease, airway disease, microbiology missing | Keep NTM mimic visible | broader infection source needed for dedicated parity |
| Fungal infection | granulomatous disease, geographic/exposure context, immunosuppression, microbiology missing | Keep fungal mimic visible | fungal source needed for dedicated parity |
| Other infection | fever, systemic symptoms, immunosuppression, inflammatory markers, microbiology missing | Keep infection visible | infection source needed |
| Malignancy / lymphoma | lymphadenopathy, systemic symptoms, atypical progression, sarcoid-like reaction concern | Keep malignancy mimic visible | oncology source deferred |
| Berylliosis / chronic beryllium disease | occupational/environmental beryllium exposure context missing or suggestive | Keep berylliosis visible | beryllium source needed |
| Pneumoconiosis / occupational granulomatous disease | occupational dust exposure, upper-lung fibrosis, nodules, exposure gap | Keep occupational mimic visible | occupational source needed |
| Hypersensitivity pneumonitis | exposure history, small-airway features, poorly formed granulomas, bronchiolocentric context | Keep HP visible | HP source available |
| Drug-induced granulomatous disease | medication or therapy history missing/suggestive | Keep drug reaction visible | drug-induced source needed |
| Immune disorder / CVID-like granulomatous-lymphocytic ILD | immune deficiency context, lymphoid hyperplasia, recurrent infection context | Keep immune disorder visible | source needed |
| Foreign body / aspiration | aspirated particles, dependent distribution, aspiration risk | Keep aspiration/foreign body visible | aspiration source needed |

Required rule:

> Alternative granulomatous causes must remain visible until reviewed; the platform cannot exclude them.

---

## 10. Sampling and Follow-Up Boundary Rules

| Rule ID | Rule | Required Behavior |
|---|---|---|
| SARC_SAMPLE_001 | Tissue or lymph node sampling may be discussed in source context, but platform cannot decide it | Show sampling uncertainty only |
| SARC_SAMPLE_002 | High clinical suspicion presentations may reduce need for sampling in guideline context | Do not convert into platform no-sampling decision |
| SARC_SAMPLE_003 | Asymptomatic bilateral hilar lymphadenopathy has no universal sampling rule | Preserve case-by-case uncertainty |
| SARC_SAMPLE_004 | If sampling is not performed in certain contexts, close follow-up may be relevant | Show follow-up prompt without schedule |
| SARC_SAMPLE_005 | Sampling route or procedure selection is outside platform authority | Block procedure recommendation |
| SARC_SAMPLE_006 | Regional prevalence of infection/malignancy and patient-specific risk can affect decision-making | Preserve clinical context prompt |
| SARC_SAMPLE_007 | Patient preference and procedural risk remain outside platform automation | Block automated sampling logic |

Blocked output:

- “Biopsy should be performed.”
- “Lymph node sampling should be performed.”
- “Lymph node sampling is unnecessary.”
- “Follow-up every X months.”
- “EBUS should be performed.”
- “No follow-up needed.”

---

## 11. Sarcoidosis / ILD Overlap Rules

| Overlap | Required Behavior |
|---|---|
| Sarcoidosis vs infection | Preserve TB/NTM/fungal/other infection mimics |
| Sarcoidosis vs HP | Preserve exposure, small-airway, HP granuloma context |
| Sarcoidosis vs pneumoconiosis / berylliosis | Preserve occupational/environmental exposure prompt |
| Sarcoidosis vs malignancy | Preserve malignancy / lymphoma / sarcoid-like reaction prompt |
| Sarcoidosis vs drug reaction | Preserve medication / therapy context |
| Sarcoidosis vs CTD-ILD | Preserve autoimmune context and granulomatous differential |
| Sarcoidosis vs NSIP/OP | Preserve NSIP/OP pattern prompts and secondary causes |
| Sarcoidosis vs UIP/IPF | Preserve UIP/IPF boundary; perilymphatic or upper-lung clue may challenge closure |
| Sarcoidosis vs acute overlay | Preserve infection/urgent review where relevant |
| Sarcoidosis vs unclassifiable ILD | Preserve discordance and MDD prompt |

Rule:

> Sarcoid-like prompts must not erase competing granulomatous, infectious, occupational, autoimmune, or fibrotic ILD families.

---

## 12. Missing Evidence Matrix

| Missing Evidence | Required Prompt |
|---|---|
| Clinical presentation incomplete | compatible presentation not established |
| Extrapulmonary review missing | systemic sarcoid context incomplete |
| Lymph node distribution context missing | thoracic pattern incomplete |
| HRCT pattern incomplete | perilymphatic / nodular / fibrotic distribution uncertain |
| Pathology unavailable | granuloma context missing |
| Pathology not integrated | histology not integrated with clinical/radiologic context |
| Microbiology unavailable | infectious granulomatous mimics not excluded |
| TB/NTM/fungal context missing | infection mimic visible |
| Occupational/beryllium exposure history missing | berylliosis / occupational mimic visible |
| Medication history missing | drug-induced granulomatous disease visible |
| Malignancy context missing | lymphoma / sarcoid-like reaction visible |
| HP exposure/small-airway context missing | HP mimic visible |
| Autoimmune context missing | CTD-ILD / immune disorder context visible |
| Prior imaging missing | progression/stability uncertain |
| Follow-up context missing | temporal behavior uncertain |
| MDD unavailable | integrated diagnosis not established |
| Urgent clinical status missing | acute danger incompletely assessed |

Required rule:

> Missing evidence must remain visible and must not be converted into exclusion.

---

## 13. MDD and Review Rules

| Rule ID | Rule | Required Behavior |
|---|---|---|
| SARC_MDD_001 | Sarcoidosis-like reasoning requires integration of clinical, radiologic, pathology, microbiology, and alternative-cause review | Preserve MDD/review prompt |
| SARC_MDD_002 | Granulomatous differential requires alternative cause visibility | Do not force sarcoidosis label |
| SARC_MDD_003 | Atypical presentation triggers elevated review prompt | Keep mimics visible |
| SARC_MDD_004 | Missing pathology or microbiology limits confidence | Show evidence gap |
| SARC_MDD_005 | Sampling uncertainty remains clinician/MDD domain | Block sampling decision |
| SARC_MDD_006 | Working diagnosis remains provisional and reviewable | Preserve confidence/re-review |
| SARC_MDD_007 | Acute danger must not wait for sarcoidosis classification | Preserve urgent review prompt |

Blocked output:

- “Sarcoidosis confirmed.”
- “MDD unnecessary.”
- “Alternative causes excluded.”
- “Working diagnosis final.”
- “No follow-up needed.”
- “No urgent review needed” when acute danger exists.

---

## 14. Urgent Review / Acute Overlay Rules

Sarcoid-like reasoning may coexist with urgent or acute processes.

| Acute / Overlay Concern | Required Prompt |
|---|---|
| Fever / systemic illness | infection / inflammatory / malignancy mimic visible |
| Acute dyspnea / hypoxemia | urgent review prompt visible |
| Hemoptysis or anemia | hemorrhage / infection / malignancy prompt visible |
| Immunosuppression | infection mimic visible |
| New consolidation or GGO | infection, OP, drug reaction, acute overlay visible |
| Rapid lymph node enlargement | malignancy / infection prompt visible |
| Cardiac symptoms or syncope | urgent review prompt visible |
| Neurologic symptoms | urgent review prompt visible |
| Hypercalcemia symptoms | urgent review / systemic review visible |
| Pulmonary hypertension concern | review prompt visible |

Rule:

> Sarcoid-like pattern must not hide urgent clinical danger.

---

## 15. Source Scope Limits

The ATS sarcoidosis guideline can support:

- sarcoidosis diagnostic uncertainty,
- three-criterion diagnostic framing,
- alternative cause exclusion prompt,
- granulomatous mimic visibility,
- sampling uncertainty,
- follow-up prompt where relevant.

It cannot by itself support full dedicated parity for:

- tuberculosis,
- nontuberculous mycobacterial disease,
- fungal infection,
- berylliosis,
- occupational granulomatous disease,
- malignancy,
- drug-induced granulomatous disease,
- immune deficiency-related granulomatous disease.

Those domains require dedicated source mapping before domain-specific parity.

Source rule:

> A mimic listed in the sarcoidosis guideline may remain visible, but dedicated mimic parity requires its own source.

---

## 16. Priority Order

When sarcoidosis / granulomatous differential reasoning is active, visibility priority is:

1. urgent clinical danger,
2. acute infection / malignancy / vascular / systemic danger prompts,
3. infection mimic visibility,
4. alternative granulomatous cause visibility,
5. occupational / beryllium / exposure prompt,
6. HP / CTD-ILD / drug / immune disorder competing prompts,
7. missing evidence,
8. source-needed or mapping-limited status,
9. MDD / integrated review prompt,
10. sampling uncertainty,
11. temporal comparison / follow-up prompt,
12. sarcoid-like pattern-family description,
13. working diagnosis caveat.

Sarcoidosis naming must not outrank safety, mimic exclusion, source status, or MDD need.

---

## 17. Allowed Language

Allowed output posture:

- “Sarcoid-like granulomatous differential prompt is visible.”
- “Compatible presentation context is incomplete.”
- “Nonnecrotizing granulomatous inflammation supports sarcoid-like reasoning but does not diagnose sarcoidosis.”
- “Alternative granulomatous causes remain visible.”
- “Infection, berylliosis, HP, malignancy, drug reaction, and immune disorder mimics are not excluded by this platform.”
- “Histopathology must be integrated with clinical and radiologic context.”
- “Sampling decision remains outside platform authority.”
- “Close follow-up may be relevant in source context, but no schedule is set by the platform.”
- “MDD prompt remains visible.”
- “Final diagnosis is not established by this platform.”
- “diagnostic_authority: none”
- “treatment_authority: none”
- “public_ready: false”
- “clinically_reviewed: false”

---

## 18. Blocked Language

Blocked output posture:

- “Sarcoidosis diagnosed.”
- “Pulmonary sarcoidosis confirmed.”
- “Nonnecrotizing granulomas confirm sarcoidosis.”
- “Alternative causes excluded.”
- “TB excluded.”
- “NTM excluded.”
- “Fungal infection excluded.”
- “Berylliosis excluded.”
- “Malignancy excluded.”
- “HP excluded.”
- “Drug reaction excluded.”
- “Biopsy should be performed.”
- “Lymph node sampling should be performed.”
- “Sampling is unnecessary.”
- “Follow-up every X months.”
- “Treatment should be started.”
- “MDD unnecessary.”
- “Public-ready.”
- “Clinically reviewed.”

---

## 19. Testable Sarcoidosis / Granulomatous Expectations

Future test cases should evaluate:

| Expectation ID | Expectation |
|---|---|
| SARC_001 | Sarcoid-like prompt is visible without sarcoidosis diagnosis |
| SARC_002 | Compatible presentation is represented as prompt, not diagnosis |
| SARC_003 | Nonnecrotizing granulomatous inflammation is supportive but not diagnostic alone |
| SARC_004 | Alternative granulomatous causes remain visible |
| SARC_005 | Infection mimics remain visible |
| SARC_006 | Berylliosis / occupational mimic remains visible where relevant |
| SARC_007 | HP mimic remains visible |
| SARC_008 | Malignancy / lymphoma / sarcoid-like reaction remains visible |
| SARC_009 | Drug-induced granulomatous disease remains visible where relevant |
| SARC_010 | Histopathology alone does not settle diagnosis |
| SARC_011 | Missing microbiology is listed |
| SARC_012 | Missing occupational/exposure history is listed |
| SARC_013 | Sampling uncertainty is preserved |
| SARC_014 | Follow-up prompt does not become schedule |
| SARC_015 | MDD prompt remains visible |
| SARC_016 | Urgent review prompt remains visible where relevant |
| SARC_017 | Source-needed mimic domains are not over-expanded |
| SARC_018 | Diagnostic authority remains none |
| SARC_019 | Treatment authority remains none |
| SARC_020 | Public readiness remains false |
| SARC_021 | Clinically reviewed remains false |

---

## 20. Example Reasoning Scenarios

### 20.1 Bilateral Hilar Lymphadenopathy Without Tissue

Input reasoning context:

- bilateral hilar lymphadenopathy,
- no tissue sampling,
- no microbiology data,
- no systemic symptom review documented,
- follow-up context unknown.

Allowed platform output:

- “Sarcoid-like prompt is visible.”
- “Granuloma/pathology context is missing.”
- “Infection and malignancy mimics remain visible.”
- “Sampling decision remains outside platform authority.”
- “Close follow-up context may be relevant, but no schedule is set.”
- “Final diagnosis is not established by this platform.”

Blocked output:

- “Sarcoidosis confirmed.”
- “Lymph node sampling unnecessary.”
- “Infection excluded.”
- “Malignancy excluded.”
- “Follow-up every X months.”

---

### 20.2 Nonnecrotizing Granulomas With Incomplete Microbiology

Input reasoning context:

- nonnecrotizing granulomatous inflammation reported,
- microbiology incomplete,
- occupational exposure history missing,
- medication history missing.

Allowed platform output:

- “Nonnecrotizing granulomatous inflammation supports sarcoid-like reasoning.”
- “This does not diagnose sarcoidosis.”
- “Infection, berylliosis/occupational exposure, and drug reaction remain visible.”
- “Microbiology, occupational exposure, and medication contexts are incomplete.”
- “MDD prompt remains visible.”

Blocked output:

- “Sarcoidosis diagnosed.”
- “TB excluded.”
- “Berylliosis excluded.”
- “Drug reaction excluded.”
- “No MDD needed.”

---

### 20.3 Sarcoid-Like Pattern With HP Features

Input reasoning context:

- granulomatous inflammation,
- mosaic attenuation / air trapping,
- possible exposure,
- poorly formed granuloma concern,
- HP source features possible.

Allowed platform output:

- “Sarcoid-like and HP-like prompts both remain visible.”
- “Exposure and small-airway contexts support HP review.”
- “Granulomatous features require alternative cause review.”
- “Sarcoidosis and HP are not resolved by this platform.”
- “MDD prompt remains visible.”

Blocked output:

- “Sarcoidosis confirmed.”
- “HP excluded.”
- “Granulomas settle the diagnosis.”
- “Treatment should be started.”

---

### 20.4 Atypical Sarcoid-Like Fibrotic Disease

Input reasoning context:

- upper-lung/perihilar fibrosis,
- lymphadenopathy,
- systemic symptoms,
- infection data missing,
- malignancy context missing,
- prior imaging unavailable.

Allowed platform output:

- “Sarcoid-like fibrotic differential prompt is visible.”
- “Atypical or systemic features elevate alternative-cause visibility.”
- “Infection and malignancy contexts are incomplete.”
- “Prior imaging is unavailable, limiting temporal assessment.”
- “Urgent review prompt remains visible where clinically relevant.”

Blocked output:

- “Sarcoidosis confirmed.”
- “Infection excluded.”
- “Malignancy excluded.”
- “No urgent review concern.”

---

### 20.5 Possible Löfgren-Type Presentation

Input reasoning context:

- high-suspicion clinical syndrome reported,
- no tissue sampling,
- alternative cause review incomplete,
- follow-up context not documented.

Allowed platform output:

- “High-suspicion sarcoid-like presentation prompt is visible.”
- “Source context may support non-sampling in selected clinical circumstances, but the platform does not decide sampling.”
- “Alternative cause review and follow-up context remain visible.”
- “Final diagnosis is not established by this platform.”

Blocked output:

- “Sarcoidosis diagnosed.”
- “Sampling should not be performed.”
- “Alternative causes excluded.”
- “Follow-up unnecessary.”

---

## 21. Failure Modes

The following are explicit v0.7.7 failures:

| Failure Mode | Why It Fails |
|---|---|
| Sarcoid-like prompt becomes sarcoidosis diagnosis | Violates diagnostic_authority none |
| Nonnecrotizing granuloma becomes diagnostic alone | Overclaims pathology |
| Histopathology excludes all alternatives | Contradicts granulomatous differential principle |
| Infection mimics hidden | Weakens safety and source governance |
| Berylliosis / occupational mimic hidden | Hides exposure-based differential |
| HP mimic hidden | Violates v0.7.4 overlap logic |
| Malignancy mimic hidden | Weakens alternative-cause visibility |
| Drug reaction hidden | Hides medication-related mimic |
| Tissue sampling decision appears | Creates clinical authority |
| Follow-up schedule appears | Creates management authority |
| Missing microbiology hidden | Creates false exclusion |
| Missing exposure/occupational history hidden | Creates false confidence |
| MDD omitted in granulomatous uncertainty | Weakens review governance |
| Urgent review omitted in acute/systemic danger | Weakens safety visibility |
| Treatment recommendation appears | Violates treatment_authority none |
| Public-ready claim appears | Violates public_ready false |
| Clinically reviewed claim appears | Violates clinically_reviewed false |

---

## 22. Acceptance Criteria

v0.7.7 is accepted only if:

- sarcoid-like prompt remains a prompt, not diagnosis,
- compatible presentation is represented without diagnostic closure,
- granuloma context is represented without diagnostic closure,
- nonnecrotizing granulomas are not treated as diagnostic alone,
- alternative granulomatous causes remain visible,
- infection mimics remain visible,
- berylliosis / occupational mimic remains visible where relevant,
- HP mimic remains visible,
- malignancy mimic remains visible,
- drug reaction mimic remains visible,
- source-needed domains are not over-expanded,
- sampling uncertainty remains visible,
- no tissue or lymph node sampling decision is made,
- follow-up prompt does not become schedule,
- MDD prompt remains visible,
- urgent review prompt remains visible where relevant,
- diagnostic_authority remains none,
- treatment_authority remains none,
- public_ready remains false,
- clinically_reviewed remains false.

---

## 23. Next Step

The next recommended step is:

- v0.7.8 — Non-UIP Differential Test Case Pack

v0.7.8 should create test cases for:

- fibrotic HP visibility without HP diagnosis,
- CTD-ILD/SARD-ILD context prompt without diagnosis,
- NSIP-like prompt with secondary-cause visibility,
- OP-like prompt with infection/aspiration/drug/CTD visibility,
- unclassifiable / mixed-pattern uncertainty,
- sarcoid-like granulomatous prompt with alternative cause visibility,
- source-needed deferred domains,
- MDD visibility,
- urgent review visibility,
- diagnostic_authority: none,
- treatment_authority: none,
- public_ready: false,
- clinically_reviewed: false.

---

## 24. Governance Statement

Sarcoidosis / Granulomatous Differential Prompt Parity protects the platform from both sarcoid-like erasure and sarcoidosis overdiagnosis.

It does not diagnose.  
It does not treat.  
It does not decide biopsy.  
It does not decide lymph node sampling.  
It does not confirm sarcoidosis.  
It does not confirm pulmonary sarcoidosis.  
It does not exclude infection.  
It does not exclude berylliosis.  
It does not exclude HP.  
It does not exclude malignancy.  
It does not exclude drug reaction.  
It does not replace microbiology.  
It does not replace pathology.  
It does not replace MDD.  
It does not claim public readiness.  
It does not claim clinical review.

The platform remains an evidence-governed clinical reasoning platform.

The v0.7 rule remains:

> “Differential reasoning is not differential diagnosis authority.”

For sarcoidosis / granulomatous differential reasoning:

> “Read compatible presentation, granuloma context, alternative causes, infection risk, exposure history, source limits, and review need before naming sarcoidosis.”