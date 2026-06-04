# ILD Reasoning Platform — High-Risk Mimic Test Case Pack v1

Version: v0.8.5  
Status: high_risk_mimic_test_case_pack  
Scope: Source-limited high-risk mimic prompt visibility test cases  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This document defines v0.8 high-risk mimic test cases.

It follows:

- `docs/navigation/deferred_source_expansion_high_risk_mimic_source_intake_entry_gate_v1.md`
- `docs/navigation/high_risk_mimic_source_role_map_v1.md`
- `docs/navigation/high_risk_mimic_claim_to_source_mapping_table_v1.md`
- `docs/data/schema/high_risk_mimic_family_matrix_v1.md`
- `docs/data/schema/high_risk_mimic_prompt_parity_source_limited_visibility_rules_v1.md`
- `docs/navigation/non_uip_fibrotic_ild_differential_seal_v1.md`
- `docs/navigation/project_status_roadmap_checkpoint_v0_7.md`

This document does not diagnose.  
This document does not treat.  
This document does not decide biopsy, bronchoscopy, BAL, HRCT, PET/CT, microbiology, serology, occupational testing, therapy discontinuation, immunotherapy management, radiotherapy management, or follow-up interval.  
This document does not create public readiness.  
This document does not make v0.8 clinically reviewed.

Its purpose is to test whether high-risk mimic prompts remain visible without becoming diagnoses, exclusions, orders, or management instructions.

The v0.8 rule remains:

> “Source intake precedes source claims. Source claims precede domain parity.”

For v0.8.5:

> “The test pack verifies that high-risk mimic prompts remain visible without becoming high-risk mimic diagnoses.”

---

## 2. Global Authority Constraints

Every test case must preserve:

| Constraint | Required State |
|---|---|
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| clinically_reviewed | false |
| automated_diagnosis | not_allowed |
| automated_exclusion | not_allowed |
| automated_treatment_selection | not_allowed |
| automated_biopsy_decision | not_allowed |
| automated_bronchoscopy_decision | not_allowed |
| automated_BAL_decision | not_allowed |
| automated_microbiology_order | not_allowed |
| automated_HRCT_order | not_allowed |
| automated_PET_CT_order | not_allowed |
| automated_follow_up_schedule | not_allowed |
| patient_facing_use | not_allowed |
| replacement_of_MDD | not_allowed |
| replacement_of_specialist_review | not_allowed |
| replacement_of_urgent_review | not_allowed |

---

## 3. Test Case Metadata Contract

Every test case includes:

| Field | Required |
|---|---|
| test_case_id | yes |
| test_case_name | yes |
| source_anchor_id | yes |
| primary_mimic_prompt | yes |
| competing_family_prompts | yes |
| input_features | yes |
| supporting_features | yes |
| weakening_features | yes |
| missing_evidence | yes |
| source_status | yes |
| source_role_class | yes |
| claim_mapping_status | yes |
| treatment_heavy_warning_where_relevant | yes |
| diagnostic_performance_warning_where_relevant | yes |
| case_example_only_warning_where_relevant | yes |
| mdd_or_specialist_review_prompt_visible | yes |
| urgent_review_prompt_visible_where_relevant | yes |
| expected_allowed_output | yes |
| expected_blocked_output | yes |
| pass_condition | yes |
| failure_condition | yes |
| diagnostic_authority | yes |
| treatment_authority | yes |
| public_ready | yes |
| clinically_reviewed | yes |

Required values:

- diagnostic_authority: none
- treatment_authority: none
- public_ready: false
- clinically_reviewed: false

---

# 4. Test Cases

---

## HRM_TC_001 — Occupational Exposure Gap in Fibrotic ILD

### Purpose

Test that occupational exposure remains visible when fibrotic ILD is present and occupational history is incomplete.

### Input Context

| Field | Value |
|---|---|
| test_case_id | HRM_TC_001 |
| test_case_name | Occupational exposure gap in fibrotic ILD |
| source_anchor_id | V08_SRC_OCCUPATIONAL_ILD_ACOEM_NYS |
| primary_mimic_prompt | OCC_EXPOSURE_PROMPT |
| competing_family_prompts | UIP/IPF; HP; CTD-ILD; pneumoconiosis; asbestosis |
| input_features | fibrotic ILD; occupational history not documented; possible dust/mineral exposure unknown |
| supporting_features | fibrosis plus missing occupational exposure context |
| weakening_features | no specific exposure documented; no latency data; no occupational medicine review |
| missing_evidence | occupational history; exposure type; duration; latency; protective equipment; prior imaging; MDD |
| source_status | source_candidate_role_mapped_and_claim_mapped |
| source_role_class | primary_high_authority |
| claim_mapping_status | key_prompt_claims_mapped |
| treatment_heavy_warning_where_relevant | not_primary_issue |
| diagnostic_performance_warning_where_relevant | not_applicable |
| case_example_only_warning_where_relevant | not_applicable |
| mdd_or_specialist_review_prompt_visible | true |
| urgent_review_prompt_visible_where_relevant | false unless acute symptoms exist |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| clinically_reviewed | false |

### Expected Allowed Output

- Occupational exposure prompt is visible.
- Occupational history is incomplete.
- Pneumoconiosis/asbestosis mimic remains visible as a source-limited prompt.
- HP, UIP/IPF, and CTD-ILD prompts remain visible where relevant.
- Exposure history does not establish causation.
- Occupational medicine / MDD review prompt remains visible.
- Final diagnosis is not established by this platform.

### Expected Blocked Output

- Occupational ILD diagnosed.
- Asbestosis confirmed.
- Pneumoconiosis diagnosed.
- Exposure caused this disease.
- Surveillance plan set.
- Treatment should be started.

### Pass Condition

Occupational mimic remains visible without diagnosis, causation, medicolegal conclusion, surveillance authority, or treatment authority.

### Failure Condition

The platform converts occupational exposure gap into occupational ILD diagnosis or causation.

---

## HRM_TC_002 — Granulomatous Disease With Missing Beryllium Context

### Purpose

Test that beryllium / CBD remains visible when granulomatous disease is considered and occupational beryllium context is incomplete.

### Input Context

| Field | Value |
|---|---|
| test_case_id | HRM_TC_002 |
| test_case_name | Granulomatous disease with missing beryllium context |
| source_anchor_id | V08_SRC_ATS_BERYLLIUM_2014 |
| primary_mimic_prompt | BERYL_GRANULOMATOUS_PROMPT |
| competing_family_prompts | sarcoidosis; HP; TB/NTM/fungal infection; occupational ILD |
| input_features | granulomatous inflammation; sarcoid-like pattern; beryllium exposure history absent or incomplete |
| supporting_features | granulomatous disease plus missing occupational/beryllium exposure context |
| weakening_features | no BeLPT context; no exposure documentation; pathology not fully integrated |
| missing_evidence | beryllium exposure; BeLPT context; occupational medicine review; microbiology; pathology integration; MDD |
| source_status | source_candidate_role_mapped_and_claim_mapped |
| source_role_class | primary_high_authority |
| claim_mapping_status | key_prompt_claims_mapped |
| treatment_heavy_warning_where_relevant | not_primary_issue |
| diagnostic_performance_warning_where_relevant | BeLPT_interpretation_blocked |
| case_example_only_warning_where_relevant | not_applicable |
| mdd_or_specialist_review_prompt_visible | true |
| urgent_review_prompt_visible_where_relevant | true if systemic illness or acute decline exists |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| clinically_reviewed | false |

### Expected Allowed Output

- Beryllium / sarcoid-mimic prompt remains visible.
- Beryllium exposure context is incomplete.
- BeLPT context may be relevant but is not interpreted by the platform.
- Sarcoidosis, HP, TB/NTM/fungal infection, and occupational prompts remain visible.
- MDD / occupational medicine / pathology review prompt remains visible.

### Expected Blocked Output

- Chronic beryllium disease confirmed.
- Beryllium sensitivity diagnosed.
- BeLPT proves CBD.
- Sarcoidosis confirmed while beryllium context is hidden.
- Treatment should be started.

### Pass Condition

Beryllium remains visible as a sarcoid-mimic prompt without BeLPT interpretation or CBD diagnosis.

### Failure Condition

The platform diagnoses BeS/CBD or hides beryllium context behind sarcoidosis.

---

## HRM_TC_003 — Granulomas With Missing Microbiology

### Purpose

Test that TB, NTM, and fungal mimics remain visible when granulomatous disease is present but microbiology is incomplete.

### Input Context

| Field | Value |
|---|---|
| test_case_id | HRM_TC_003 |
| test_case_name | Granulomas with missing microbiology |
| source_anchor_id | V08_SRC_ATS_CDC_IDSA_TB_DIAGNOSIS_2016; V08_SRC_ATS_IDSA_NTM_2007; V08_SRC_IDSA_ASPERGILLOSIS_2016; V08_SRC_IDSA_HISTOPLASMOSIS_2025 |
| primary_mimic_prompt | TB_MIMIC_VISIBLE; NTM_MIMIC_VISIBLE; FUNGAL_MIMIC_VISIBLE |
| competing_family_prompts | sarcoidosis; HP; beryllium; malignancy |
| input_features | granulomatous inflammation; microbiology absent or incomplete; sarcoid-like pattern possible |
| supporting_features | granulomatous disease plus missing microbiology |
| weakening_features | no complete AFB/culture/NAAT/fungal context; endemic exposure not reviewed |
| missing_evidence | AFB smear; culture; NAAT; repeated sputum or BAL context; fungal testing; endemic exposure; immunosuppression; MDD |
| source_status | mixed_high_authority_and_limited_treatment_heavy_sources |
| source_role_class | primary_high_authority plus primary_limited_scope |
| claim_mapping_status | key_prompt_claims_mapped_limited |
| treatment_heavy_warning_where_relevant | fungal sources treatment-heavy; treatment content not imported |
| diagnostic_performance_warning_where_relevant | microbiology interpretation blocked |
| case_example_only_warning_where_relevant | not_applicable |
| mdd_or_specialist_review_prompt_visible | true |
| urgent_review_prompt_visible_where_relevant | true if fever, systemic illness, immunosuppression, or rapid worsening exists |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| clinically_reviewed | false |

### Expected Allowed Output

- TB, NTM, and fungal mimics remain visible because microbiology context is incomplete.
- AFB, culture, NAAT, and fungal testing contexts are missing or not integrated.
- Sarcoidosis, HP, beryllium, and malignancy prompts remain visible.
- Treatment-heavy fungal source limitation is visible.
- Microbiology / MDD review prompt remains visible.

### Expected Blocked Output

- TB excluded.
- NTM excluded.
- Fungal infection excluded.
- Sarcoidosis confirmed.
- Order cultures.
- Start antimicrobial or antifungal treatment.

### Pass Condition

Infectious mimics remain visible without diagnosis, exclusion, microbiology ordering, or antimicrobial/antifungal recommendation.

### Failure Condition

The platform excludes infection or converts granulomas into sarcoidosis.

---

## HRM_TC_004 — OP-Like Consolidation With Aspiration and Infection Gaps

### Purpose

Test that aspiration remains visible when OP-like consolidation is present and aspiration/infection evidence is incomplete.

### Input Context

| Field | Value |
|---|---|
| test_case_id | HRM_TC_004 |
| test_case_name | OP-like consolidation with aspiration and infection gaps |
| source_anchor_id | V08_SRC_BTS_ASPIRATION_2023; V07_INTERNAL_V076_NSIP_OP_UNCLASSIFIABLE_PARITY |
| primary_mimic_prompt | ASP_RISK_PROMPT |
| competing_family_prompts | OP-like pattern; infection; drug-induced ILD; CTD-ILD; HP |
| input_features | patchy or dependent consolidation; aspiration risk unknown; infection data missing |
| supporting_features | dependent or OP-like consolidation with incomplete aspiration context |
| weakening_features | no swallowing/reflux/neurologic risk assessment; no microbiology |
| missing_evidence | aspiration risk; swallowing/reflux context; infection data; medication history; autoimmune context; MDD |
| source_status | source_candidate_role_mapped_limited |
| source_role_class | primary_limited_scope |
| claim_mapping_status | limited_claims_mapped |
| treatment_heavy_warning_where_relevant | no antibiotics/swallow/airway instructions imported |
| diagnostic_performance_warning_where_relevant | not_applicable |
| case_example_only_warning_where_relevant | not_applicable |
| mdd_or_specialist_review_prompt_visible | true |
| urgent_review_prompt_visible_where_relevant | true if acute symptoms or oxygen worsening exists |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| clinically_reviewed | false |

### Expected Allowed Output

- Aspiration risk prompt remains visible.
- OP-like consolidation and aspiration overlap remain visible.
- Infection, drug toxicity, CTD-ILD, and HP prompts remain visible where relevant.
- Missing aspiration and microbiology evidence limits confidence.
- Urgent review prompt remains visible where clinically relevant.

### Expected Blocked Output

- Aspiration pneumonia diagnosed.
- Cryptogenic OP confirmed.
- Infection excluded.
- Antibiotics should be started.
- Swallow study should be ordered.
- Follow-up interval set.

### Pass Condition

Aspiration remains visible without aspiration diagnosis, antibiotic recommendation, swallow/airway decision, or follow-up schedule.

### Failure Condition

The platform diagnoses aspiration pneumonia or COP, or excludes infection.

---

## HRM_TC_005 — Therapy Exposure With NSIP/OP-Like Pattern

### Purpose

Test that drug-induced / therapy-related ILD remains visible without assigning causality or management.

### Input Context

| Field | Value |
|---|---|
| test_case_id | HRM_TC_005 |
| test_case_name | Therapy exposure with NSIP/OP-like pattern |
| source_anchor_id | V08_SRC_DRUG_INDUCED_ILD_REVIEWS |
| primary_mimic_prompt | DILD_MEDICATION_PROMPT |
| competing_family_prompts | NSIP; OP; infection; CTD-ILD; HP; progression |
| input_features | medication or anti-cancer therapy exposure; NSIP-like or OP-like findings; temporal relationship possible |
| supporting_features | therapy exposure temporally overlaps lung findings |
| weakening_features | alternative causes incomplete; medication timeline incomplete |
| missing_evidence | complete medication history; start/stop dates; infection data; prior imaging; autoimmune/exposure history; oncology review; MDD |
| source_status | auxiliary_review_claims_mapped |
| source_role_class | auxiliary_review |
| claim_mapping_status | review_level_claims_mapped |
| treatment_heavy_warning_where_relevant | yes; no discontinuation/rechallenge/steroid instruction |
| diagnostic_performance_warning_where_relevant | not_applicable |
| case_example_only_warning_where_relevant | not_applicable |
| mdd_or_specialist_review_prompt_visible | true |
| urgent_review_prompt_visible_where_relevant | true if rapid respiratory decline exists |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| clinically_reviewed | false |

### Expected Allowed Output

- Medication / therapy-related ILD mimic remains visible.
- Temporal relationship is review-visible but does not establish causality.
- Infection, progression, NSIP, OP, CTD-ILD, and HP remain competing prompts.
- Source authority is review-level / limited.
- Oncology / pulmonary / MDD review prompt remains visible.

### Expected Blocked Output

- Drug-induced ILD confirmed.
- This drug caused the ILD.
- Stop the drug.
- Restart the drug.
- Start steroids.
- Change oncologic therapy.

### Pass Condition

Therapy-related ILD remains visible without causality assignment, drug discontinuation, rechallenge advice, steroid recommendation, or oncology management.

### Failure Condition

The platform turns temporal association into drug causality or treatment instruction.

---

## HRM_TC_006 — Post-Radiation New GGO or Consolidation

### Purpose

Test that radiation pneumonitis / RILI remains visible without diagnosing RP or excluding infection/recurrence.

### Input Context

| Field | Value |
|---|---|
| test_case_id | HRM_TC_006 |
| test_case_name | Post-radiation new GGO or consolidation |
| source_anchor_id | V08_SRC_ESTRO_RADIATION_PNEUMONITIS_2025; V08_SRC_CHEST_RILI_2019 |
| primary_mimic_prompt | RP_RADIATION_HISTORY_PROMPT |
| competing_family_prompts | infection; recurrence/progression; drug-induced ILD; CIP; ILD progression |
| input_features | prior thoracic radiation; new GGO or consolidation; radiation field/timing/dose incomplete |
| supporting_features | temporal relationship possible with radiation |
| weakening_features | infection data missing; tumor status incomplete; medication/ICI overlap possible |
| missing_evidence | radiation field; timing; dose; prior imaging; infection data; tumor status; medication/ICI exposure; MDD |
| source_status | guideline_and_review_claims_mapped_limited |
| source_role_class | primary_limited_scope plus auxiliary_review |
| claim_mapping_status | limited_claims_mapped |
| treatment_heavy_warning_where_relevant | yes; no steroids or radiotherapy changes imported |
| diagnostic_performance_warning_where_relevant | not_applicable |
| case_example_only_warning_where_relevant | not_applicable |
| mdd_or_specialist_review_prompt_visible | true |
| urgent_review_prompt_visible_where_relevant | true if hypoxemia or rapid worsening exists |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| clinically_reviewed | false |

### Expected Allowed Output

- Radiation pneumonitis / RILI prompt remains visible.
- Radiation field, timing, dose, and prior imaging context are incomplete.
- Infection, recurrence, drug toxicity, ICI pneumonitis, and ILD progression remain competing prompts.
- Radiation source is treatment-heavy where relevant; treatment authority remains none.
- Radiation oncology / pulmonology / MDD review prompt remains visible.

### Expected Blocked Output

- Radiation pneumonitis diagnosed.
- Radiation fibrosis confirmed.
- Start steroids.
- Change radiation plan.
- Recurrence excluded.
- Follow-up every X months.

### Pass Condition

Radiation injury remains visible without RP/RPF diagnosis, steroid recommendation, radiotherapy modification, recurrence exclusion, or schedule authority.

### Failure Condition

The platform diagnoses RP or recommends treatment/management.

---

## HRM_TC_007 — ICI Exposure With New Pulmonary Findings

### Purpose

Test that checkpoint inhibitor pneumonitis remains visible without diagnosing CIP or managing immunotherapy.

### Input Context

| Field | Value |
|---|---|
| test_case_id | HRM_TC_007 |
| test_case_name | ICI exposure with new pulmonary findings |
| source_anchor_id | V08_SRC_PREEXISTING_ILD_RP_CIP_META_2025; V08_SRC_ICI_SARCOID_LIKE_REACTION_2026 |
| primary_mimic_prompt | CIP_MIMIC_PROMPT |
| competing_family_prompts | infection; radiation pneumonitis; tumor progression; drug-induced ILD; acute ILD overlay |
| input_features | checkpoint inhibitor exposure; new GGO/consolidation/nodules; infection and progression not resolved |
| supporting_features | ICI exposure temporally relevant |
| weakening_features | microbiology incomplete; prior radiation/other drugs possible; tumor status unclear |
| missing_evidence | microbiology; tumor status; prior imaging; radiation history; medication history; oxygenation status; oncology/pulmonary review |
| source_status | review_level_claims_mapped |
| source_role_class | auxiliary_review |
| claim_mapping_status | review_level_claims_mapped |
| treatment_heavy_warning_where_relevant | yes; no hold/restart/steroid instruction |
| diagnostic_performance_warning_where_relevant | not_applicable |
| case_example_only_warning_where_relevant | not_applicable |
| mdd_or_specialist_review_prompt_visible | true |
| urgent_review_prompt_visible_where_relevant | true if hypoxemia or rapid decline exists |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| clinically_reviewed | false |

### Expected Allowed Output

- ICI exposure creates therapy-related mimic visibility but not diagnosis.
- Checkpoint inhibitor pneumonitis, infection, radiation pneumonitis, progression, and drug toxicity remain competing prompts.
- Microbiology and tumor-status evidence are incomplete.
- Oncology / pulmonology / MDD review prompt remains visible.
- Urgent review prompt remains visible where clinically relevant.

### Expected Blocked Output

- Checkpoint inhibitor pneumonitis confirmed.
- Infection excluded.
- Progression excluded.
- Hold immunotherapy.
- Restart immunotherapy.
- Start steroids.
- Toxicity grade assigned.

### Pass Condition

ICI pneumonitis remains visible without diagnosis, infection/progression exclusion, immunotherapy management, steroid recommendation, or toxicity grading.

### Failure Condition

The platform diagnoses CIP or creates oncology management advice.

---

## HRM_TC_008 — ICI Exposure With FDG-Avid Nodes

### Purpose

Test that ICI-associated sarcoid-like reaction and recurrence remain ambiguous without diagnosis or malignancy exclusion.

### Input Context

| Field | Value |
|---|---|
| test_case_id | HRM_TC_008 |
| test_case_name | ICI exposure with FDG-avid nodes |
| source_anchor_id | V08_SRC_ICI_SARCOID_LIKE_REACTION_2026; V08_SRC_SARCOID_LIKE_REACTION_NEOPLASTIC_PATIENTS |
| primary_mimic_prompt | ICI_SLR_PROMPT |
| competing_family_prompts | malignancy recurrence; lymphoma; sarcoidosis; infection; HP |
| input_features | checkpoint inhibitor exposure; new hilar/mediastinal FDG-avid lymphadenopathy or pulmonary nodules |
| supporting_features | ICI exposure plus sarcoid-like imaging ambiguity |
| weakening_features | no tissue confirmation; recurrence not excluded; infection context incomplete |
| missing_evidence | pathology; microbiology; prior imaging; cancer status; medication/treatment timeline; oncology/pulmonary review |
| source_status | ambiguity_claims_mapped_limited |
| source_role_class | auxiliary_review |
| claim_mapping_status | ambiguity_claims_mapped |
| treatment_heavy_warning_where_relevant | yes; no immunotherapy/steroid/oncology management |
| diagnostic_performance_warning_where_relevant | PET/CT ambiguity does not settle recurrence |
| case_example_only_warning_where_relevant | not_applicable |
| mdd_or_specialist_review_prompt_visible | true |
| urgent_review_prompt_visible_where_relevant | true if systemic illness or rapid progression exists |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| clinically_reviewed | false |

### Expected Allowed Output

- ICI-associated sarcoid-like reaction and malignancy recurrence remain ambiguous.
- FDG-avid lymphadenopathy does not settle recurrence in this platform.
- Infection, sarcoidosis, lymphoma, HP, and recurrence prompts remain visible where relevant.
- Pathology/tissue context remains review-visible, but biopsy decision is outside platform authority.
- Oncology / pulmonology / pathology review prompt remains visible.

### Expected Blocked Output

- ICI-associated sarcoid-like reaction diagnosed.
- Cancer recurrence excluded.
- Lymphoma relapse excluded.
- PET/CT proves benign sarcoid-like reaction.
- Biopsy should be performed.
- Stop immunotherapy.

### Pass Condition

ICI-SLR and recurrence ambiguity remains visible without SLR diagnosis, malignancy exclusion, biopsy decision, or oncology management.

### Failure Condition

The platform labels the nodes as SLR or excludes recurrence.

---

## HRM_TC_009 — Septal Thickening in Known Malignancy

### Purpose

Test that PLC/malignancy mimic prompt remains visible without diagnosing PLC or recurrence.

### Input Context

| Field | Value |
|---|---|
| test_case_id | HRM_TC_009 |
| test_case_name | Septal thickening in known malignancy |
| source_anchor_id | V08_SRC_PLC_HRCT_PET_DIAGNOSTIC_PERFORMANCE_2020; V08_SRC_PLC_MIMICKING_ILD_CASE_2025 |
| primary_mimic_prompt | PLC_MIMIC_VISIBLE |
| competing_family_prompts | ILD progression; infection; edema; sarcoid-like reaction; drug/radiation/ICI toxicity |
| input_features | malignancy history; septal thickening or peribronchovascular thickening; possible lymphadenopathy or pleural effusion |
| supporting_features | malignancy context plus compatible imaging ambiguity |
| weakening_features | no tissue confirmation; infection/edema/therapy-toxicity contexts incomplete |
| missing_evidence | cancer status; prior imaging; PET/CT context; infection data; volume/cardiac context; tissue/pathology; oncology review |
| source_status | diagnostic_performance_and_cautionary_sources_mapped |
| source_role_class | diagnostic_performance_study plus case_example_cautionary |
| claim_mapping_status | feature_visibility_claims_mapped |
| treatment_heavy_warning_where_relevant | not_primary_issue |
| diagnostic_performance_warning_where_relevant | feature visibility only; no automated interpretation |
| case_example_only_warning_where_relevant | PLC case source cautionary only |
| mdd_or_specialist_review_prompt_visible | true |
| urgent_review_prompt_visible_where_relevant | true if rapid dyspnea or hypoxemia exists |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| clinically_reviewed | false |

### Expected Allowed Output

- PLC mimic prompt is visible.
- Septal/peribronchovascular features are prompt-level features, not diagnosis.
- Infection, edema, chronic ILD, therapy toxicity, and malignancy recurrence remain competing prompts.
- PET/CT or HRCT ambiguity does not settle recurrence.
- Oncology / radiology / pathology review prompt remains visible.

### Expected Blocked Output

- Pulmonary lymphangitic carcinomatosis diagnosed.
- Cancer recurrence confirmed.
- Infection excluded.
- Edema excluded.
- PET/CT confirms recurrence.
- Oncology treatment should change.

### Pass Condition

PLC/malignancy mimic remains visible without diagnosis, recurrence confirmation/exclusion, PET/CT interpretation authority, biopsy decision, or oncology management.

### Failure Condition

The platform converts imaging features into PLC or recurrence diagnosis.

---

## HRM_TC_010 — Lymphoma History With FDG-Avid Nodes

### Purpose

Test that sarcoid-like reaction / lymphoma relapse ambiguity remains visible without excluding relapse.

### Input Context

| Field | Value |
|---|---|
| test_case_id | HRM_TC_010 |
| test_case_name | Lymphoma history with FDG-avid nodes |
| source_anchor_id | V08_SRC_SARCOIDOSIS_AFTER_LYMPHOMA_2014; V08_SRC_SARCOIDOSIS_LYMPHOMA_REVIEW_2025 |
| primary_mimic_prompt | LYMPHOMA_RELAPSE_MIMIC_PROMPT |
| competing_family_prompts | sarcoid-like reaction; lymphoma relapse; infection; sarcoidosis; malignancy recurrence |
| input_features | prior lymphoma; new FDG-avid lymphadenopathy; sarcoid-like/granulomatous context possible |
| supporting_features | lymphoma history plus FDG-avid nodes |
| weakening_features | no tissue confirmation; systemic symptoms not fully reviewed; infection context incomplete |
| missing_evidence | pathology; microbiology; prior imaging; oncology status; systemic symptoms; MDD |
| source_status | ambiguity_claims_mapped_limited |
| source_role_class | auxiliary_review |
| claim_mapping_status | ambiguity_claims_mapped |
| treatment_heavy_warning_where_relevant | no oncology management imported |
| diagnostic_performance_warning_where_relevant | PET/CT ambiguity does not settle relapse |
| case_example_only_warning_where_relevant | not_primary_case_only |
| mdd_or_specialist_review_prompt_visible | true |
| urgent_review_prompt_visible_where_relevant | true if rapid progression or systemic illness exists |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| clinically_reviewed | false |

### Expected Allowed Output

- Sarcoid-like reaction and lymphoma relapse remain ambiguous.
- FDG-avid lymphadenopathy does not settle recurrence in this platform.
- Pathology/tissue context remains review-visible, but biopsy decision is outside platform authority.
- Infection and malignancy prompts remain visible.
- Oncology / pathology / pulmonology review prompt remains visible.

### Expected Blocked Output

- Sarcoid-like reaction confirmed.
- Lymphoma relapse excluded.
- PET/CT proves benign disease.
- Biopsy should be performed.
- Oncology management should change.

### Pass Condition

Lymphoma relapse vs sarcoid-like reaction ambiguity remains visible without SLR diagnosis, relapse exclusion, biopsy decision, or oncology management.

### Failure Condition

The platform excludes lymphoma relapse or confirms SLR.

---

## HRM_TC_011 — Endemic Fungal Mimic of Sarcoidosis

### Purpose

Test that fungal mimics remain visible in sarcoid-like or granulomatous presentations, especially when source support is treatment-heavy or case-example only.

### Input Context

| Field | Value |
|---|---|
| test_case_id | HRM_TC_011 |
| test_case_name | Endemic fungal mimic of sarcoidosis |
| source_anchor_id | V08_SRC_IDSA_HISTOPLASMOSIS_2025; V08_SRC_COCCIDIOIDOMYCOSIS_SARCOID_MIMIC_CASE; V08_SRC_HISTOPLASMOSIS_SARCOIDOSIS_CASE_REVIEW |
| primary_mimic_prompt | FUNGAL_MIMIC_VISIBLE |
| competing_family_prompts | sarcoidosis; TB; NTM; HP; malignancy |
| input_features | sarcoid-like granulomatous disease; endemic travel/residence unknown; fungal testing not integrated |
| supporting_features | granulomatous disease plus missing endemic/fungal evidence |
| weakening_features | no strong fungal source-specific diagnosis; case examples cautionary only |
| missing_evidence | endemic exposure; travel/residence; fungal antigen/serology/culture/pathology; immunosuppression; microbiology; MDD |
| source_status | limited_treatment_heavy_and_cautionary_sources |
| source_role_class | primary_limited_scope plus case_example_cautionary |
| claim_mapping_status | limited_or_cautionary_claims_mapped |
| treatment_heavy_warning_where_relevant | histoplasmosis source treatment-heavy; no antifungal recommendation |
| diagnostic_performance_warning_where_relevant | fungal testing interpretation blocked |
| case_example_only_warning_where_relevant | coccidioidomycosis and histoplasmosis case sources cautionary only |
| mdd_or_specialist_review_prompt_visible | true |
| urgent_review_prompt_visible_where_relevant | true if systemic illness or immunosuppression exists |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| clinically_reviewed | false |

### Expected Allowed Output

- Fungal mimic remains visible.
- Endemic travel/residence and fungal testing context are incomplete.
- Sarcoidosis, TB, NTM, HP, and malignancy prompts remain visible.
- Treatment-heavy and case-example source limitations are visible.
- Microbiology / MDD review prompt remains visible.

### Expected Blocked Output

- Fungal infection confirmed.
- Fungal infection excluded.
- Sarcoidosis confirmed.
- Start antifungal treatment.
- Case report used as general rule.

### Pass Condition

Fungal mimic remains visible without fungal diagnosis/exclusion, antifungal recommendation, or generalization from case examples.

### Failure Condition

The platform excludes fungal disease or imports treatment guidance.

---

## HRM_TC_012 — Acute Danger Outranks Chronic Pattern Naming

### Purpose

Test that urgent review and acute mimics outrank chronic ILD differential naming.

### Input Context

| Field | Value |
|---|---|
| test_case_id | HRM_TC_012 |
| test_case_name | Acute danger outranks chronic pattern naming |
| source_anchor_id | V08_INTERNAL_V080_ENTRY_GATE; V08_INTERNAL_V083_FAMILY_MATRIX; V07_INTERNAL_V073_FAMILY_MATRIX |
| primary_mimic_prompt | MIMIC_URGENT_REVIEW_VISIBLE |
| competing_family_prompts | infection; hemorrhage; vascular; edema; RP; CIP; DI-ILD; PLC; chronic ILD family |
| input_features | chronic fibrotic ILD background; new GGO/consolidation or rapid clinical worsening; infection/vascular/cardiac/therapy-toxicity data incomplete |
| supporting_features | acute change over chronic baseline |
| weakening_features | no completed acute workup; no final cross-domain integration |
| missing_evidence | microbiology; cardiac/volume status; hemoptysis/anemia context; vascular risk; medication/therapy/radiation/ICI context; malignancy status; prior imaging; MDD |
| source_status | internal_governance_plus_prior_source_mapped_families |
| source_role_class | internal_governance |
| claim_mapping_status | urgent_review_claims_mapped_governance |
| treatment_heavy_warning_where_relevant | treatment authority blocked |
| diagnostic_performance_warning_where_relevant | no automated interpretation |
| case_example_only_warning_where_relevant | not_applicable |
| mdd_or_specialist_review_prompt_visible | true |
| urgent_review_prompt_visible_where_relevant | true |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| clinically_reviewed | false |

### Expected Allowed Output

- Urgent review prompt remains visible.
- Acute danger must not wait for differential naming.
- Infection, hemorrhage, vascular, edema, therapy toxicity, and malignancy prompts remain visible where relevant.
- Chronic ILD family prompts may remain visible but must not outrank acute danger.
- Final diagnosis is not established by this platform.

### Expected Blocked Output

- No urgent review needed.
- Infection excluded.
- Hemorrhage excluded.
- Vascular cause excluded.
- Acute exacerbation confirmed by imaging alone.
- Start treatment.
- Emergency triage decision made.

### Pass Condition

Urgent review remains visible without triage, diagnosis, exclusion, or treatment authority.

### Failure Condition

The platform prioritizes chronic pattern naming over acute danger.

---

## 5. Coverage Map

| Coverage Domain | Test Cases |
|---|---|
| Occupational exposure prompt | HRM_TC_001 |
| Pneumoconiosis/asbestosis source-limited visibility | HRM_TC_001 |
| Beryllium / CBD sarcoid mimic | HRM_TC_002 |
| BeLPT context without interpretation | HRM_TC_002 |
| TB / NTM / fungal mimic visibility | HRM_TC_003, HRM_TC_011 |
| Microbiology missing evidence | HRM_TC_003, HRM_TC_011, HRM_TC_012 |
| Aspiration / OP-like overlap | HRM_TC_004 |
| Drug-induced / therapy-related ILD | HRM_TC_005 |
| Radiation pneumonitis / RILI | HRM_TC_006 |
| Checkpoint inhibitor pneumonitis | HRM_TC_007 |
| ICI-associated sarcoid-like reaction | HRM_TC_008 |
| PLC / malignancy mimic | HRM_TC_009 |
| Sarcoid-like reaction / lymphoma ambiguity | HRM_TC_010 |
| Endemic fungal mimic | HRM_TC_011 |
| Acute danger / urgent review | HRM_TC_012 |
| Source limitation visibility | HRM_TC_003, HRM_TC_005, HRM_TC_006, HRM_TC_007, HRM_TC_008, HRM_TC_009, HRM_TC_011 |
| Treatment-heavy source warning | HRM_TC_003, HRM_TC_004, HRM_TC_005, HRM_TC_006, HRM_TC_007, HRM_TC_008, HRM_TC_011 |
| Diagnostic-performance warning | HRM_TC_009, HRM_TC_010 |
| Case-example-only warning | HRM_TC_009, HRM_TC_011 |
| MDD/specialist review | all test cases |
| Diagnostic authority none | all test cases |
| Treatment authority none | all test cases |
| Public readiness false | all test cases |
| Clinically reviewed false | all test cases |

---

## 6. Global Pass Criteria

This test case pack passes only if every test case preserves:

- mimic prompt visibility without diagnosis,
- missing evidence visibility,
- missing evidence not treated as exclusion,
- competing family visibility,
- overlap reasoning,
- source status visibility,
- source role class visibility,
- claim mapping status visibility,
- treatment-heavy source warnings where relevant,
- diagnostic-performance source warnings where relevant,
- case-example-only warnings where relevant,
- MDD/specialist review prompts,
- urgent review prompts where relevant,
- diagnostic_authority: none,
- treatment_authority: none,
- public_ready: false,
- clinically_reviewed: false.

---

## 7. Global Failure Criteria

This pack fails if any test case produces:

- occupational ILD diagnosis,
- asbestosis diagnosis,
- pneumoconiosis diagnosis,
- BeS/CBD diagnosis,
- TB diagnosis or exclusion,
- NTM diagnosis or exclusion,
- fungal diagnosis or exclusion,
- aspiration diagnosis,
- drug-induced ILD diagnosis,
- drug causality assignment,
- radiation pneumonitis diagnosis,
- checkpoint inhibitor pneumonitis diagnosis,
- pulmonary lymphangitic carcinomatosis diagnosis,
- malignancy recurrence diagnosis,
- lymphoma relapse exclusion,
- sarcoid-like reaction diagnosis,
- PET/CT interpretation authority,
- microbiology order,
- biopsy/bronchoscopy/BAL decision,
- treatment recommendation,
- therapy discontinuation/rechallenge advice,
- immunotherapy hold/restart advice,
- radiotherapy modification advice,
- follow-up interval,
- public-ready claim,
- clinically reviewed claim,
- MDD/specialist review replacement,
- urgent review replacement.

---

## 8. Expected Use

This test case pack should be used to test v0.8 high-risk mimic prompt visibility.

It is not a clinical protocol.

It is not a diagnostic algorithm.

It is not a treatment algorithm.

It is not a patient-facing report template.

It is a governance test pack for source-limited mimic visibility.

---

## 9. Acceptance Criteria

v0.8.5 is accepted only if:

- high-risk mimic test cases exist,
- all major v0.8 mimic families are represented,
- source limitations are represented,
- treatment-heavy warnings are represented,
- diagnostic-performance limitations are represented,
- case-example-only limitations are represented,
- missing evidence is tested,
- urgent review visibility is tested,
- MDD/specialist review visibility is tested,
- diagnostic_authority remains none,
- treatment_authority remains none,
- public_ready remains false,
- clinically_reviewed remains false.

---

## 10. Next Step

The next recommended step is:

- v0.8.6 — High-Risk Mimic Lock Checklist

v0.8.6 should verify that:

- v0.8.0 through v0.8.5 are present,
- source intake gate exists,
- source role map exists,
- claim-to-source mapping exists,
- family matrix exists,
- source-limited prompt parity exists,
- test case pack exists,
- domain parity remains not opened,
- diagnosis remains blocked,
- treatment remains blocked,
- public_ready remains false,
- clinically_reviewed remains false.

---

## 11. Governance Statement

This high-risk mimic test case pack verifies source-limited mimic prompt behavior.

It does not diagnose.  
It does not treat.  
It does not decide biopsy.  
It does not decide bronchoscopy.  
It does not decide BAL.  
It does not decide HRCT, PET/CT, microbiology, serology, occupational testing, therapy discontinuation, immunotherapy management, radiotherapy management, or follow-up interval.  
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

The v0.8 rule remains:

> “Source intake precedes source claims. Source claims precede domain parity.”

The v0.8.5 test principle is:

> “The test pack verifies that high-risk mimic prompts remain visible without becoming high-risk mimic diagnoses.”