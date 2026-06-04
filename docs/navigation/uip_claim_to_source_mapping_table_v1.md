# ILD Reasoning Platform — UIP Claim-to-Source Mapping Table v1

Version: v0.6.R2  
Status: claim_to_source_mapping_table  
Scope: UIP parity claim-to-source backfill  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This document maps key UIP parity claims to their supporting source anchors.

It follows:

- `docs/navigation/uip_source_review_debt_register_v1.md`

This file does not create diagnostic authority.  
This file does not create treatment authority.  
This file does not create public readiness.  
This file does not make v0.6 clinically reviewed.

Its purpose is to reduce source-review debt by making claim provenance visible.

The platform principle remains:

> “It teaches clinicians to read change before naming disease.”

For source governance, the controlling rule remains:

> “A structural seal is not a clinical source-review seal.”

---

## 2. Current Source Status

| Source ID | Source | Current Status | Role |
|---|---|---|---|
| UIP_SRC_2018_ATS_ERS_JRS_ALAT_DX | Raghu et al. 2018 ATS/ERS/JRS/ALAT IPF Diagnosis Guideline | uploaded_available_targeted_review_ready | primary official diagnostic framework anchor |
| UIP_SRC_2022_ATS_ERS_JRS_ALAT_IPF_PPF | Raghu et al. 2022 ATS/ERS/JRS/ALAT IPF Update and PPF Guideline | uploaded_available_targeted_review_ready | current update and PPF anchor |
| UIP_SRC_2018_FLEISCHNER_WHITE_PAPER | Lynch et al. 2018 Fleischner Society IPF Diagnostic Criteria White Paper | uploaded_available_verified_from_previous_step | verified comparative anchor |
| UIP_SRC_2020_FLEISCHNER_ILA_POSITION_PAPER | Fleischner Society 2020 ILA Position Paper | uploaded_available_verified_from_previous_step | auxiliary ILA / early fibrotic abnormality anchor |
| UIP_SRC_2020_HP_CLINICIAN_SUMMARY | Koster et al. 2021 clinician summary of 2020 ATS/JRS/ALAT HP guideline | uploaded_available_auxiliary_mimic_anchor | HP mimic / v0.7 differential reasoning support |
| UIP_SRC_INTERNAL_V03_SUPERIMPOSED_EVENTS_CORE | Internal v0.3 Superimposed Events Core | sealed_internal_governance | overlap reasoning anchor |
| UIP_SRC_INTERNAL_V04_SOURCE_GOVERNANCE | Internal v0.4 Evidence Layer / Source Review Governance | sealed_internal_governance | source governance anchor |
| UIP_SRC_INTERNAL_V05_TEST_COVERAGE_SEAL | Internal v0.5 Test Case Coverage Seal | sealed_internal_governance | test coverage / mimic / missing evidence anchor |
| UIP_INTERNAL_V06_STRUCTURAL_CHAIN | Internal v0.6 UIP Parity Structural Chain | structurally_sealed_not_clinically_reviewed | UIP parity governance chain |

---

## 3. Review Status Legend

| Review Status | Meaning |
|---|---|
| mapped_targeted_review | Source passage or section has been identified for the claim |
| mapped_partial | Source relation is identified but needs fuller extraction or exact quotation later |
| auxiliary_mapped | Source supports a mimic, terminology, or adjacent reasoning claim but is not the primary UIP authority |
| pending_deeper_review | Claim requires further full-text or section-level review before stronger use |
| not_allowed | Claim is outside v0.6 authority and must not be used |
| internal_governance_only | Claim comes from platform governance, not external clinical authority |

---

## 4. Blocking Status Legend

| Blocking Status | Meaning |
|---|---|
| clears_structural_use | Sufficient for internal non-authoritative structural reasoning |
| blocks_clinical_reviewed | Must be resolved before any clinically_reviewed status |
| blocks_public_ready | Must remain blocked; public readiness not allowed |
| blocks_treatment_authority | Treatment use not allowed in v0.6 |
| auxiliary_only | May support context but cannot serve as primary UIP diagnostic source |

---

## 5. Claim-to-Source Mapping Table

| Claim ID | Claim Text | Source ID | Source Passage or Section | Claim Scope | Limitation | Affects File(s) | Review Status | Blocking Status |
|---|---|---|---|---|---|---|---|---|
| UIP_CLAIM_001 | UIP-facing HRCT pattern categories include UIP pattern, probable UIP pattern, indeterminate for UIP pattern, and alternative diagnosis. | UIP_SRC_2018_ATS_ERS_JRS_ALAT_DX | 2018 guideline: Results summary and HRCT Patterns section; Table 4 | Pattern category framework | This is pattern categorization, not final diagnosis. | `uip_pattern_boundary_matrix_v1.md`; `uip_reasoning_parity_rules_v1.md` | mapped_targeted_review | clears_structural_use |
| UIP_CLAIM_002 | The 2022 update retains the four HRCT categories while making minor modifications for clarity. | UIP_SRC_2022_ATS_ERS_JRS_ALAT_IPF_PPF | 2022 guideline: Radiological Features of UIP; Table 3 | Current update / source hierarchy | Does not by itself make v0.6 guideline-complete. | `uip_source_anchor_review_map_v1.md`; `uip_parity_seal_v1.md` | mapped_targeted_review | clears_structural_use |
| UIP_CLAIM_003 | UIP pattern requires subpleural and basal predominance with honeycombing, with or without traction bronchiectasis/bronchiolectasis. | UIP_SRC_2018_ATS_ERS_JRS_ALAT_DX | 2018 guideline: HRCT Patterns; Table 4 | UIP pattern boundary | Must not be converted into platform diagnosis of IPF. | `uip_pattern_boundary_matrix_v1.md` | mapped_targeted_review | clears_structural_use |
| UIP_CLAIM_004 | Probable UIP pattern includes subpleural and basal predominant reticular abnormality with peripheral traction bronchiectasis/bronchiolectasis and no honeycombing. | UIP_SRC_2018_ATS_ERS_JRS_ALAT_DX | 2018 guideline: Probable UIP pattern; Table 4 | Probable UIP boundary | Probable UIP must not auto-upgrade to UIP or IPF. | `uip_reasoning_parity_rules_v1.md`; `uip_parity_upgrade_test_case_pack_v1.md` | mapped_targeted_review | clears_structural_use |
| UIP_CLAIM_005 | Probable UIP and UIP may have similar diagnostic approach in selected clinical contexts, but the categories remain separate. | UIP_SRC_2022_ATS_ERS_JRS_ALAT_IPF_PPF | 2022 guideline: Probable UIP pattern in diagnostic approach; Figure 10 | Probable UIP pathway nuance | This does not authorize automatic diagnostic closure. | `uip_reasoning_parity_rules_v1.md`; `uip_mdd_missing_evidence_prompt_parity_v1.md` | mapped_targeted_review | clears_structural_use |
| UIP_CLAIM_006 | Indeterminate for UIP applies when fibrosis is present but HRCT does not meet UIP or probable UIP criteria and does not explicitly suggest an alternative diagnosis. | UIP_SRC_2018_ATS_ERS_JRS_ALAT_DX | 2018 guideline: Indeterminate pattern; Table 4 | Indeterminate boundary | Must preserve uncertainty and review need. | `uip_pattern_boundary_matrix_v1.md`; `uip_parity_upgrade_test_case_pack_v1.md` | mapped_targeted_review | clears_structural_use |
| UIP_CLAIM_007 | The 2022 update retains the term indeterminate for UIP for HRCT features that do not meet UIP/probable UIP and do not suggest an alternative diagnosis. | UIP_SRC_2022_ATS_ERS_JRS_ALAT_IPF_PPF | 2022 guideline: Table 3 footnote / HRCT pattern definitions | Current update confirmation | Does not resolve indeterminate cases automatically. | `uip_parity_seal_v1.md` | mapped_targeted_review | clears_structural_use |
| UIP_CLAIM_008 | Alternative diagnosis pattern includes CT features or distributions suggesting another diagnosis, such as marked mosaic attenuation, predominant GGO, nodules, consolidation, peribronchovascular/perilymphatic/upper-mid lung predominance, pleural plaques, dilated esophagus, distal clavicular erosions, lymphadenopathy, or pleural disease. | UIP_SRC_2018_ATS_ERS_JRS_ALAT_DX | 2018 guideline: Alternative diagnosis; Table 4 | Alternative pattern closure block | Alternative prompt is not diagnosis; it blocks premature UIP/IPF closure. | `uip_mimic_superimposed_process_parity_v1.md` | mapped_targeted_review | clears_structural_use |
| UIP_CLAIM_009 | The 2022 update also lists alternative diagnosis clues including distribution patterns and CT/mediastinal findings such as mosaic attenuation, three-density sign, predominant GGO, nodules, consolidation, pleural plaques, and dilated esophagus. | UIP_SRC_2022_ATS_ERS_JRS_ALAT_IPF_PPF | 2022 guideline: Table 3 | Current update support for alternative pattern prompts | Must not be used to diagnose the alternative automatically. | `uip_mimic_superimposed_process_parity_v1.md`; `uip_parity_lock_checklist_v1.md` | mapped_targeted_review | clears_structural_use |
| UIP_CLAIM_010 | IPF diagnosis requires exclusion of other known causes of ILD, including domestic/occupational exposures, CTD, and drug toxicity. | UIP_SRC_2018_ATS_ERS_JRS_ALAT_DX | 2018 guideline: Diagnostic Criteria for IPF | Known-cause exclusion | Platform may prompt missing evidence but must not confirm exclusion. | `uip_mdd_missing_evidence_prompt_parity_v1.md` | mapped_targeted_review | clears_structural_use |
| UIP_CLAIM_011 | Detailed history of medication use and environmental exposures is recommended to exclude potential causes of ILD. | UIP_SRC_2018_ATS_ERS_JRS_ALAT_DX | 2018 guideline: Question 1 recommendation | Exposure / medication context | Missing history keeps HP, occupational disease, and drug toxicity visible. | `uip_mdd_missing_evidence_prompt_parity_v1.md`; `uip_parity_upgrade_test_case_pack_v1.md` | mapped_targeted_review | clears_structural_use |
| UIP_CLAIM_012 | Serological testing is recommended to aid exclusion of CTD as a potential cause of ILD. | UIP_SRC_2018_ATS_ERS_JRS_ALAT_DX | 2018 guideline: Question 2 recommendation | Autoimmune / CTD context | Platform may show CTD context missing; it must not order tests or diagnose CTD. | `uip_mdd_missing_evidence_prompt_parity_v1.md` | mapped_targeted_review | clears_structural_use |
| UIP_CLAIM_013 | MDD is suggested for diagnostic decision-making in patients clinically suspected of IPF. | UIP_SRC_2018_ATS_ERS_JRS_ALAT_DX | 2018 guideline: Summary of Recommendations; Question 7 | MDD role | MDD prompt is review routing, not automated decision-making. | `uip_mdd_missing_evidence_prompt_parity_v1.md`; `uip_parity_seal_v1.md` | mapped_targeted_review | clears_structural_use |
| UIP_CLAIM_014 | In appropriate clinical settings, a radiological pattern of probable UIP may support IPF diagnosis after MDD without biopsy, but this remains contextual and non-automatic. | UIP_SRC_2022_ATS_ERS_JRS_ALAT_IPF_PPF | 2022 guideline: Diagnostic algorithm Figure 10 footnote | Probable UIP + MDD nuance | In platform terms, this must remain non-authoritative and not auto-diagnostic. | `uip_reasoning_parity_rules_v1.md`; `uip_mdd_missing_evidence_prompt_parity_v1.md` | mapped_targeted_review | clears_structural_use |
| UIP_CLAIM_015 | Pure or new ground-glass opacity is not a typical UIP feature and should raise acute overlay concern in the appropriate context. | UIP_SRC_2018_ATS_ERS_JRS_ALAT_DX | 2018 guideline: HRCT Features of UIP Pattern; CT findings in acute exacerbation | Acute overlay separation | Platform may trigger urgent/mimic review but must not diagnose acute exacerbation. | `uip_temporal_comparison_parity_v1.md`; `uip_mimic_superimposed_process_parity_v1.md` | mapped_targeted_review | clears_structural_use |
| UIP_CLAIM_016 | Acute exacerbation context may show bilateral GGO/consolidation on a background of fibrosis/UIP pattern. | UIP_SRC_2018_ATS_ERS_JRS_ALAT_DX | 2018 guideline: CT findings in acute exacerbation; Figure 6 | Acute superimposed modifier | Imaging alone must not confirm acute exacerbation. | `uip_temporal_comparison_parity_v1.md`; `uip_parity_upgrade_test_case_pack_v1.md` | mapped_targeted_review | clears_structural_use |
| UIP_CLAIM_017 | PPF is defined separately from IPF and is not itself a diagnosis; it is agnostic to the underlying condition. | UIP_SRC_2022_ATS_ERS_JRS_ALAT_IPF_PPF | 2022 guideline: Definition of PPF | PPF context | v0.6 may cite PPF context but cannot extend into treatment authority. | `uip_source_review_debt_register_v1.md`; future differential reasoning | mapped_targeted_review | clears_structural_use |
| UIP_CLAIM_018 | PPF requires at least two of three criteria within the past year with no alternative explanation in an ILD other than IPF: worsening symptoms, physiological progression, and radiological progression. | UIP_SRC_2022_ATS_ERS_JRS_ALAT_IPF_PPF | 2022 guideline: Definition of PPF; Table 4 | PPF progression framework | Treatment implications are not allowed in v0.6. | `uip_temporal_comparison_parity_v1.md`; future v0.7/v0.8 | mapped_targeted_review | blocks_treatment_authority |
| UIP_CLAIM_019 | Radiological progression criteria for PPF include increased traction bronchiectasis/bronchiolectasis, new GGO with traction bronchiectasis, new fine reticulation, increased/coarser reticulation, new/increased honeycombing, or lobar volume loss. | UIP_SRC_2022_ATS_ERS_JRS_ALAT_IPF_PPF | 2022 guideline: Table 4; Radiological Criteria for PPF | Feature-level progression mapping | Must not be converted into IPF progression diagnosis by platform. | `uip_temporal_comparison_parity_v1.md` | mapped_targeted_review | clears_structural_use |
| UIP_CLAIM_020 | Visual progression assessment compares initial and follow-up HRCT side by side and must account for lung volume changes. | UIP_SRC_2022_ATS_ERS_JRS_ALAT_IPF_PPF | 2022 guideline: Radiological Criteria for PPF | Temporal comparison method | Platform may encode comparison discipline but cannot clinically certify progression. | `uip_temporal_comparison_parity_v1.md` | mapped_targeted_review | clears_structural_use |
| UIP_CLAIM_021 | Follow-up HRCT may be indicated when there is clinical suspicion of worsening fibrosis, but the optimal interval is unknown. | UIP_SRC_2022_ATS_ERS_JRS_ALAT_IPF_PPF | 2022 guideline: Radiological Criteria for PPF | Follow-up uncertainty | No automated follow-up schedule or management order allowed. | `uip_temporal_comparison_parity_v1.md`; future ILA/follow-up layer | mapped_targeted_review | blocks_treatment_authority |
| UIP_CLAIM_022 | Incidental interstitial lung abnormalities are not automatically clinically significant ILD or UIP/IPF and require clinical evaluation. | UIP_SRC_2020_FLEISCHNER_ILA_POSITION_PAPER | Fleischner 2020 ILA Position Paper | ILA non-diagnostic handling | Auxiliary to v0.6; should not become primary UIP criteria. | `uip_parity_upgrade_test_case_pack_v1.md` | mapped_partial | auxiliary_only |
| UIP_CLAIM_023 | Subpleural fibrotic ILA carries progression concern and follow-up uncertainty but does not equal UIP/IPF diagnosis. | UIP_SRC_2020_FLEISCHNER_ILA_POSITION_PAPER | Fleischner 2020 ILA Position Paper | ILA progression / follow-up reasoning | Requires separate ILA parity if expanded later. | `uip_parity_upgrade_test_case_pack_v1.md`; future ILA module | mapped_partial | auxiliary_only |
| UIP_CLAIM_024 | Fleischner 2018 supports comparative framing around clinical context, probable UIP, MDD, working diagnosis, and re-review over time. | UIP_SRC_2018_FLEISCHNER_WHITE_PAPER | Lynch et al. 2018 Fleischner Society White Paper | Comparative diagnostic reasoning | Comparative anchor, not replacement for ATS official guideline. | `uip_mdd_missing_evidence_prompt_parity_v1.md`; `uip_parity_upgrade_test_case_pack_v1.md` | mapped_partial | clears_structural_use |
| UIP_CLAIM_025 | Working diagnosis must remain provisional and reviewable when evidence is incomplete or longitudinal behavior changes. | UIP_SRC_2018_FLEISCHNER_WHITE_PAPER | Lynch et al. 2018 Fleischner Society White Paper | Working diagnosis reviewability | Requires formal exact-passage extraction later before clinical review status. | `uip_mdd_missing_evidence_prompt_parity_v1.md` | mapped_partial | blocks_clinical_reviewed |
| UIP_CLAIM_026 | HP can mimic or overlap UIP-facing reasoning, especially fibrotic HP with UIP-like fibrosis and small airway disease such as mosaic attenuation, air trapping, or three-density pattern. | UIP_SRC_2020_HP_CLINICIAN_SUMMARY | Koster et al. 2021 clinician summary of 2020 HP guideline | HP mimic / v0.7 differential support | Auxiliary mimic source; not primary UIP diagnostic criteria source. | `uip_mimic_superimposed_process_parity_v1.md`; future v0.7 | auxiliary_mapped | auxiliary_only |
| UIP_CLAIM_027 | No individual history, HRCT, or histopathology feature is adequate in isolation to diagnose HP; HP diagnosis is ideally made via MDD. | UIP_SRC_2020_HP_CLINICIAN_SUMMARY | Koster et al. 2021: Diagnostic Criteria section | HP differential governance | Supports mimic humility; does not diagnose HP. | future v0.7 HP parity | auxiliary_mapped | auxiliary_only |
| UIP_CLAIM_028 | Treatment-related claims are not allowed in v0.6 UIP parity docs. | UIP_SRC_INTERNAL_V04_SOURCE_GOVERNANCE; UIP_INTERNAL_V06_STRUCTURAL_CHAIN | Internal governance | Authority boundary | Even if sources discuss treatment, v0.6 does not. | all v0.6 files | internal_governance_only | blocks_treatment_authority |
| UIP_CLAIM_029 | Public-ready claims are not allowed in v0.6. | UIP_SRC_INTERNAL_V04_SOURCE_GOVERNANCE; UIP_INTERNAL_V06_STRUCTURAL_CHAIN | Internal governance | Public readiness boundary | Structural source mapping is not clinical validation. | all v0.6 files | internal_governance_only | blocks_public_ready |
| UIP_CLAIM_030 | Diagnostic authority remains none across v0.6. | UIP_SRC_INTERNAL_V04_SOURCE_GOVERNANCE; UIP_INTERNAL_V06_STRUCTURAL_CHAIN | Internal governance | Authority boundary | Platform structures reasoning but does not diagnose. | all v0.6 files | internal_governance_only | blocks_clinical_reviewed |

---

## 6. Claim Families Cleared for Internal Structural Use

The following claim families are now sufficiently mapped for internal, non-authoritative structural use:

| Claim Family | Status |
|---|---|
| UIP HRCT category framework | mapped for internal structural use |
| UIP pattern boundary | mapped for internal structural use |
| Probable UIP boundary | mapped for internal structural use |
| Indeterminate for UIP boundary | mapped for internal structural use |
| Alternative diagnosis pattern prompts | mapped for internal structural use |
| Known-cause exclusion prompts | mapped for internal structural use |
| Exposure / medication history prompts | mapped for internal structural use |
| CTD serology / autoimmune context prompts | mapped for internal structural use |
| MDD prompt role | mapped for internal structural use |
| Acute overlay / new GGO distinction | mapped for internal structural use |
| PPF context and radiological progression framework | mapped for internal structural use |
| HP mimic auxiliary visibility | auxiliary mapped |
| ILA non-diagnostic handling | partial auxiliary mapping |

---

## 7. Claims Still Not Cleared for Clinical Review

The following remain blocked before any clinical_reviewed status:

| Blocked Claim Area | Reason |
|---|---|
| v0.6 fully reflects all ATS/ERS/JRS/ALAT guideline details | Only targeted claim mapping has been performed |
| UIP parity is clinically validated | No clinical validation performed |
| Platform diagnosis of UIP/IPF | Diagnostic authority remains none |
| Treatment recommendation for IPF or PPF | Treatment authority remains none |
| Biopsy decision automation | Clinical decision authority not allowed |
| Public-facing UIP parity | public_ready remains false |
| Patient-facing interpretation | patient_facing_use not allowed |
| Full ILA management parity | Fleischner 2020 only auxiliary in v0.6 |
| Full HP diagnostic parity | Koster 2021 only auxiliary mimic anchor in v0.6 |

---

## 8. Required Corrections to R1 Status

The v0.6.R1 debt register should now be interpreted with the following updated status:

| Source ID | R1 Status | R2 Updated Status |
|---|---|---|
| UIP_SRC_2018_ATS_ERS_JRS_ALAT_DX | referenced_anchor_pending_claim_mapping | uploaded_available_targeted_review_ready; key claims mapped in R2 |
| UIP_SRC_2022_ATS_ERS_JRS_ALAT_IPF_PPF | referenced_anchor_pending_targeted_review | uploaded_available_targeted_review_ready; key claims mapped in R2 |
| UIP_SRC_2018_FLEISCHNER_WHITE_PAPER | uploaded_and_review_usable | remains verified comparative anchor; mapping still partial |
| UIP_SRC_2020_FLEISCHNER_ILA_POSITION_PAPER | uploaded_and_review_usable | remains auxiliary ILA anchor; mapping still partial |
| UIP_SRC_2020_HP_CLINICIAN_SUMMARY | not listed in R1 | add as auxiliary HP mimic / future v0.7 differential anchor |

R1 remains valid as the debt register.

R2 partially pays down the debt.

---

## 9. R2 Status Summary

Current status after R2:

| Field | Status |
|---|---|
| v0_6_structural_seal_valid | true |
| uip_source_review | targeted_partial |
| uip_claim_mapping | partial_backfill_complete |
| ats_2018_key_claims_mapped | true |
| ats_2022_key_claims_mapped | true |
| fleischner_2018_mapping | partial_verified_comparative |
| fleischner_2020_ila_mapping | partial_auxiliary |
| hp_mimic_anchor_added | true |
| clinically_reviewed | false |
| public_ready | false |
| diagnostic_authority | none |
| treatment_authority | none |
| v0_7_entry_allowed | not_yet; requires source-status correction and backfill lock |

---

## 10. Next Required Work

The next recommended step is:

v0.6.R3 — UIP Source Status Correction / Backfill Lock

R3 should:

- update source statuses across the v0.6 documentation chain,
- register Koster 2021 as an auxiliary HP mimic / future v0.7 source,
- clarify that ATS 2018 and ATS 2022 are now uploaded and targeted-review-ready,
- state that R2 performs partial claim mapping, not clinical review,
- decide whether v0.7 entry can open after R3 or whether one more source review checkpoint is needed.

---

## 11. Governance Statement

This mapping table reduces v0.6 source-review debt.

It does not convert v0.6 into clinical review.

It does not diagnose.  
It does not treat.  
It does not decide biopsy.  
It does not confirm UIP.  
It does not confirm IPF.  
It does not exclude mimics.  
It does not confirm acute exacerbation.  
It does not claim public readiness.

The platform remains an evidence-governed clinical reasoning platform.

Current status:

- uip_parity_structural_governance: sealed
- uip_source_review: targeted_partial
- uip_claim_mapping: partial_backfill_complete
- clinically_reviewed: false
- public_ready: false
- diagnostic_authority: none
- treatment_authority: none

The next correct move is source-status correction and backfill lock, not clinical deployment.