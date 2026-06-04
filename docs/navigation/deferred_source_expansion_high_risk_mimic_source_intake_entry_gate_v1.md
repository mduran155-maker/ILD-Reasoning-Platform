# ILD Reasoning Platform — Deferred Source Expansion / High-Risk Mimic Source Intake Entry Gate v1

Version: v0.8.0  
Status: source_intake_entry_gate  
Scope: Deferred high-risk mimic source intake and source role mapping  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This document opens v0.8 — Deferred Source Expansion / High-Risk Mimic Source Intake.

v0.8 begins with source intake, not domain parity.

This document does not diagnose occupational ILD.  
This document does not diagnose pneumoconiosis.  
This document does not diagnose asbestosis.  
This document does not diagnose chronic beryllium disease.  
This document does not diagnose tuberculosis.  
This document does not diagnose nontuberculous mycobacterial disease.  
This document does not diagnose fungal infection.  
This document does not diagnose aspiration-related lung disease.  
This document does not diagnose drug-induced ILD.  
This document does not diagnose radiation pneumonitis.  
This document does not diagnose checkpoint inhibitor pneumonitis.  
This document does not diagnose pulmonary lymphangitic carcinomatosis.  
This document does not diagnose lymphoma.  
This document does not diagnose malignancy.  
This document does not diagnose sarcoidosis-like reaction.  
This document does not recommend treatment.  
This document does not decide biopsy, bronchoscopy, BAL, HRCT, PET/CT, microbiology, serology, occupational testing, drug discontinuation, radiation planning, immunotherapy management, or follow-up interval.  
This document does not create public readiness.  
This document does not make v0.8 clinically reviewed.

Its purpose is to create a governed entry gate for sources that may later support high-risk mimic visibility.

The v0.8 rule is:

> “Source intake precedes source claims. Source claims precede domain parity.”

The platform principle remains:

> “It teaches clinicians to read change before naming disease.”

---

## 2. Relationship to Prior Seals

v0.8 inherits:

- v0.3 Superimposed Events Core,
- v0.4 Evidence Layer / Source Review Governance,
- v0.5 Test Case Coverage Expansion,
- v0.6 UIP Parity Upgrade,
- v0.6.R1/R2/R3 source debt correction,
- v0.7 Non-UIP Fibrotic ILD Differential Reasoning Structural Seal,
- checkpoint-v0.7 project status / roadmap discipline.

v0.8 must not weaken any prior seal.

v0.8 must preserve:

- diagnostic_authority: none,
- treatment_authority: none,
- public_ready: false,
- clinically_reviewed: false,
- uncertainty preserved,
- missing pieces visible,
- mimics visible,
- MDD prompts visible where relevant,
- urgent review prompts visible where relevant.

---

## 3. Entry Gate Scope

v0.8 source intake may cover the following deferred high-risk mimic families.

| Mimic Family | v0.8 Source Intake Status | Domain Parity Status |
|---|---|---|
| Occupational ILD / pneumoconiosis / asbestosis | allowed_for_source_intake | not_opened |
| Chronic beryllium disease / beryllium sensitivity | allowed_for_source_intake | not_opened |
| Tuberculosis mimic | allowed_for_source_intake | not_opened |
| Nontuberculous mycobacterial disease mimic | allowed_for_source_intake | not_opened |
| Fungal mimic / histoplasmosis / aspergillosis / coccidioidomycosis | allowed_for_source_intake | not_opened |
| Aspiration-related lung disease | allowed_for_source_intake | not_opened |
| Drug-induced / therapy-related ILD | allowed_for_source_intake | not_opened |
| Radiation-induced lung injury / radiation pneumonitis | allowed_for_source_intake | not_opened |
| Checkpoint inhibitor pneumonitis | allowed_for_source_intake | not_opened |
| Pulmonary lymphangitic carcinomatosis | allowed_for_source_intake | not_opened |
| Malignancy / lymphoma / sarcoid-like reaction | allowed_for_source_intake | not_opened |
| Sarcoidosis-like reaction after cancer therapy | allowed_for_source_intake | not_opened |

Entry gate rule:

> v0.8.0 may admit sources into the roadmap, but it may not convert any source into domain parity.

---

## 4. Authority Constraints

The following constraints are mandatory across v0.8.

| Constraint | Required State |
|---|---|
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| clinically_reviewed | false |
| automated_occupational_ILD_diagnosis | not_allowed |
| automated_berylliosis_diagnosis | not_allowed |
| automated_TB_diagnosis | not_allowed |
| automated_NTM_diagnosis | not_allowed |
| automated_fungal_infection_diagnosis | not_allowed |
| automated_aspiration_diagnosis | not_allowed |
| automated_drug_induced_ILD_diagnosis | not_allowed |
| automated_radiation_pneumonitis_diagnosis | not_allowed |
| automated_checkpoint_inhibitor_pneumonitis_diagnosis | not_allowed |
| automated_PLC_diagnosis | not_allowed |
| automated_malignancy_diagnosis | not_allowed |
| automated_lymphoma_diagnosis | not_allowed |
| automated_sarcoid_like_reaction_diagnosis | not_allowed |
| automated_treatment_selection | not_allowed |
| automated_drug_discontinuation | not_allowed |
| automated_immunotherapy_hold_or_restart | not_allowed |
| automated_radiotherapy_plan_change | not_allowed |
| automated_biopsy_decision | not_allowed |
| automated_bronchoscopy_decision | not_allowed |
| automated_BAL_decision | not_allowed |
| automated_microbiology_order | not_allowed |
| automated_PET_CT_order | not_allowed |
| automated_follow_up_schedule | not_allowed |
| patient_facing_use | not_allowed |
| replacement_of_MDD | not_allowed |
| replacement_of_clinician | not_allowed |
| replacement_of_radiologist | not_allowed |
| replacement_of_pathologist | not_allowed |
| replacement_of_pulmonologist | not_allowed |
| replacement_of_rheumatologist | not_allowed |
| replacement_of_microbiology | not_allowed |
| replacement_of_occupational_medicine_review | not_allowed |
| replacement_of_oncology_review | not_allowed |
| replacement_of_radiation_oncology_review | not_allowed |
| replacement_of_urgent_review | not_allowed |

No source admitted in v0.8 may override these constraints.

---

## 5. Source Role Classes

Every v0.8 source must be assigned one role class.

| Role Class | Meaning | Allowed Use | Blocked Use |
|---|---|---|---|
| primary_high_authority | guideline / official statement / major society source directly relevant to a mimic family | source anchor; claim mapping candidate | diagnosis or treatment authority |
| primary_limited_scope | guideline or society source with narrow scope or treatment-heavy content | source anchor with restricted use | broad domain expansion |
| auxiliary_review | review, seminar, meta-analysis, or expert review | context support; risk visibility; limitation visibility | primary authority replacement |
| diagnostic_performance_study | study evaluating imaging/lab/pathology performance | feature visibility; test limitation visibility | automated test interpretation |
| case_example_cautionary | case report or case series illustrating mimic failure | test case inspiration; cautionary example | generalized rule or parity seal |
| internal_governance | platform governance document | inheritance and constraint enforcement | clinical claim source |

Source role rule:

> A source’s role determines how far it can be used.

---

## 6. v0.8 Source Intake Candidate Map

The following uploaded/source candidates are admitted for v0.8 source intake review.

| Source ID | Source Area | Proposed Role Class | Proposed Use | Domain Parity Allowed Now |
|---|---|---|---|---|
| V08_SRC_OCCUPATIONAL_ILD_ACOEM_NYS | Occupational ILD / pneumoconiosis / asbestosis | primary_high_authority | occupational exposure mimic prompt and source mapping | no |
| V08_SRC_ATS_BERYLLIUM_2014 | Beryllium sensitivity / chronic beryllium disease | primary_high_authority | berylliosis / sarcoid mimic source mapping | no |
| V08_SRC_ATS_CDC_IDSA_TB_DIAGNOSIS_2016 | Tuberculosis diagnosis | primary_high_authority | TB mimic visibility and microbiology evidence gap mapping | no |
| V08_SRC_ATS_IDSA_NTM_2007 | NTM pulmonary disease | primary_high_authority | NTM mimic visibility and microbiologic criteria boundary | no |
| V08_SRC_IDSA_ASPERGILLOSIS_2016 | Aspergillosis | primary_limited_scope | fungal mimic visibility; immunocompromised context | no |
| V08_SRC_IDSA_HISTOPLASMOSIS_2025 | Histoplasmosis | primary_limited_scope | endemic fungal mimic visibility; treatment-heavy source restriction | no |
| V08_SRC_BTS_ASPIRATION_2023 | Aspiration pneumonia / aspiration-related lung disease | primary_limited_scope | aspiration mimic and dependent injury prompt | no |
| V08_SRC_DRUG_INDUCED_ILD_REVIEWS | Drug-induced / therapy-related ILD | auxiliary_review | medication/therapy mimic visibility; low-authority caution | no |
| V08_SRC_ESTRO_RADIATION_PNEUMONITIS_2025 | Radiation pneumonitis | primary_limited_scope | radiation pneumonitis mimic/risk context; diagnosis-of-exclusion framing | no |
| V08_SRC_CHEST_RILI_2019 | Radiation-induced lung injury | auxiliary_review | temporal radiation injury context; RP/RPF distinction | no |
| V08_SRC_PREEXISTING_ILD_RP_CIP_META_2025 | Pre-existing ILD risk for RP/CIP | auxiliary_review | risk context and cautionary oncology overlap | no |
| V08_SRC_PLC_HRCT_PET_DIAGNOSTIC_PERFORMANCE_2020 | Pulmonary lymphangitic carcinomatosis | diagnostic_performance_study | malignancy mimic / septal and peribronchovascular pattern visibility | no |
| V08_SRC_PLC_MIMICKING_ILD_CASE_2025 | Pulmonary lymphangitic carcinomatosis mimic case | case_example_cautionary | test case cautionary example | no |
| V08_SRC_SARCOID_LIKE_REACTION_NEOPLASTIC_PATIENTS | Sarcoid-like reaction in neoplastic patients | auxiliary_review_or_case_series | malignancy vs benign granulomatous lymphadenopathy visibility | no |
| V08_SRC_SARCOIDOSIS_AFTER_LYMPHOMA_2014 | Sarcoidosis after lymphoma | auxiliary_review_or_case_series | lymphoma relapse mimic / histologic confirmation prompt | no |
| V08_SRC_SARCOIDOSIS_LYMPHOMA_REVIEW_2025 | Sarcoidosis-lymphoma relationship | auxiliary_review | lymphoma mimic and chronic inflammation context | no |
| V08_SRC_ICI_SARCOID_LIKE_REACTION_2026 | ICI-associated sarcoidosis-like reaction | auxiliary_review | immunotherapy-related sarcoid-like mimic visibility | no |
| V08_SRC_COCCIDIOIDOMYCOSIS_SARCOID_MIMIC_CASE | Coccidioidomycosis sarcoid mimic | case_example_cautionary | fungal mimic cautionary test case | no |
| V08_SRC_HISTOPLASMOSIS_SARCOIDOSIS_CASE_REVIEW | Histoplasmosis vs sarcoidosis | case_example_cautionary | endemic fungal mimic cautionary test case | no |

Important note:

- Some v0.8 sources are recent or treatment-heavy.
- Their presence does not create treatment authority.
- Their presence does not create clinical review.
- Their presence does not create public readiness.

---

## 7. High-Risk Mimic Intake Rationale

v0.8 is needed because v0.7 deliberately left several high-risk mimics as source-needed.

These mimics matter because they can imitate ILD patterns, sarcoidosis, OP-like consolidation, acute exacerbation-like change, or chronic fibrosis.

The platform must keep these mimics visible without diagnosing them.

v0.8 intake focuses on:

- sources,
- source scope,
- source authority,
- claim eligibility,
- source debt,
- missing evidence prompts,
- mimic visibility,
- urgent review visibility,
- MDD visibility.

It does not focus on:

- diagnostic rules,
- treatment algorithms,
- management pathways,
- public deployment,
- clinical validation.

---

## 8. Source Intake Requirements

A source may enter v0.8 only if the following fields are recorded.

| Field | Required |
|---|---|
| source_id | yes |
| source_title | yes |
| source_year | yes |
| source_type | yes |
| role_class | yes |
| domain_family | yes |
| primary_or_auxiliary_role | yes |
| treatment_heavy | yes/no |
| diagnostic_claim_eligible | yes/no/limited |
| mimic_visibility_eligible | yes/no |
| missing_evidence_prompt_eligible | yes/no |
| urgent_review_prompt_eligible | yes/no |
| MDD_prompt_eligible | yes/no |
| source_limitations | yes |
| domain_parity_allowed_now | always no at v0.8.0 |
| public_ready_supported | always false |
| clinically_reviewed_supported | always false |
| diagnostic_authority_supported | always none |
| treatment_authority_supported | always none |

---

## 9. Claim Eligibility Rules

v0.8.0 admits sources but does not yet approve claims.

Potential claim types are classified as follows.

| Claim Type | v0.8.0 Status |
|---|---|
| Source exists | allowed |
| Source role assigned | allowed |
| Source scope described | allowed |
| Source limitation visible | allowed |
| Mimic family remains visible | allowed |
| Missing evidence prompt possible | allowed |
| MDD prompt possible | allowed |
| Urgent review prompt possible | allowed |
| Diagnostic criteria implemented | not_allowed |
| Treatment recommendation implemented | not_allowed |
| Biopsy/BAL/order decision implemented | not_allowed |
| Follow-up interval implemented | not_allowed |
| Domain parity sealed | not_allowed |
| Public readiness supported | not_allowed |
| Clinically reviewed status supported | not_allowed |

---

## 10. Source Family Boundaries

### 10.1 Occupational ILD / Pneumoconiosis / Asbestosis

Allowed in v0.8.0:

- source intake,
- occupational exposure prompt eligibility,
- pneumoconiosis/asbestosis mimic visibility,
- missing occupational history prompt,
- source mapping candidate.

Blocked in v0.8.0:

- occupational ILD diagnosis,
- asbestosis diagnosis,
- pneumoconiosis diagnosis,
- compensation/medicolegal claim,
- exposure causation decision,
- treatment or surveillance plan.

---

### 10.2 Chronic Beryllium Disease / Beryllium Sensitivity

Allowed in v0.8.0:

- beryllium source intake,
- BeS/CBD distinction source mapping candidate,
- sarcoidosis mimic visibility,
- occupational/environmental beryllium exposure prompt.

Blocked in v0.8.0:

- beryllium sensitivity diagnosis,
- chronic beryllium disease diagnosis,
- BeLPT interpretation authority,
- occupational causation decision,
- treatment plan.

---

### 10.3 TB / NTM / Fungal Mimics

Allowed in v0.8.0:

- infection mimic source intake,
- microbiology missing-evidence prompts,
- endemic / exposure / immunosuppression context prompts,
- granulomatous infection mimic visibility,
- urgent review prompt eligibility.

Blocked in v0.8.0:

- TB diagnosis,
- NTM diagnosis,
- fungal infection diagnosis,
- infection exclusion,
- microbiology test ordering,
- antimicrobial or antifungal treatment recommendation,
- isolation or public health instruction.

---

### 10.4 Aspiration-Related Lung Disease

Allowed in v0.8.0:

- aspiration source intake,
- aspiration risk prompt eligibility,
- dependent injury / OP-like overlap prompt eligibility,
- infection/aspiration overlap visibility.

Blocked in v0.8.0:

- aspiration pneumonia diagnosis,
- aspiration-related ILD diagnosis,
- swallow study order,
- antibiotic recommendation,
- feeding or airway management instruction,
- follow-up schedule.

---

### 10.5 Drug-Induced / Therapy-Related ILD

Allowed in v0.8.0:

- medication/therapy source intake,
- drug temporal relationship prompt eligibility,
- alternative cause exclusion prompt visibility,
- oncology therapy mimic visibility,
- treatment-heavy source limitation.

Blocked in v0.8.0:

- drug-induced ILD diagnosis,
- causal attribution to a specific drug,
- drug discontinuation recommendation,
- steroid recommendation,
- rechallenge decision,
- oncologic treatment change.

---

### 10.6 Radiation Pneumonitis / Radiation-Induced Lung Injury

Allowed in v0.8.0:

- radiation pneumonitis source intake,
- temporal relationship prompt eligibility,
- radiation field / dose-context prompt eligibility,
- RP/RPF distinction as source-mapped future candidate,
- mimic visibility with infection, tumor progression, drug toxicity, edema, and ILD progression.

Blocked in v0.8.0:

- radiation pneumonitis diagnosis,
- radiation fibrosis diagnosis,
- steroid recommendation,
- radiation plan change,
- radiotherapy risk calculation,
- treatment decision.

---

### 10.7 Checkpoint Inhibitor Pneumonitis / ICI Sarcoid-Like Reaction

Allowed in v0.8.0:

- ICI therapy source intake,
- CIP risk context,
- sarcoid-like reaction mimic visibility,
- recurrence mimic prompt eligibility,
- imaging ambiguity visibility.

Blocked in v0.8.0:

- CIP diagnosis,
- ICI-associated SLR diagnosis,
- immunotherapy hold/restart decision,
- steroid recommendation,
- oncology treatment escalation or interruption.

---

### 10.8 Malignancy / Lymphoma / Pulmonary Lymphangitic Carcinomatosis

Allowed in v0.8.0:

- malignancy mimic source intake,
- PLC mimic visibility,
- septal/peribronchovascular pattern prompt eligibility,
- lymphoma relapse mimic visibility,
- sarcoid-like reaction vs recurrence prompt eligibility,
- tissue confirmation uncertainty prompt.

Blocked in v0.8.0:

- malignancy diagnosis,
- lymphoma diagnosis,
- pulmonary lymphangitic carcinomatosis diagnosis,
- recurrence diagnosis,
- PET/CT interpretation authority,
- biopsy decision,
- oncology management recommendation.

---

## 11. Missing Evidence Domains Opened for Source Intake

v0.8 may map source support for the following missing-evidence prompts.

| Missing Evidence | Mimic Families Protected |
|---|---|
| occupational exposure history | occupational ILD; berylliosis; pneumoconiosis; sarcoid mimic |
| beryllium exposure / BeLPT context | berylliosis; sarcoidosis mimic |
| microbiology data | TB; NTM; fungal infection; sarcoidosis mimic; OP-like consolidation |
| endemic fungal exposure/travel | histoplasmosis; coccidioidomycosis; fungal mimic |
| immunosuppression context | fungal infection; TB/NTM; ICI-related toxicity; opportunistic infection |
| aspiration risk | aspiration-related lung disease; OP-like consolidation; infection |
| medication / therapy history | drug-induced ILD; OP-like process; NSIP-like process; sarcoid-like reaction |
| radiation therapy history | radiation pneumonitis; radiation fibrosis; tumor recurrence mimic |
| radiation field / timing / dose context | RP/RPF distinction; treatment-related mimic |
| checkpoint inhibitor exposure | CIP; ICI-associated SLR; recurrence mimic |
| malignancy history | PLC; lymphoma; sarcoid-like reaction; infection risk |
| PET/CT ambiguity | sarcoid-like reaction; malignancy recurrence; lymphoma |
| tissue/pathology context | malignancy; sarcoid-like reaction; infection; berylliosis |
| prior imaging | temporal change; recurrence; therapy-related toxicity; infection |
| response/nonresponse to empiric therapy | infection; malignancy; drug/radiation/ICI toxicity |
| urgent clinical status | infection, hemorrhage, vascular, severe therapy toxicity, acute respiratory failure |

Required rule:

> Missing evidence must be made visible, not silently converted into exclusion.

---

## 12. Mimic Visibility Rules

v0.8 source intake must preserve the following mimic visibility rules.

| Rule ID | Rule |
|---|---|
| V08_MIMIC_001 | Infection may mimic ILD progression, OP-like consolidation, sarcoidosis, or therapy toxicity |
| V08_MIMIC_002 | Occupational exposure may mimic sarcoidosis, HP, UIP-like fibrosis, or nonspecific fibrosis |
| V08_MIMIC_003 | Berylliosis may mimic sarcoidosis and granulomatous ILD |
| V08_MIMIC_004 | Drug-induced ILD may mimic OP, NSIP, acute exacerbation, infection, or progression |
| V08_MIMIC_005 | Radiation pneumonitis may mimic infection, tumor progression, drug toxicity, or ILD worsening |
| V08_MIMIC_006 | Checkpoint inhibitor pneumonitis may mimic infection, radiation pneumonitis, ILD progression, or tumor progression |
| V08_MIMIC_007 | ICI-associated sarcoid-like reaction may mimic malignancy recurrence or sarcoidosis |
| V08_MIMIC_008 | Pulmonary lymphangitic carcinomatosis may mimic ILD, infection, edema, or sarcoid-like disease |
| V08_MIMIC_009 | Fungal granulomatous disease may mimic sarcoidosis |
| V08_MIMIC_010 | Sarcoid-like reactions in cancer patients may mimic recurrence or metastatic disease |
| V08_MIMIC_011 | Multiple mimics may coexist with chronic fibrotic ILD |
| V08_MIMIC_012 | Acute danger must outrank chronic pattern-family naming |

---

## 13. Source Debt Register Opened

The following source-debt register is opened for v0.8 tracking.

| Debt ID | Domain | Current Status | Next Required Action |
|---|---|---|---|
| V08_DEBT_OCC_001 | Occupational ILD / pneumoconiosis / asbestosis | source_candidate_present | role mapping and claim mapping |
| V08_DEBT_BERYL_001 | Chronic beryllium disease | source_candidate_present | role mapping and claim mapping |
| V08_DEBT_TB_001 | Tuberculosis mimic | source_candidate_present | role mapping and claim mapping |
| V08_DEBT_NTM_001 | NTM mimic | source_candidate_present | role mapping and claim mapping |
| V08_DEBT_FUNGAL_001 | Aspergillosis / fungal mimic | source_candidate_present_limited_scope | role mapping and claim mapping |
| V08_DEBT_HISTO_001 | Histoplasmosis / endemic fungal mimic | source_candidate_present_treatment_heavy | role mapping and claim mapping |
| V08_DEBT_COCCI_001 | Coccidioidomycosis mimic | case_example_present | lower-authority caution mapping |
| V08_DEBT_ASP_001 | Aspiration-related disease | source_candidate_present | role mapping and claim mapping |
| V08_DEBT_DILD_001 | Drug-induced ILD | review_sources_present | lower-authority claim mapping |
| V08_DEBT_RP_001 | Radiation pneumonitis / RILI | guideline_and_review_present | role mapping and claim mapping |
| V08_DEBT_CIP_001 | Checkpoint inhibitor pneumonitis | meta_analysis_present | role mapping and claim mapping |
| V08_DEBT_PLC_001 | Pulmonary lymphangitic carcinomatosis | diagnostic_performance_and_case_sources_present | role mapping and claim mapping |
| V08_DEBT_SLR_001 | Sarcoid-like reaction / malignancy mimic | review_and_case_series_present | role mapping and claim mapping |
| V08_DEBT_LYMPHOMA_001 | Lymphoma / sarcoidosis overlap | review_and_case_series_present | role mapping and claim mapping |

Debt register rule:

> A source candidate reduces source debt only after role mapping and claim-to-source mapping.

---

## 14. Treatment-Heavy Source Guard

Several v0.8 sources include treatment recommendations.

The platform must not import treatment recommendations.

Treatment-heavy sources may be used only for:

- source existence,
- diagnostic uncertainty,
- mimic visibility,
- clinical context,
- evidence gap visibility,
- urgent review visibility,
- MDD/review prompt visibility,
- source limitations.

Treatment-heavy sources may not be used for:

- treatment selection,
- drug initiation,
- drug discontinuation,
- steroid recommendation,
- antifungal recommendation,
- antimicrobial recommendation,
- immunotherapy hold/restart,
- radiotherapy modification,
- follow-up interval.

Treatment-heavy source rule:

> A treatment source may inform mimic visibility, but it does not create treatment authority.

---

## 15. Urgent Review Guard

v0.8 high-risk mimics include potentially urgent conditions.

Urgent review prompts must remain visible where relevant.

| Urgent Context | Required v0.8 Behavior |
|---|---|
| acute hypoxemia | urgent review prompt visible |
| rapid dyspnea progression | urgent review prompt visible |
| fever or systemic illness | infection mimic visible |
| hemoptysis or anemia | hemorrhage/malignancy/infection prompt visible |
| immunosuppression | opportunistic infection and therapy toxicity prompts visible |
| known malignancy with new septal thickening | PLC/recurrence mimic visible |
| new FDG-avid lymphadenopathy after cancer therapy | recurrence vs sarcoid-like reaction prompt visible |
| post-radiation new GGO/consolidation | RP vs infection vs recurrence vs drug toxicity prompt visible |
| ICI exposure with new pulmonary findings | CIP vs infection vs progression vs SLR prompt visible |
| nonresponse to empiric therapy | mimic re-review prompt visible |
| severe or worsening respiratory status | urgent clinical review visible |

Urgent review rule:

> v0.8 may show urgent review prompts, but it may not triage, diagnose, or treat.

---

## 16. MDD / Specialist Review Guard

v0.8 source intake must preserve review prompts.

| Review Domain | Required Visibility |
|---|---|
| pulmonology | visible where ILD/mimic uncertainty exists |
| radiology | visible where imaging pattern or temporal change is central |
| pathology | visible where tissue/granuloma/malignancy/infection distinction is relevant |
| microbiology | visible where TB/NTM/fungal/infectious mimic is possible |
| occupational medicine | visible where exposure or beryllium/pneumoconiosis/asbestosis is possible |
| rheumatology | visible where sarcoid/CTD/immune mimic overlap exists |
| oncology | visible where malignancy recurrence, PLC, therapy toxicity, or SLR is possible |
| radiation oncology | visible where RP/RILI/radiation field context is relevant |
| MDD | visible where cross-domain integration is required |
| urgent clinical review | visible where instability or danger exists |

Review rule:

> Source intake must not replace specialist review.

---

## 17. Allowed Language

Allowed v0.8.0 language:

- “Source candidate admitted for role mapping.”
- “Mimic family remains visible.”
- “Source scope is limited.”
- “Treatment-heavy source: treatment authority blocked.”
- “Diagnostic performance source: test interpretation authority blocked.”
- “Case example supports cautionary test design only.”
- “Missing microbiology remains visible.”
- “Occupational exposure history remains visible.”
- “Therapy-related mimic remains visible.”
- “Malignancy recurrence mimic remains visible.”
- “MDD prompt remains visible.”
- “Urgent review prompt remains visible where relevant.”
- “Domain parity is not opened.”
- “diagnostic_authority: none”
- “treatment_authority: none”
- “public_ready: false”
- “clinically_reviewed: false”

---

## 18. Blocked Language

Blocked v0.8.0 language:

- “Occupational ILD diagnosed.”
- “Berylliosis confirmed.”
- “TB excluded.”
- “NTM excluded.”
- “Fungal infection excluded.”
- “Aspiration pneumonia diagnosed.”
- “Drug-induced ILD confirmed.”
- “Radiation pneumonitis diagnosed.”
- “Checkpoint inhibitor pneumonitis confirmed.”
- “Pulmonary lymphangitic carcinomatosis diagnosed.”
- “Cancer recurrence diagnosed.”
- “Lymphoma relapse excluded.”
- “Sarcoid-like reaction confirmed.”
- “Order PET/CT.”
- “Perform biopsy.”
- “Perform bronchoscopy.”
- “Start antifungal treatment.”
- “Start steroids.”
- “Stop immunotherapy.”
- “Change radiation plan.”
- “Follow up every X months.”
- “Public-ready.”
- “Clinically reviewed.”

---

## 19. v0.8.0 Acceptance Criteria

v0.8.0 is accepted only if:

- v0.8 opens as source intake, not domain parity,
- all admitted sources receive provisional role classes,
- treatment-heavy sources are explicitly constrained,
- diagnostic performance sources do not create test interpretation authority,
- case reports are limited to cautionary examples,
- high-risk mimic families remain visible but non-diagnostic,
- source debt remains visible,
- missing evidence remains visible,
- MDD prompts remain visible where relevant,
- urgent review prompts remain visible where relevant,
- domain parity remains not opened,
- diagnostic_authority remains none,
- treatment_authority remains none,
- public_ready remains false,
- clinically_reviewed remains false.

---

## 20. Next Step

The next recommended step is:

- v0.8.1 — High-Risk Mimic Source Role Map

v0.8.1 should convert the v0.8 source intake list into a structured role map.

It should define:

- source_id,
- source title,
- year,
- domain family,
- source role class,
- source authority level,
- treatment-heavy status,
- diagnostic claim eligibility,
- mimic visibility eligibility,
- missing evidence eligibility,
- urgent review eligibility,
- MDD/review eligibility,
- blocked uses,
- source limitations.

v0.8.1 must not create domain parity.

---

## 21. Governance Statement

v0.8.0 opens the deferred high-risk mimic source intake gate.

It does not diagnose.  
It does not treat.  
It does not decide biopsy.  
It does not decide bronchoscopy.  
It does not decide BAL.  
It does not decide HRCT, PET/CT, microbiology, serology, occupational testing, or follow-up interval.  
It does not confirm infection.  
It does not exclude infection.  
It does not confirm malignancy.  
It does not exclude malignancy.  
It does not confirm therapy-related toxicity.  
It does not replace MDD.  
It does not claim public readiness.  
It does not claim clinical review.

The platform remains an evidence-governed clinical reasoning platform.

The current principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.8 rule is:

> “Source intake precedes source claims. Source claims precede domain parity.”