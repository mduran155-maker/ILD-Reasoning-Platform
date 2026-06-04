# ILD Reasoning Platform — High-Risk Mimic Source Role Map v1

Version: v0.8.1  
Status: source_role_map  
Scope: High-risk mimic source role classification after v0.8.0 source intake entry gate  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This document defines the source role map for v0.8 — Deferred Source Expansion / High-Risk Mimic Source Intake.

It follows:

- `docs/navigation/deferred_source_expansion_high_risk_mimic_source_intake_entry_gate_v1.md`
- `docs/navigation/non_uip_fibrotic_ild_differential_seal_v1.md`
- `docs/navigation/project_status_roadmap_checkpoint_v0_7.md`

This document does not create domain parity.

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

Its purpose is to classify v0.8 source candidates before claim-to-source mapping.

The v0.8 rule remains:

> “Source intake precedes source claims. Source claims precede domain parity.”

---

## 2. Relationship to Prior v0.8 Entry Gate

v0.8.0 opened the source intake gate.

v0.8.1 assigns role classes to admitted sources.

v0.8.1 may define:

- source role class,
- source authority level,
- domain family,
- treatment-heavy status,
- diagnostic-claim eligibility,
- mimic-visibility eligibility,
- missing-evidence eligibility,
- urgent-review eligibility,
- MDD/review eligibility,
- blocked uses,
- limitations.

v0.8.1 may not define:

- diagnostic rules,
- treatment rules,
- domain parity,
- test case lock,
- structural seal,
- public readiness,
- clinical review.

---

## 3. Global Authority Constraints

The following constraints remain mandatory across v0.8.1.

| Constraint | Required State |
|---|---|
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| clinically_reviewed | false |
| automated_diagnosis | not_allowed |
| automated_treatment_selection | not_allowed |
| automated_drug_discontinuation | not_allowed |
| automated_immunotherapy_hold_or_restart | not_allowed |
| automated_radiotherapy_plan_change | not_allowed |
| automated_biopsy_decision | not_allowed |
| automated_bronchoscopy_decision | not_allowed |
| automated_BAL_decision | not_allowed |
| automated_microbiology_order | not_allowed |
| automated_HRCT_order | not_allowed |
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

---

## 4. Source Role Class Definitions

| Role Class | Definition | Allowed Use | Blocked Use |
|---|---|---|---|
| primary_high_authority | Major guideline, official society statement, or formal diagnostic statement directly relevant to a mimic family | source anchor, future claim mapping, source-scope definition | diagnosis, treatment authority, public readiness |
| primary_limited_scope | Guideline or society source with narrow population, treatment-heavy focus, or limited diagnostic scope | restricted source anchor, future claim mapping with limitations | broad domain parity or treatment import |
| auxiliary_review | Review, seminar, meta-analysis, or expert review | context support, risk visibility, limitation visibility | replacement of primary authority |
| diagnostic_performance_study | Study evaluating imaging/lab/PET/CT/pathology performance | feature visibility, test limitation visibility | automated test interpretation |
| case_example_cautionary | Case report or case series illustrating mimic risk or diagnostic failure | cautionary examples and future test case inspiration | general rules or domain parity |
| internal_governance | Platform governance document | authority constraints, inheritance, source-debt discipline | clinical claim source |

---

## 5. Source Authority Level Definitions

| Authority Level | Meaning |
|---|---|
| high | Society guideline, official statement, or formal guideline-grade source |
| moderate | Major review, systematic review, meta-analysis, or diagnostic-performance study |
| limited | Case series, case report, narrative review, or treatment-heavy guideline used only for narrow context |
| internal | Platform governance only |

Authority rule:

> Authority level controls claim strength, but no authority level creates diagnostic or treatment authority.

---

## 6. v0.8 Source Role Map

| Source ID | Domain Family | Source Type | Role Class | Authority Level | Treatment-Heavy | Diagnostic Claim Eligibility | Mimic Visibility Eligibility | Missing Evidence Eligibility | Urgent Review Eligibility | MDD / Review Eligibility | Domain Parity Allowed Now |
|---|---|---|---|---|---|---|---|---|---|---|---|
| V08_SRC_OCCUPATIONAL_ILD_ACOEM_NYS | Occupational ILD / pneumoconiosis / asbestosis | occupational guideline / medical treatment guideline | primary_high_authority | high | partial | limited_future_mapping | yes | yes | yes | yes | no |
| V08_SRC_ATS_BERYLLIUM_2014 | Beryllium sensitivity / chronic beryllium disease | ATS official statement | primary_high_authority | high | partial | limited_future_mapping | yes | yes | yes | yes | no |
| V08_SRC_ATS_CDC_IDSA_TB_DIAGNOSIS_2016 | TB mimic | clinical practice diagnosis guideline | primary_high_authority | high | no_or_low | limited_future_mapping | yes | yes | yes | yes | no |
| V08_SRC_ATS_IDSA_NTM_2007 | NTM mimic | ATS/IDSA statement | primary_high_authority | high | partial | limited_future_mapping | yes | yes | yes | yes | no |
| V08_SRC_IDSA_ASPERGILLOSIS_2016 | Fungal / aspergillosis mimic | IDSA guideline | primary_limited_scope | high | yes | restricted_future_mapping | yes | yes | yes | yes | no |
| V08_SRC_IDSA_HISTOPLASMOSIS_2025 | Histoplasmosis / endemic fungal mimic | IDSA guideline update | primary_limited_scope | high | yes | restricted_future_mapping | yes | yes | yes | yes | no |
| V08_SRC_BTS_ASPIRATION_2023 | Aspiration-related lung disease | BTS clinical statement | primary_limited_scope | high | partial | restricted_future_mapping | yes | yes | yes | yes | no |
| V08_SRC_DRUG_INDUCED_ILD_REVIEWS | Drug-induced / therapy-related ILD | reviews / systematic review / expert viewpoint | auxiliary_review | moderate | yes | limited_or_low_authority | yes | yes | yes | yes | no |
| V08_SRC_ESTRO_RADIATION_PNEUMONITIS_2025 | Radiation pneumonitis | guideline / consensus-style source | primary_limited_scope | high | yes | restricted_future_mapping | yes | yes | yes | yes | no |
| V08_SRC_CHEST_RILI_2019 | Radiation-induced lung injury | review | auxiliary_review | moderate | yes | limited_future_mapping | yes | yes | yes | yes | no |
| V08_SRC_PREEXISTING_ILD_RP_CIP_META_2025 | Pre-existing ILD risk for RP/CIP | meta-analysis | auxiliary_review | moderate | no_or_low | risk_context_only | yes | yes | yes | yes | no |
| V08_SRC_PLC_HRCT_PET_DIAGNOSTIC_PERFORMANCE_2020 | Pulmonary lymphangitic carcinomatosis | diagnostic performance study | diagnostic_performance_study | moderate | no | feature_visibility_only | yes | yes | yes | yes | no |
| V08_SRC_PLC_MIMICKING_ILD_CASE_2025 | PLC mimicking ILD | case report | case_example_cautionary | limited | yes | no_general_claim | yes | yes | yes | yes | no |
| V08_SRC_SARCOID_LIKE_REACTION_NEOPLASTIC_PATIENTS | Sarcoid-like reaction in neoplastic patients | case series / correspondence | auxiliary_review | moderate_limited | no | limited_future_mapping | yes | yes | no_or_contextual | yes | no |
| V08_SRC_SARCOIDOSIS_AFTER_LYMPHOMA_2014 | Sarcoidosis after lymphoma | case series and literature review | auxiliary_review | moderate | partial | limited_future_mapping | yes | yes | yes | yes | no |
| V08_SRC_SARCOIDOSIS_LYMPHOMA_REVIEW_2025 | Sarcoidosis-lymphoma relationship | review | auxiliary_review | moderate | partial | context_only | yes | yes | yes | yes | no |
| V08_SRC_ICI_SARCOID_LIKE_REACTION_2026 | ICI-associated sarcoidosis-like reaction | review | auxiliary_review | moderate | yes | context_only | yes | yes | yes | yes | no |
| V08_SRC_COCCIDIOIDOMYCOSIS_SARCOID_MIMIC_CASE | Coccidioidomycosis sarcoid mimic | case report | case_example_cautionary | limited | yes | no_general_claim | yes | yes | yes | yes | no |
| V08_SRC_HISTOPLASMOSIS_SARCOIDOSIS_CASE_REVIEW | Histoplasmosis vs sarcoidosis | case report / literature review | case_example_cautionary | limited | yes | no_general_claim | yes | yes | yes | yes | no |
| V08_INTERNAL_V070_SEAL | Non-UIP differential seal | internal governance | internal_governance | internal | no | governance_only | yes | yes | yes | yes | no |
| V08_INTERNAL_V080_ENTRY_GATE | v0.8 source intake entry gate | internal governance | internal_governance | internal | no | governance_only | yes | yes | yes | yes | no |

---

## 7. Source Family Role Boundaries

### 7.1 Occupational ILD / Pneumoconiosis / Asbestosis

Source role:

- primary_high_authority.

Allowed future mapping:

- occupational exposure prompt,
- inorganic dust exposure prompt,
- pneumoconiosis/asbestosis source boundary,
- missing occupational history prompt,
- radiologic pattern caution,
- occupational medicine review prompt.

Blocked use:

- occupational ILD diagnosis,
- asbestosis diagnosis,
- pneumoconiosis diagnosis,
- occupational causation decision,
- compensation/medicolegal conclusion,
- treatment/surveillance plan.

---

### 7.2 Chronic Beryllium Disease / Beryllium Sensitivity

Source role:

- primary_high_authority.

Allowed future mapping:

- beryllium exposure prompt,
- beryllium sensitization vs CBD distinction,
- sarcoidosis mimic visibility,
- BeLPT context visibility,
- occupational medicine review prompt.

Blocked use:

- BeS diagnosis,
- CBD diagnosis,
- BeLPT interpretation authority,
- occupational causation conclusion,
- treatment plan.

---

### 7.3 TB Diagnosis Source

Source role:

- primary_high_authority.

Allowed future mapping:

- TB mimic visibility,
- microbiology missing-evidence prompt,
- smear/culture/NAAT limitation prompt,
- infection mimic visibility in granulomatous disease,
- urgent review prompt where relevant.

Blocked use:

- TB diagnosis,
- TB exclusion,
- microbiology ordering,
- isolation/public health instruction,
- treatment recommendation.

---

### 7.4 NTM Pulmonary Disease Source

Source role:

- primary_high_authority.

Allowed future mapping:

- NTM mimic visibility,
- clinical-radiologic-microbiologic integration prompt,
- repeated microbiology context,
- NTM vs colonization/contamination caution,
- treatment-not-automatic caution.

Blocked use:

- NTM diagnosis,
- NTM exclusion,
- antibiotic recommendation,
- bronchoscopy decision,
- follow-up schedule.

---

### 7.5 Aspergillosis Source

Source role:

- primary_limited_scope.

Allowed future mapping:

- fungal mimic visibility,
- immunocompromised context,
- biomarker/test limitation prompt,
- imaging ambiguity prompt,
- urgent review prompt in severe infection contexts.

Blocked use:

- aspergillosis diagnosis,
- antifungal treatment recommendation,
- biomarker interpretation authority,
- test ordering,
- treatment monitoring.

---

### 7.6 Histoplasmosis Source

Source role:

- primary_limited_scope because current guideline update is treatment-heavy and narrow.

Allowed future mapping:

- endemic fungal mimic visibility,
- histoplasmoma / pulmonary histoplasmosis context,
- fungal mimic source status,
- diagnostic uncertainty prompt where source supports it,
- caution around granulomatous sarcoid mimic.

Blocked use:

- histoplasmosis diagnosis,
- antifungal treatment recommendation,
- routine treatment/no-treatment recommendation,
- follow-up interval,
- public-ready guidance.

---

### 7.7 Aspiration Source

Source role:

- primary_limited_scope.

Allowed future mapping:

- aspiration risk prompt,
- silent aspiration / microaspiration context where source supports,
- dependent injury prompt,
- OP-like consolidation overlap,
- infection/aspiration ambiguity.

Blocked use:

- aspiration pneumonia diagnosis,
- aspiration-related ILD diagnosis,
- antibiotic recommendation,
- swallow study order,
- airway/feeding management.

---

### 7.8 Drug-Induced / Therapy-Related ILD Sources

Source role:

- auxiliary_review.

Allowed future mapping:

- medication history prompt,
- temporal relationship prompt,
- alternative cause exclusion prompt,
- OP-like / NSIP-like / acute injury mimic visibility,
- evidence quality limitation.

Blocked use:

- drug-induced ILD diagnosis,
- causality assignment to specific drug,
- drug discontinuation,
- rechallenge decision,
- steroid or treatment recommendation.

---

### 7.9 Radiation Pneumonitis / Radiation-Induced Lung Injury Sources

Source role:

- primary_limited_scope for guideline source,
- auxiliary_review for review source.

Allowed future mapping:

- radiation therapy history prompt,
- radiation field/timing context,
- acute radiation pneumonitis vs chronic radiation fibrosis distinction,
- infection/tumor progression/drug toxicity mimic visibility,
- risk context where source supports.

Blocked use:

- radiation pneumonitis diagnosis,
- radiation fibrosis diagnosis,
- steroid recommendation,
- radiation plan change,
- risk calculation,
- follow-up interval.

---

### 7.10 Checkpoint Inhibitor Pneumonitis / ICI-Related Toxicity Sources

Source role:

- auxiliary_review / meta-analysis.

Allowed future mapping:

- ICI exposure prompt,
- CIP mimic visibility,
- pre-existing ILD risk context,
- infection/progression/radiation pneumonitis overlap,
- urgent review visibility.

Blocked use:

- CIP diagnosis,
- immunotherapy hold/restart,
- steroid recommendation,
- oncology treatment decision,
- grading authority.

---

### 7.11 Pulmonary Lymphangitic Carcinomatosis Sources

Source role:

- diagnostic_performance_study,
- case_example_cautionary.

Allowed future mapping:

- malignancy mimic visibility,
- septal thickening / peribronchovascular infiltration prompt,
- asymmetric interstitial disease prompt,
- pleural effusion / lymph node context,
- ILD/infection/edema mimic warning,
- tissue confirmation uncertainty.

Blocked use:

- PLC diagnosis,
- malignancy diagnosis,
- PET/CT interpretation authority,
- biopsy decision,
- oncology management recommendation.

---

### 7.12 Sarcoid-Like Reaction / Lymphoma / Malignancy Mimic Sources

Source role:

- auxiliary_review,
- case series / literature review.

Allowed future mapping:

- sarcoid-like reaction visibility in cancer patients,
- lymphoma relapse mimic prompt,
- recurrence vs benign granulomatous lymphadenopathy uncertainty,
- FDG-PET ambiguity prompt,
- histologic confirmation prompt as uncertainty visibility.

Blocked use:

- lymphoma diagnosis,
- lymphoma relapse exclusion,
- sarcoid-like reaction diagnosis,
- malignancy exclusion,
- biopsy decision,
- oncology management recommendation.

---

### 7.13 Case-Example Fungal Mimic Sources

Source role:

- case_example_cautionary.

Allowed future mapping:

- cautionary test case inspiration,
- sarcoidosis/fungal mimic warning,
- travel/endemic exposure prompt,
- microbiology/pathology missing evidence prompt.

Blocked use:

- fungal diagnosis,
- general rule generation,
- source parity seal,
- treatment recommendation.

---

## 8. Treatment-Heavy Source Classification

The following sources are treatment-heavy or management-heavy.

| Source ID | Treatment-Heavy Status | Restriction |
|---|---|---|
| V08_SRC_IDSA_ASPERGILLOSIS_2016 | yes | use only for fungal mimic / diagnostic uncertainty / source limitation |
| V08_SRC_IDSA_HISTOPLASMOSIS_2025 | yes | use only for endemic fungal context and source role; no treatment import |
| V08_SRC_BTS_ASPIRATION_2023 | partial | no antibiotic, swallow, airway, or follow-up instruction |
| V08_SRC_DRUG_INDUCED_ILD_REVIEWS | yes | no drug discontinuation, steroid, rechallenge, or oncologic treatment change |
| V08_SRC_ESTRO_RADIATION_PNEUMONITIS_2025 | yes | no steroid, radiotherapy, or management instruction |
| V08_SRC_CHEST_RILI_2019 | yes | no treatment or management import |
| V08_SRC_ICI_SARCOID_LIKE_REACTION_2026 | yes | no immunotherapy hold/restart or steroid instruction |
| V08_SRC_PLC_MIMICKING_ILD_CASE_2025 | yes | no oncology management import |

Treatment-heavy rule:

> Treatment-heavy sources may support mimic visibility, but treatment authority remains none.

---

## 9. Diagnostic Performance Source Classification

The following sources evaluate diagnostic performance or imaging behavior.

| Source ID | Diagnostic Performance Use | Restriction |
|---|---|---|
| V08_SRC_PLC_HRCT_PET_DIAGNOSTIC_PERFORMANCE_2020 | HRCT/PET-CT feature visibility for PLC | no automated PET/CT or HRCT interpretation |
| V08_SRC_SARCOID_LIKE_REACTION_NEOPLASTIC_PATIENTS | EBUS/EUS-TBNA yield and benign granulomatous lymphadenopathy context | no biopsy decision |
| V08_SRC_SARCOIDOSIS_AFTER_LYMPHOMA_2014 | CT/PET relapse mimic context | no lymphoma relapse determination |
| V08_SRC_ICI_SARCOID_LIKE_REACTION_2026 | surveillance imaging ambiguity | no recurrence vs SLR diagnosis |

Diagnostic performance rule:

> Diagnostic-performance evidence may show ambiguity and limitations, but it cannot automate interpretation or management.

---

## 10. Case-Example Source Classification

The following sources are admitted only as cautionary examples.

| Source ID | Case Example Use | Restriction |
|---|---|---|
| V08_SRC_COCCIDIOIDOMYCOSIS_SARCOID_MIMIC_CASE | fungal disease misread as sarcoid-like process | no generalized fungal rule |
| V08_SRC_HISTOPLASMOSIS_SARCOIDOSIS_CASE_REVIEW | histoplasmosis vs sarcoidosis resemblance and workup caution | no histoplasmosis parity |
| V08_SRC_PLC_MIMICKING_ILD_CASE_2025 | PLC mimicking ILD/infection | no PLC diagnostic rule |

Case-example rule:

> A case report can inspire a test case, not a platform rule.

---

## 11. Claim Eligibility Matrix

| Source Family | Eligible Claim Types at v0.8.1 | Not Eligible Yet |
|---|---|---|
| Occupational ILD | source role; exposure prompt eligibility; missing occupational history visibility | diagnostic criteria implementation |
| Beryllium | source role; BeS/CBD distinction candidate; sarcoid mimic visibility | BeLPT interpretation or CBD diagnosis |
| TB | source role; infection mimic visibility; microbiology evidence gap | TB diagnosis/exclusion |
| NTM | source role; clinical-radiologic-microbiologic integration prompt | NTM diagnosis/exclusion |
| Aspergillosis | fungal mimic visibility; immunocompromised context | antifungal treatment or diagnosis |
| Histoplasmosis | endemic fungal mimic visibility | treatment/no-treatment recommendation |
| Aspiration | aspiration risk and dependent injury prompt | aspiration pneumonia diagnosis |
| Drug-induced ILD | medication/therapy history prompt; alternative cause visibility | causality assignment or drug stop |
| Radiation pneumonitis | radiation timing/field context; mimic visibility | RP diagnosis or management |
| Checkpoint inhibitor pneumonitis | ICI exposure and risk context | CIP diagnosis or ICI management |
| PLC | malignancy mimic feature visibility | PLC diagnosis |
| Lymphoma / sarcoid-like reaction | recurrence mimic and granulomatous lymphadenopathy ambiguity | malignancy or SLR diagnosis |
| Fungal case examples | cautionary test design | generalizable claims |

---

## 12. Source Debt Status After v0.8.1

| Debt ID | Domain | v0.8.0 Status | v0.8.1 Status | Still Blocks |
|---|---|---|---|---|
| V08_DEBT_OCC_001 | Occupational ILD / pneumoconiosis / asbestosis | source_candidate_present | role_mapped | claim mapping; domain parity |
| V08_DEBT_BERYL_001 | Chronic beryllium disease | source_candidate_present | role_mapped | claim mapping; domain parity |
| V08_DEBT_TB_001 | Tuberculosis mimic | source_candidate_present | role_mapped | claim mapping; domain parity |
| V08_DEBT_NTM_001 | NTM mimic | source_candidate_present | role_mapped | claim mapping; domain parity |
| V08_DEBT_FUNGAL_001 | Aspergillosis / fungal mimic | source_candidate_present_limited_scope | role_mapped_limited | claim mapping; domain parity |
| V08_DEBT_HISTO_001 | Histoplasmosis / endemic fungal mimic | source_candidate_present_treatment_heavy | role_mapped_limited | claim mapping; domain parity |
| V08_DEBT_COCCI_001 | Coccidioidomycosis mimic | case_example_present | cautionary_role_mapped | domain parity blocked |
| V08_DEBT_ASP_001 | Aspiration-related disease | source_candidate_present | role_mapped_limited | claim mapping; domain parity |
| V08_DEBT_DILD_001 | Drug-induced ILD | review_sources_present | auxiliary_role_mapped | claim mapping; domain parity |
| V08_DEBT_RP_001 | Radiation pneumonitis / RILI | guideline_and_review_present | role_mapped_limited | claim mapping; domain parity |
| V08_DEBT_CIP_001 | Checkpoint inhibitor pneumonitis | meta_analysis_present | auxiliary_role_mapped | claim mapping; domain parity |
| V08_DEBT_PLC_001 | Pulmonary lymphangitic carcinomatosis | diagnostic_performance_and_case_sources_present | role_mapped | claim mapping; domain parity |
| V08_DEBT_SLR_001 | Sarcoid-like reaction / malignancy mimic | review_and_case_series_present | role_mapped | claim mapping; domain parity |
| V08_DEBT_LYMPHOMA_001 | Lymphoma / sarcoidosis overlap | review_and_case_series_present | role_mapped | claim mapping; domain parity |

Debt status rule:

> Role mapping reduces source uncertainty but does not clear claim-mapping debt.

---

## 13. Missing Evidence Eligibility Map

| Missing Evidence Prompt | Source Families Supporting Future Mapping |
|---|---|
| occupational exposure history missing | occupational ILD; beryllium; sarcoid-like mimic |
| beryllium exposure / BeLPT context missing | beryllium source |
| microbiology missing | TB; NTM; fungal; sarcoid-like mimic; OP-like consolidation |
| endemic travel / fungal exposure missing | histoplasmosis; coccidioidomycosis; fungal source |
| immunosuppression context missing | fungal; TB/NTM; ICI toxicity; opportunistic infection |
| aspiration risk missing | aspiration source |
| medication / therapy history missing | drug-induced ILD; ICI SLR; RP/CIP context |
| radiation therapy history missing | RP/RILI source |
| radiation field / timing context missing | RP/RILI source |
| checkpoint inhibitor exposure missing | CIP/ICI SLR source |
| malignancy history missing | PLC; lymphoma; sarcoid-like reaction |
| PET/CT ambiguity present | PLC; sarcoid-like reaction; lymphoma |
| tissue/pathology context missing | PLC; lymphoma; sarcoid-like reaction; infection; beryllium |
| prior imaging missing | therapy-related toxicity; recurrence; infection; progression |
| nonresponse to empiric therapy | malignancy; infection; drug/radiation/ICI toxicity |
| urgent clinical status missing | infection; hemorrhage; vascular; acute respiratory failure; therapy toxicity |

---

## 14. Blocked Source Misuse Map

| Misuse | Block |
|---|---|
| using occupational source to diagnose asbestosis | blocked |
| using beryllium source to diagnose CBD or interpret BeLPT | blocked |
| using TB source to exclude TB | blocked |
| using NTM source to diagnose NTM | blocked |
| using fungal guideline to recommend antifungal therapy | blocked |
| using histoplasmosis guideline to decide treatment/no treatment | blocked |
| using aspiration statement to diagnose aspiration pneumonia | blocked |
| using DI-ILD review to stop a drug | blocked |
| using radiation pneumonitis guideline to start steroids | blocked |
| using CIP source to hold immunotherapy | blocked |
| using PLC imaging study to diagnose PLC | blocked |
| using PET/CT ambiguity source to decide recurrence | blocked |
| using sarcoid-like reaction source to exclude malignancy | blocked |
| using case report as general rule | blocked |
| using any source to claim public readiness | blocked |
| using any source to claim clinical review | blocked |

---

## 15. Acceptance Criteria

v0.8.1 is accepted only if:

- every admitted source has a role class,
- every admitted source has an authority level,
- treatment-heavy sources are identified,
- diagnostic-performance sources are constrained,
- case-example sources are constrained,
- domain parity remains closed,
- source debt remains visible,
- claim mapping remains future work,
- missing evidence eligibility is mapped,
- blocked uses are explicit,
- diagnostic_authority remains none,
- treatment_authority remains none,
- public_ready remains false,
- clinically_reviewed remains false.

---

## 16. Next Step

The next recommended step is:

- v0.8.2 — High-Risk Mimic Claim-to-Source Mapping Table

v0.8.2 should map only source-supported, non-authoritative claims.

It should not open domain parity.

It should map claim families such as:

- occupational exposure missing evidence,
- beryllium as sarcoidosis mimic,
- TB/NTM/fungal infection mimic visibility,
- aspiration risk prompt,
- drug/therapy-related temporal relationship prompt,
- radiation timing/field context,
- ICI exposure and sarcoid-like reaction / pneumonitis ambiguity,
- PLC as ILD/infection/edema mimic,
- lymphoma / malignancy / sarcoid-like reaction ambiguity.

v0.8.2 must preserve:

- diagnostic_authority: none,
- treatment_authority: none,
- public_ready: false,
- clinically_reviewed: false.

---

## 17. Governance Statement

This source role map classifies v0.8 source candidates.

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

The v0.8 rule remains:

> “Source intake precedes source claims. Source claims precede domain parity.”