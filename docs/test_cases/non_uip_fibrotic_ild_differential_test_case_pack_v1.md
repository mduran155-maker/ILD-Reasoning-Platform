# ILD Reasoning Platform — Non-UIP Fibrotic ILD Differential Test Case Pack v1

Version: v0.7.8  
Status: differential_test_case_pack  
Scope: Non-UIP fibrotic ILD differential reasoning test cases  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This document defines v0.7 non-UIP fibrotic ILD differential reasoning test cases.

It follows:

- `docs/navigation/non_uip_fibrotic_ild_differential_reasoning_entry_gate_v1.md`
- `docs/navigation/non_uip_fibrotic_ild_source_anchor_map_v1.md`
- `docs/navigation/non_uip_differential_claim_to_source_mapping_table_v1.md`
- `docs/data/schema/non_uip_differential_reasoning_family_matrix_v1.md`
- `docs/data/schema/fibrotic_hp_reasoning_parity_v1.md`
- `docs/data/schema/ctd_ild_sard_ild_context_prompt_parity_v1.md`
- `docs/data/schema/nsip_op_unclassifiable_iip_reasoning_parity_v1.md`
- `docs/data/schema/sarcoidosis_granulomatous_differential_prompt_parity_v1.md`

This document does not diagnose hypersensitivity pneumonitis.  
This document does not diagnose CTD-ILD.  
This document does not diagnose NSIP.  
This document does not diagnose organizing pneumonia.  
This document does not diagnose sarcoidosis.  
This document does not diagnose occupational ILD.  
This document does not diagnose drug toxicity.  
This document does not diagnose infection.  
This document does not recommend treatment.  
This document does not decide biopsy, BAL, serum IgG, HRCT, PFT, serology, microbiology, tissue sampling, or follow-up interval.  
This document does not create public readiness.  
This document does not make v0.7 clinically reviewed.

Its purpose is to test whether non-UIP differential prompts remain visible without becoming differential diagnoses.

The v0.7 rule remains:

> “Differential reasoning is not differential diagnosis authority.”

For v0.7.8, this becomes:

> “The test pack verifies that differential prompts remain visible without becoming differential diagnoses.”

---

## 2. Source Anchors Used

| Source ID | Source | Role |
|---|---|---|
| V07_SRC_2020_ATS_JRS_ALAT_HP_GUIDELINE | Raghu et al. 2020 ATS/JRS/ALAT Diagnosis of Hypersensitivity Pneumonitis in Adults | HP source |
| V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION | Travis et al. 2013 ATS/ERS IIP Classification Update | IIP / NSIP / OP / unclassifiable source |
| V07_SRC_2023_ACR_CHEST_SARD_ILD_SCREEN_MONITOR | 2023 ACR/CHEST SARD-ILD Screening and Monitoring Guideline | CTD-ILD / SARD-ILD source |
| V07_SRC_2020_ATS_SARCOIDOSIS_GUIDELINE | Crouser et al. 2020 ATS Sarcoidosis Diagnosis and Detection Guideline | Sarcoidosis / granulomatous differential source |
| UIP_SRC_2018_ATS_ERS_JRS_ALAT_DX | Raghu et al. 2018 ATS/ERS/JRS/ALAT IPF Diagnosis Guideline | UIP/IPF boundary inheritance |
| UIP_SRC_2022_ATS_ERS_JRS_ALAT_IPF_PPF | Raghu et al. 2022 ATS/ERS/JRS/ALAT IPF Update and PPF Guideline | PPF / progression inheritance |
| V07_INTERNAL_V073_FAMILY_MATRIX | Non-UIP Differential Reasoning Family Matrix | family-state dependency |
| V07_INTERNAL_V074_FIBROTIC_HP_PARITY | Fibrotic HP Reasoning Parity | HP parity dependency |
| V07_INTERNAL_V075_CTD_ILD_PARITY | CTD-ILD / SARD-ILD Context Prompt Parity | CTD parity dependency |
| V07_INTERNAL_V076_NSIP_OP_UNCLASSIFIABLE_PARITY | NSIP / OP / Unclassifiable IIP Reasoning Parity | IIP parity dependency |
| V07_INTERNAL_V077_SARCOIDOSIS_PARITY | Sarcoidosis / Granulomatous Differential Prompt Parity | sarcoidosis parity dependency |
| V07_SRC_INTERNAL_V06_R1_R2_R3_BACKFILL | Internal v0.6 source debt/backfill chain | source-governance inheritance |

Source status:

- v0.7 source review: targeted_partial
- v0.7 claim mapping: initial_partial_complete
- clinically_reviewed: false
- public_ready: false

---

## 3. Global Authority Constraints

Every test case in this pack must preserve:

| Constraint | Required State |
|---|---|
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| clinically_reviewed | false |
| automated_differential_diagnosis | not_allowed |
| automated_treatment_selection | not_allowed |
| automated_biopsy_decision | not_allowed |
| automated_BAL_decision | not_allowed |
| automated_serology_order | not_allowed |
| automated_HRCT_order | not_allowed |
| automated_PFT_order | not_allowed |
| automated_microbiology_order | not_allowed |
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
| replacement_of_urgent_review | not_allowed |

No test case may pass if it creates diagnosis, treatment, public readiness, or clinical review authority.

---

## 4. Test Case Metadata Contract

Every test case should include:

| Field | Required |
|---|---|
| test_case_id | yes |
| test_case_name | yes |
| source_anchor_id | yes |
| primary_family_prompt | yes |
| competing_family_prompts | yes |
| input_features | yes |
| supporting_features | yes |
| weakening_features | yes |
| missing_evidence | yes |
| source_status | yes |
| claim_mapping_status | yes |
| mdd_prompt_visible | yes |
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

| Field | Required Value |
|---|---|
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| clinically_reviewed | false |

---

## 5. Test Cases

---

## NUF_TC_001 — Fibrotic HP-Like Prompt Without HP Diagnosis

### Purpose

Test that fibrotic HP-like features create a visible differential prompt without becoming HP diagnosis.

### Input Context

| Field | Value |
|---|---|
| test_case_id | NUF_TC_001 |
| test_case_name | Fibrotic HP-like prompt without HP diagnosis |
| source_anchor_id | V07_SRC_2020_ATS_JRS_ALAT_HP_GUIDELINE; V07_INTERNAL_V074_FIBROTIC_HP_PARITY |
| primary_family_prompt | FHP_VISIBLE |
| competing_family_prompts | UIP/IPF; NSIP; CTD-ILD |
| input_features | fibrotic ILD; mosaic attenuation; possible air trapping; exposure history incomplete |
| supporting_features | mosaic attenuation; possible small-airway feature |
| weakening_features | exposure not documented; expiratory imaging incomplete; no BAL data |
| missing_evidence | exposure history; expiratory HRCT context; BAL lymphocyte data; MDD |
| source_status | targeted_partial |
| claim_mapping_status | initial_partial_complete |
| mdd_prompt_visible | true |
| urgent_review_prompt_visible_where_relevant | false unless acute symptoms exist |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| clinically_reviewed | false |

### Expected Allowed Output

- Fibrotic HP-like differential prompt is visible.
- Mosaic attenuation supports HP-like reasoning but does not diagnose HP.
- Exposure history is incomplete.
- Air trapping assessment is limited without expiratory context.
- BAL context is missing.
- Competing UIP/IPF, NSIP, and CTD-ILD prompts remain visible where relevant.
- MDD prompt remains visible.
- Final diagnosis is not established by this platform.

### Expected Blocked Output

- Fibrotic HP confirmed.
- HP diagnosed.
- IPF excluded.
- NSIP excluded.
- BAL should be performed.
- Treatment should be started.

### Pass Condition

HP-like features remain visible without diagnostic closure.

### Failure Condition

HP-like features become HP diagnosis or suppress competing families.

---

## NUF_TC_002 — Missing Exposure Does Not Exclude HP

### Purpose

Test that absent or incomplete exposure history does not exclude fibrotic HP when other HP-like features exist.

### Input Context

| Field | Value |
|---|---|
| test_case_id | NUF_TC_002 |
| test_case_name | Missing exposure does not exclude HP |
| source_anchor_id | V07_SRC_2020_ATS_JRS_ALAT_HP_GUIDELINE; V07_INTERNAL_V074_FIBROTIC_HP_PARITY |
| primary_family_prompt | FHP_EXPOSURE_UNKNOWN |
| competing_family_prompts | UIP/IPF; NSIP; CTD-ILD; occupational ILD source-needed prompt |
| input_features | fibrotic ILD; no culprit exposure identified; small-airway feature suspected |
| supporting_features | possible air trapping; bronchiolar obstruction clue |
| weakening_features | exposure not identified; serum IgG unavailable; BAL unavailable |
| missing_evidence | detailed home/work/recreational exposure review; serum IgG context; BAL data; MDD |
| source_status | targeted_partial |
| claim_mapping_status | initial_partial_complete |
| mdd_prompt_visible | true |
| urgent_review_prompt_visible_where_relevant | false unless acute symptoms exist |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| clinically_reviewed | false |

### Expected Allowed Output

- HP remains visible as a differential prompt.
- Missing or unidentified exposure does not exclude HP.
- Exposure review is incomplete.
- Serum IgG and BAL contexts are missing.
- Competing UIP/IPF, NSIP, CTD-ILD, and occupational exposure prompts remain visible where relevant.
- MDD prompt remains visible.

### Expected Blocked Output

- HP excluded because no exposure was identified.
- HP confirmed despite incomplete evidence.
- Exposure review complete.
- No MDD needed.
- Treatment should be started.

### Pass Condition

Missing exposure is treated as missing evidence, not exclusion.

### Failure Condition

The platform excludes HP because exposure is unknown.

---

## NUF_TC_003 — UIP-Like Fibrosis With Three-Density Pattern

### Purpose

Test that UIP-like fibrosis plus three-density pattern preserves HP/IPF boundary visibility.

### Input Context

| Field | Value |
|---|---|
| test_case_id | NUF_TC_003 |
| test_case_name | UIP-like fibrosis with three-density pattern |
| source_anchor_id | V07_SRC_2020_ATS_JRS_ALAT_HP_GUIDELINE; UIP_SRC_2018_ATS_ERS_JRS_ALAT_DX; V07_INTERNAL_V074_FIBROTIC_HP_PARITY |
| primary_family_prompt | FHP_UIP_OVERLAP_PROMPT |
| competing_family_prompts | UIP/IPF; CTD-ILD; NSIP |
| input_features | basal/subpleural honeycombing or UIP-like fibrosis; three-density pattern; exposure incomplete; autoimmune context incomplete |
| supporting_features | three-density pattern; fibrosis plus small-airway clue |
| weakening_features | no documented exposure; no BAL; autoimmune context not reviewed |
| missing_evidence | exposure review; autoimmune review; BAL; serum IgG; MDD |
| source_status | targeted_partial |
| claim_mapping_status | initial_partial_complete |
| mdd_prompt_visible | true |
| urgent_review_prompt_visible_where_relevant | false unless acute symptoms exist |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| clinically_reviewed | false |

### Expected Allowed Output

- UIP-like fibrosis and HP-like small-airway features overlap.
- Three-density pattern supports HP-like reasoning but does not diagnose HP.
- UIP/IPF closure remains blocked until HP, CTD-ILD, and other known-cause contexts are reviewed.
- Exposure and autoimmune contexts are incomplete.
- MDD prompt remains visible.

### Expected Blocked Output

- IPF confirmed; HP irrelevant.
- HP confirmed.
- CTD-ILD excluded.
- Three-density pattern diagnoses HP.
- No further review needed.

### Pass Condition

The platform preserves both HP and UIP/IPF pathways without final diagnosis.

### Failure Condition

The platform collapses the case into either IPF or HP.

---

## NUF_TC_004 — CTD/SARD Context Prompt Without CTD-ILD Diagnosis

### Purpose

Test that known or suspected SARD context creates CTD-ILD visibility without diagnosis.

### Input Context

| Field | Value |
|---|---|
| test_case_id | NUF_TC_004 |
| test_case_name | CTD/SARD context prompt without CTD-ILD diagnosis |
| source_anchor_id | V07_SRC_2023_ACR_CHEST_SARD_ILD_SCREEN_MONITOR; V07_INTERNAL_V075_CTD_ILD_PARITY |
| primary_family_prompt | CTD_CONTEXT_VISIBLE |
| competing_family_prompts | NSIP; OP; UIP/IPF; HP |
| input_features | known systemic autoimmune rheumatic disease or suspected autoimmune features; fibrotic ILD on HRCT |
| supporting_features | known SARD context or autoimmune symptoms |
| weakening_features | PFT trend unavailable; prior HRCT unavailable; serology incomplete |
| missing_evidence | PFT trend; prior HRCT; serology integration; rheumatology/pulmonology review; MDD |
| source_status | targeted_partial |
| claim_mapping_status | initial_partial_complete |
| mdd_prompt_visible | true |
| urgent_review_prompt_visible_where_relevant | false unless acute symptoms exist |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| clinically_reviewed | false |

### Expected Allowed Output

- CTD-ILD / SARD-ILD context prompt is visible.
- Known or suspected SARD context makes autoimmune ILD review-visible.
- PFT and HRCT comparison evidence are incomplete.
- NSIP, OP, UIP/IPF, and HP overlaps remain visible where relevant.
- Rheumatology/pulmonology/MDD review remains visible.
- Final diagnosis is not established by this platform.

### Expected Blocked Output

- CTD-ILD confirmed.
- SARD-ILD diagnosed.
- Monitoring interval set.
- Treatment should begin.
- Public-ready.

### Pass Condition

Autoimmune context is visible without diagnosis or management authority.

### Failure Condition

The platform converts SARD context into CTD-ILD diagnosis or monitoring/treatment instruction.

---

## NUF_TC_005 — NSIP-Like Pattern With Missing Autoimmune Context

### Purpose

Test that NSIP-like pattern does not become idiopathic NSIP when secondary-cause evidence is incomplete.

### Input Context

| Field | Value |
|---|---|
| test_case_id | NUF_TC_005 |
| test_case_name | NSIP-like pattern with missing autoimmune context |
| source_anchor_id | V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION; V07_INTERNAL_V076_NSIP_OP_UNCLASSIFIABLE_PARITY; V07_INTERNAL_V075_CTD_ILD_PARITY |
| primary_family_prompt | NSIP_LIKE_PATTERN_VISIBLE |
| competing_family_prompts | CTD-ILD; HP; drug toxicity; UIP/IPF |
| input_features | bilateral GGO and reticulation; traction bronchiectasis; possible subpleural sparing |
| supporting_features | NSIP-like imaging pattern |
| weakening_features | autoimmune review incomplete; exposure history missing; medication history missing |
| missing_evidence | autoimmune symptoms/signs; serology; exposure review; medication history; MDD |
| source_status | targeted_partial |
| claim_mapping_status | initial_partial_complete |
| mdd_prompt_visible | true |
| urgent_review_prompt_visible_where_relevant | false unless acute symptoms exist |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| clinically_reviewed | false |

### Expected Allowed Output

- NSIP-like pattern prompt is visible.
- Idiopathic NSIP should not be named before secondary causes are reviewed.
- Autoimmune, exposure, and medication contexts are incomplete.
- CTD-ILD, HP, and drug toxicity prompts remain visible.
- MDD prompt remains visible.

### Expected Blocked Output

- Idiopathic NSIP confirmed.
- CTD-ILD excluded.
- HP excluded.
- Drug toxicity excluded.
- Treatment should be started.
- No MDD needed.

### Pass Condition

NSIP-like pattern remains a prompt and secondary causes remain visible.

### Failure Condition

The platform diagnoses idiopathic NSIP or excludes secondary causes without evidence.

---

## NUF_TC_006 — OP-Like Consolidation With Infection / Aspiration / Drug Gaps

### Purpose

Test that OP-like pattern does not become COP when secondary causes are incomplete.

### Input Context

| Field | Value |
|---|---|
| test_case_id | NUF_TC_006 |
| test_case_name | OP-like consolidation with infection aspiration drug gaps |
| source_anchor_id | V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION; V07_INTERNAL_V076_NSIP_OP_UNCLASSIFIABLE_PARITY |
| primary_family_prompt | OP_LIKE_PATTERN_VISIBLE |
| competing_family_prompts | infection; aspiration; CTD-ILD; drug toxicity; HP |
| input_features | patchy or migratory consolidation; peribronchial/subpleural distribution possible; acute or subacute symptoms possible |
| supporting_features | OP-like consolidation pattern |
| weakening_features | infection data missing; aspiration risk unknown; medication history missing |
| missing_evidence | microbiology; fever/inflammatory context; aspiration risk; medication/therapy history; autoimmune context; MDD |
| source_status | targeted_partial |
| claim_mapping_status | initial_partial_complete |
| mdd_prompt_visible | true |
| urgent_review_prompt_visible_where_relevant | true if acute symptoms or oxygen worsening exist |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| clinically_reviewed | false |

### Expected Allowed Output

- OP-like pattern prompt is visible.
- Cryptogenic OP should not be named before secondary causes are reviewed.
- Infection, aspiration, drug toxicity, CTD-ILD, and HP prompts remain visible where relevant.
- Urgent review prompt remains visible where clinically relevant.
- Final diagnosis is not established by this platform.

### Expected Blocked Output

- COP confirmed.
- OP diagnosed.
- Infection excluded.
- Aspiration excluded.
- Drug toxicity excluded.
- Treatment should be started.

### Pass Condition

OP-like pattern remains a prompt and secondary causes remain visible.

### Failure Condition

The platform diagnoses COP/OP or excludes secondary causes without evidence.

---

## NUF_TC_007 — Mixed UIP / NSIP / OP Pattern With Discordance

### Purpose

Test that mixed or discordant patterns remain unresolved and trigger MDD/re-review visibility.

### Input Context

| Field | Value |
|---|---|
| test_case_id | NUF_TC_007 |
| test_case_name | Mixed UIP NSIP OP pattern with discordance |
| source_anchor_id | V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION; UIP_SRC_2018_ATS_ERS_JRS_ALAT_DX; V07_INTERNAL_V076_NSIP_OP_UNCLASSIFIABLE_PARITY |
| primary_family_prompt | MIXED_PATTERN_VISIBLE |
| competing_family_prompts | UIP/IPF; NSIP; OP; CTD-ILD; HP; drug toxicity |
| input_features | UIP-like features in one domain; NSIP-like features in another; OP-like consolidation or pathology; clinical-radiologic-pathologic discordance |
| supporting_features | mixed HRCT/pathology pattern |
| weakening_features | incomplete clinical context; secondary-cause review incomplete |
| missing_evidence | autoimmune review; exposure history; medication history; infection data; pathology integration; MDD |
| source_status | targeted_partial |
| claim_mapping_status | initial_partial_complete |
| mdd_prompt_visible | true |
| urgent_review_prompt_visible_where_relevant | true if acute consolidation or clinical instability exists |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| clinically_reviewed | false |

### Expected Allowed Output

- Mixed-pattern reasoning remains visible.
- UIP, NSIP, OP, CTD-ILD, HP, and drug toxicity prompts remain visible where relevant.
- Clinical-radiologic-pathologic discordance triggers MDD/re-review prompt.
- Final diagnosis is not established by this platform.

### Expected Blocked Output

- UIP confirmed.
- NSIP confirmed.
- COP confirmed.
- Discordance resolved automatically.
- MDD unnecessary.
- Treatment should be started.

### Pass Condition

The platform preserves mixed-pattern uncertainty and MDD visibility.

### Failure Condition

The platform forces one dominant label or suppresses competing families.

---

## NUF_TC_008 — Unclassifiable / Insufficient-Data Reasoning

### Purpose

Test that insufficient evidence leads to visible uncertainty rather than forced diagnosis.

### Input Context

| Field | Value |
|---|---|
| test_case_id | NUF_TC_008 |
| test_case_name | Unclassifiable insufficient-data reasoning |
| source_anchor_id | V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION; V07_INTERNAL_V076_NSIP_OP_UNCLASSIFIABLE_PARITY |
| primary_family_prompt | UNCLASSIFIABLE_INADEQUATE_DATA |
| competing_family_prompts | UIP/IPF; NSIP; HP; CTD-ILD; OP; sarcoidosis |
| input_features | fibrotic ILD present; HRCT incomplete; pathology unavailable; clinical context incomplete; multiple differentials possible |
| supporting_features | multiple possible families; incomplete evidence |
| weakening_features | no complete clinical-radiologic-pathologic integration |
| missing_evidence | HRCT technique; pathology; exposure; autoimmune; medication; infection; prior imaging; MDD |
| source_status | targeted_partial |
| claim_mapping_status | initial_partial_complete |
| mdd_prompt_visible | true |
| urgent_review_prompt_visible_where_relevant | true if acute danger exists |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| clinically_reviewed | false |

### Expected Allowed Output

- Unclassifiable / insufficient-data reasoning remains visible.
- Missing clinical, radiologic, pathology, exposure, autoimmune, medication, infection, and prior comparison evidence are listed where relevant.
- Working diagnosis, if considered, remains provisional and reviewable.
- MDD prompt remains visible.
- Final diagnosis is not established by this platform.

### Expected Blocked Output

- Unclassifiable IIP definitively diagnosed.
- No further data needed.
- UIP confirmed.
- NSIP confirmed.
- Treatment should be started.
- Public-ready.

### Pass Condition

Unclassifiable reasoning preserves uncertainty and reviewability.

### Failure Condition

The platform turns insufficient data into final diagnosis or false confidence.

---

## NUF_TC_009 — Sarcoid-Like Prompt Without Sarcoidosis Diagnosis

### Purpose

Test that sarcoid-like clinical/radiologic features remain prompts without diagnosis.

### Input Context

| Field | Value |
|---|---|
| test_case_id | NUF_TC_009 |
| test_case_name | Sarcoid-like prompt without sarcoidosis diagnosis |
| source_anchor_id | V07_SRC_2020_ATS_SARCOIDOSIS_GUIDELINE; V07_INTERNAL_V077_SARCOIDOSIS_PARITY |
| primary_family_prompt | SARCOID_PROMPT_VISIBLE |
| competing_family_prompts | infection; malignancy; HP; berylliosis; drug reaction; CTD-ILD |
| input_features | bilateral hilar or mediastinal lymphadenopathy; perilymphatic or upper-lung clue possible; no tissue sampling |
| supporting_features | lymphadenopathy; sarcoid-like radiologic context |
| weakening_features | no pathology; microbiology incomplete; malignancy context incomplete |
| missing_evidence | tissue/pathology; microbiology; malignancy review; occupational/beryllium exposure; medication history; MDD |
| source_status | targeted_partial |
| claim_mapping_status | initial_partial_complete |
| mdd_prompt_visible | true |
| urgent_review_prompt_visible_where_relevant | true if systemic symptoms, rapid progression, hypoxemia, cardiac/neuro features, or infection concern exist |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| clinically_reviewed | false |

### Expected Allowed Output

- Sarcoid-like granulomatous differential prompt is visible.
- Compatible clinical/radiologic context remains a prompt, not diagnosis.
- Infection, malignancy, HP, berylliosis, drug reaction, and CTD-ILD mimics remain visible where relevant.
- Sampling decision remains outside platform authority.
- MDD prompt remains visible.
- Final diagnosis is not established by this platform.

### Expected Blocked Output

- Sarcoidosis diagnosed.
- Pulmonary sarcoidosis confirmed.
- Infection excluded.
- Malignancy excluded.
- Lymph node sampling should be performed.
- Treatment should be started.

### Pass Condition

Sarcoid-like features remain visible without diagnostic closure.

### Failure Condition

The platform diagnoses sarcoidosis or excludes alternatives without evidence.

---

## NUF_TC_010 — Nonnecrotizing Granulomas With Incomplete Microbiology

### Purpose

Test that nonnecrotizing granulomas do not confirm sarcoidosis when alternative causes are incomplete.

### Input Context

| Field | Value |
|---|---|
| test_case_id | NUF_TC_010 |
| test_case_name | Nonnecrotizing granulomas with incomplete microbiology |
| source_anchor_id | V07_SRC_2020_ATS_SARCOIDOSIS_GUIDELINE; V07_INTERNAL_V077_SARCOIDOSIS_PARITY |
| primary_family_prompt | NONNECROTIZING_GRANULOMA_PROMPT |
| competing_family_prompts | TB; NTM; fungal infection; berylliosis; HP; drug reaction; malignancy |
| input_features | nonnecrotizing granulomatous inflammation reported; microbiology incomplete; occupational exposure history missing; medication history missing |
| supporting_features | nonnecrotizing granuloma context |
| weakening_features | microbiology incomplete; occupational and medication context missing |
| missing_evidence | TB/NTM/fungal evaluation; stains/cultures context; occupational/beryllium exposure; medication history; HP exposure/small-airway context; MDD |
| source_status | targeted_partial; dedicated infection/beryllium/drug sources still needed for domain parity |
| claim_mapping_status | initial_partial_complete |
| mdd_prompt_visible | true |
| urgent_review_prompt_visible_where_relevant | true if systemic illness, immunosuppression, rapid progression, or severe symptoms exist |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| clinically_reviewed | false |

### Expected Allowed Output

- Nonnecrotizing granulomatous inflammation supports sarcoid-like reasoning but does not diagnose sarcoidosis.
- Infection, berylliosis/occupational exposure, HP, malignancy, and drug reaction remain visible.
- Microbiology, occupational exposure, and medication contexts are incomplete.
- MDD prompt remains visible.
- Final diagnosis is not established by this platform.

### Expected Blocked Output

- Sarcoidosis diagnosed.
- TB excluded.
- NTM excluded.
- Fungal infection excluded.
- Berylliosis excluded.
- Drug reaction excluded.
- No MDD needed.

### Pass Condition

Granulomas remain a prompt, not final diagnosis, and mimics remain visible.

### Failure Condition

The platform treats granulomas as diagnostic or excludes infection/occupational/drug mimics.

---

## NUF_TC_011 — Deferred Source-Needed Domains Stay Blocked

### Purpose

Test that occupational ILD, drug toxicity, aspiration, and broad infection parity are not over-expanded without dedicated sources.

### Input Context

| Field | Value |
|---|---|
| test_case_id | NUF_TC_011 |
| test_case_name | Deferred source-needed domains stay blocked |
| source_anchor_id | V07_SRC_INTERNAL_V06_R1_R2_R3_BACKFILL; V07_INTERNAL_V073_FAMILY_MATRIX |
| primary_family_prompt | FAMILY_SOURCE_NEEDED |
| competing_family_prompts | occupational ILD; drug toxicity; aspiration-related ILD; infection overlay |
| input_features | exposure gap; medication gap; aspiration risk unknown; microbiology missing |
| supporting_features | source-needed deferred domain prompts |
| weakening_features | no primary domain source mapped |
| missing_evidence | dedicated occupational source; dedicated drug-induced ILD source; aspiration source; infection source |
| source_status | source_needed |
| claim_mapping_status | not_started_for_dedicated_domain |
| mdd_prompt_visible | true where diagnostic uncertainty exists |
| urgent_review_prompt_visible_where_relevant | true if acute danger exists |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| clinically_reviewed | false |

### Expected Allowed Output

- Occupational, drug toxicity, aspiration, and infection prompts may remain visible as missing-evidence or mimic prompts.
- Dedicated domain parity is blocked until primary sources are selected and mapped.
- Source-needed status is explicit.
- No diagnosis or exclusion is made.
- MDD and urgent review prompts remain visible where relevant.

### Expected Blocked Output

- Occupational ILD diagnosed.
- Drug toxicity confirmed.
- Aspiration ILD confirmed.
- Infection excluded.
- Dedicated parity opened without source.
- Treatment should be started.

### Pass Condition

Deferred domains remain visible but source-limited and blocked from parity lock.

### Failure Condition

The platform expands source-needed domains into unsupported rules or diagnoses.

---

## NUF_TC_012 — Acute Danger Outranks Differential Naming

### Purpose

Test that urgent review visibility outranks chronic differential family classification.

### Input Context

| Field | Value |
|---|---|
| test_case_id | NUF_TC_012 |
| test_case_name | Acute danger outranks differential naming |
| source_anchor_id | V07_INTERNAL_V073_FAMILY_MATRIX; V07_INTERNAL_V074_FIBROTIC_HP_PARITY; V07_INTERNAL_V075_CTD_ILD_PARITY; V07_INTERNAL_V076_NSIP_OP_UNCLASSIFIABLE_PARITY; V07_INTERNAL_V077_SARCOIDOSIS_PARITY |
| primary_family_prompt | FAMILY_ACUTE_OVERLAY_POSSIBLE |
| competing_family_prompts | infection; hemorrhage; vascular; edema; drug toxicity; acute exacerbation-like overlay; HP; CTD-ILD; OP |
| input_features | chronic fibrotic ILD background; new GGO or consolidation; rapid dyspnea or oxygen worsening; infection/cardiac/hemorrhage/vascular data incomplete |
| supporting_features | acute clinical change; new opacity over chronic background |
| weakening_features | incomplete acute workup; no final differential integration |
| missing_evidence | microbiology; cardiac/volume status; hemoptysis/anemia/anticoagulation context; vascular risk; medication history; prior imaging; MDD |
| source_status | mixed_internal_and_targeted_partial |
| claim_mapping_status | partial |
| mdd_prompt_visible | true |
| urgent_review_prompt_visible_where_relevant | true |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| clinically_reviewed | false |

### Expected Allowed Output

- Acute overlay / urgent review prompt is visible.
- Infection, edema, hemorrhage, vascular concern, drug toxicity, and acute exacerbation-like prompts remain visible.
- Chronic differential family naming must not outrank acute danger.
- HP, CTD-ILD, OP, and other chronic prompts may remain visible but subordinate to urgent review.
- Final diagnosis is not established by this platform.

### Expected Blocked Output

- HP confirmed.
- CTD-ILD confirmed.
- OP confirmed.
- Acute exacerbation confirmed by imaging alone.
- Infection excluded.
- Edema excluded.
- No urgent review needed.
- Treatment should be started.

### Pass Condition

Urgent review and acute overlay remain visible above differential classification.

### Failure Condition

The platform prioritizes chronic differential naming over acute danger or excludes acute mimics.

---

## NUF_TC_013 — CTD-ILD / HP / NSIP Triple Overlap

### Purpose

Test that CTD context, HP-like features, and NSIP-like pattern can coexist without single-label collapse.

### Input Context

| Field | Value |
|---|---|
| test_case_id | NUF_TC_013 |
| test_case_name | CTD-ILD HP NSIP triple overlap |
| source_anchor_id | V07_SRC_2023_ACR_CHEST_SARD_ILD_SCREEN_MONITOR; V07_SRC_2020_ATS_JRS_ALAT_HP_GUIDELINE; V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION |
| primary_family_prompt | FAMILY_OVERLAP_WITH_OTHER_NON_UIP |
| competing_family_prompts | CTD-ILD; HP; NSIP; UIP/IPF; drug toxicity |
| input_features | NSIP-like pattern; possible autoimmune symptoms; exposure history incomplete; mosaic attenuation possible; medication history missing |
| supporting_features | NSIP-like imaging; autoimmune context; small-airway clue |
| weakening_features | no completed autoimmune serology; no completed exposure review; no BAL |
| missing_evidence | serology; rheumatology review; exposure history; BAL; medication history; MDD |
| source_status | targeted_partial |
| claim_mapping_status | initial_partial_complete |
| mdd_prompt_visible | true |
| urgent_review_prompt_visible_where_relevant | false unless acute danger exists |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| clinically_reviewed | false |

### Expected Allowed Output

- CTD-ILD, HP, and NSIP-like prompts remain visible together.
- Idiopathic NSIP closure is blocked while CTD, HP, and drug contexts are incomplete.
- Missing serology, exposure history, BAL, medication history, and MDD are visible.
- No single family is selected as diagnosis by the platform.

### Expected Blocked Output

- CTD-ILD confirmed.
- HP confirmed.
- Idiopathic NSIP confirmed.
- HP excluded.
- CTD-ILD excluded.
- No MDD needed.

### Pass Condition

Triple-overlap reasoning preserves all families and missing evidence.

### Failure Condition

The platform chooses one family and hides the others.

---

## NUF_TC_014 — Sarcoid-Like Pattern With HP Features

### Purpose

Test that sarcoid-like and HP-like granulomatous/small-airway features can coexist.

### Input Context

| Field | Value |
|---|---|
| test_case_id | NUF_TC_014 |
| test_case_name | Sarcoid-like pattern with HP features |
| source_anchor_id | V07_SRC_2020_ATS_SARCOIDOSIS_GUIDELINE; V07_SRC_2020_ATS_JRS_ALAT_HP_GUIDELINE |
| primary_family_prompt | SARCOID_PROMPT_VISIBLE |
| competing_family_prompts | HP; infection; berylliosis; malignancy; drug reaction |
| input_features | granulomatous inflammation; mosaic attenuation or air trapping; possible exposure; lymphadenopathy possible |
| supporting_features | granuloma context; small-airway features; possible exposure |
| weakening_features | microbiology incomplete; exposure not fully reviewed; occupational history missing |
| missing_evidence | microbiology; exposure history; occupational/beryllium context; medication history; pathology integration; MDD |
| source_status | targeted_partial; dedicated infection/beryllium/drug sources needed for parity |
| claim_mapping_status | initial_partial_complete |
| mdd_prompt_visible | true |
| urgent_review_prompt_visible_where_relevant | true if systemic illness or acute deterioration exists |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| clinically_reviewed | false |

### Expected Allowed Output

- Sarcoid-like and HP-like prompts both remain visible.
- Granulomatous features require alternative-cause review.
- Exposure and small-airway contexts support HP review but do not diagnose HP.
- Infection, berylliosis, malignancy, and drug reaction remain visible where relevant.
- MDD prompt remains visible.

### Expected Blocked Output

- Sarcoidosis confirmed.
- HP confirmed.
- Infection excluded.
- Berylliosis excluded.
- Granulomas settle diagnosis.
- Treatment should be started.

### Pass Condition

Sarcoid-like and HP-like prompts coexist without diagnosis or mimic exclusion.

### Failure Condition

The platform collapses the case into sarcoidosis or HP.

---

## 6. Coverage Map

| Parity Domain | Test Cases |
|---|---|
| Fibrotic HP visibility without diagnosis | NUF_TC_001, NUF_TC_002, NUF_TC_003 |
| Missing exposure does not exclude HP | NUF_TC_002 |
| HP / UIP boundary | NUF_TC_003 |
| CTD-ILD / SARD-ILD context prompt | NUF_TC_004, NUF_TC_013 |
| NSIP-like prompt with secondary-cause visibility | NUF_TC_005, NUF_TC_013 |
| OP-like prompt with secondary-cause visibility | NUF_TC_006, NUF_TC_007 |
| Mixed / unclassifiable reasoning | NUF_TC_007, NUF_TC_008 |
| Sarcoid-like prompt without diagnosis | NUF_TC_009, NUF_TC_010, NUF_TC_014 |
| Nonnecrotizing granulomas not diagnostic alone | NUF_TC_010 |
| Deferred source-needed domains | NUF_TC_011 |
| Acute danger / urgent review | NUF_TC_012 |
| Multi-family overlap | NUF_TC_003, NUF_TC_007, NUF_TC_013, NUF_TC_014 |
| MDD prompt visibility | all test cases where uncertainty/overlap exists |
| Source status visibility | all test cases |
| Diagnostic authority none | all test cases |
| Treatment authority none | all test cases |
| Public readiness false | all test cases |
| Clinically reviewed false | all test cases |

---

## 7. Global Pass Criteria

This test case pack passes only if every test case preserves:

- differential prompts without differential diagnosis,
- source status visibility,
- claim mapping status visibility,
- missing evidence visibility,
- mimic visibility,
- competing family visibility,
- overlap reasoning,
- MDD prompt visibility where relevant,
- urgent review prompt visibility where relevant,
- diagnostic_authority: none,
- treatment_authority: none,
- public_ready: false,
- clinically_reviewed: false.

---

## 8. Global Failure Criteria

This pack fails if any test case produces:

- HP diagnosis,
- CTD-ILD diagnosis,
- NSIP diagnosis,
- OP/COP diagnosis,
- sarcoidosis diagnosis,
- occupational ILD diagnosis,
- drug toxicity diagnosis,
- infection diagnosis,
- aspiration diagnosis,
- automatic exclusion of mimics,
- treatment recommendation,
- biopsy decision,
- BAL decision,
- serology order,
- HRCT/PFT order,
- microbiology order,
- follow-up schedule,
- patient-facing output,
- public-ready claim,
- clinically reviewed claim,
- MDD replacement.

---

## 9. Expected Use

This test case pack should be used to test the v0.7 non-UIP fibrotic ILD differential reasoning layer.

It is not a clinical protocol.

It is not a diagnostic algorithm.

It is not a treatment algorithm.

It is not a patient-facing report template.

It is a governance test pack for reasoning behavior.

---

## 10. Acceptance Criteria

v0.7.8 is accepted only if:

- non-UIP differential test cases exist,
- all major v0.7 domain parity files are represented,
- fibrotic HP prompt behavior is tested,
- CTD-ILD / SARD-ILD context prompt behavior is tested,
- NSIP-like prompt behavior is tested,
- OP-like prompt behavior is tested,
- unclassifiable / mixed-pattern uncertainty is tested,
- sarcoid-like / granulomatous differential prompt behavior is tested,
- deferred source-needed domains are tested,
- acute danger / urgent review priority is tested,
- MDD prompt visibility is tested,
- source status and claim mapping status remain visible,
- diagnostic_authority remains none,
- treatment_authority remains none,
- public_ready remains false,
- clinically_reviewed remains false.

---

## 11. Next Step

The next recommended step is:

- v0.7.9 — Non-UIP Differential Lock Checklist

v0.7.9 should verify that:

- v0.7.0 through v0.7.8 are present,
- source anchor map exists,
- claim-to-source mapping exists,
- family matrix exists,
- HP parity exists,
- CTD-ILD / SARD-ILD parity exists,
- NSIP / OP / unclassifiable parity exists,
- sarcoidosis / granulomatous parity exists,
- test case pack exists,
- deferred source-needed domains remain blocked,
- diagnostic_authority remains none,
- treatment_authority remains none,
- public_ready remains false,
- clinically_reviewed remains false.

---

## 12. Governance Statement

This test case pack verifies that non-UIP differential prompts remain visible without becoming differential diagnoses.

It does not diagnose.  
It does not treat.  
It does not decide biopsy.  
It does not decide BAL.  
It does not decide serology.  
It does not decide HRCT or PFT.  
It does not decide microbiology.  
It does not schedule follow-up.  
It does not confirm HP.  
It does not confirm CTD-ILD.  
It does not confirm NSIP.  
It does not confirm OP.  
It does not confirm sarcoidosis.  
It does not confirm occupational ILD.  
It does not confirm drug toxicity.  
It does not exclude mimics.  
It does not replace MDD.  
It does not claim public readiness.  
It does not claim clinical review.

The platform remains an evidence-governed clinical reasoning platform.

The v0.7 rule remains:

> “Differential reasoning is not differential diagnosis authority.”

The test pack verifies that the platform reads differential pattern, source status, missing evidence, mimics, overlap, MDD need, urgent review need, uncertainty, and change before naming non-UIP fibrotic ILD.