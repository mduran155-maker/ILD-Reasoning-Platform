# ILD Reasoning Platform — High-Risk Mimic Claim-to-Source Mapping Table v1

Version: v0.8.2  
Status: claim_to_source_mapping_table  
Scope: High-risk mimic non-authoritative claim mapping after v0.8.1 source role map  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This document maps initial v0.8 high-risk mimic claims to source anchors.

It follows:

- `docs/navigation/deferred_source_expansion_high_risk_mimic_source_intake_entry_gate_v1.md`
- `docs/navigation/high_risk_mimic_source_role_map_v1.md`
- `docs/navigation/non_uip_fibrotic_ild_differential_seal_v1.md`
- `docs/navigation/project_status_roadmap_checkpoint_v0_7.md`

This document does not open domain parity.

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

Its purpose is to convert source intake into visible, bounded, non-authoritative claim mapping.

The v0.8 rule remains:

> “Source intake precedes source claims. Source claims precede domain parity.”

---

## 2. Mapping Status Legend

| Mapping Status | Meaning |
|---|---|
| mapped_for_prompt_visibility | Claim may support internal prompt visibility only |
| mapped_for_missing_evidence_visibility | Claim may support missing evidence prompts |
| mapped_for_mimic_visibility | Claim may support mimic visibility |
| mapped_for_review_prompt | Claim may support MDD/specialist/urgent review prompt |
| mapped_limited_treatment_heavy_source | Source supports context but treatment content is excluded |
| mapped_cautionary_case_only | Case source supports cautionary test design only |
| mapped_diagnostic_performance_limited | Diagnostic performance source supports ambiguity/feature visibility only |
| source_role_only | Source is admitted but claim scope remains too limited |
| not_allowed | Claim is outside v0.8 authority |

---

## 3. Blocking Status Legend

| Blocking Status | Meaning |
|---|---|
| clears_source_mapping | Claim is mapped for non-authoritative source-governed use |
| blocks_domain_parity | More structure/test coverage required before domain parity |
| blocks_diagnostic_authority | Diagnosis remains prohibited |
| blocks_treatment_authority | Treatment/management import remains prohibited |
| blocks_test_order_authority | Platform cannot order or recommend tests |
| blocks_public_ready | Public readiness remains false |
| blocks_clinically_reviewed | Clinical review remains false |
| cautionary_only | Cannot support generalized platform rule |

---

## 4. Claim-to-Source Mapping Table

| Claim ID | Claim Text | Source ID | Source Passage / Section | Claim Scope | Limitation | Affects Future File(s) | Mapping Status | Blocking Status |
|---|---|---|---|---|---|---|---|---|
| V08_CLAIM_OCC_001 | Occupational ILD includes heterogeneous exposure-related interstitial lung disease categories. | V08_SRC_OCCUPATIONAL_ILD_ACOEM_NYS | Occupational ILD overview / introduction | occupational mimic visibility | Does not diagnose occupational ILD. | occupational_ild_mimic_prompt_parity_v1.md | mapped_for_mimic_visibility | blocks_domain_parity |
| V08_CLAIM_OCC_002 | Occupationally related ILD may include pneumoconiosis, HP, granulomatous disease, and toxic inhalation injury categories. | V08_SRC_OCCUPATIONAL_ILD_ACOEM_NYS | Occupational ILD category table | source family boundary | Category visibility only. | occupational_ild_mimic_prompt_parity_v1.md | mapped_for_prompt_visibility | blocks_domain_parity |
| V08_CLAIM_OCC_003 | Silica, asbestos, coal mine dust, beryllium, hard metal, and irritant gases/radiation may support occupational exposure prompts. | V08_SRC_OCCUPATIONAL_ILD_ACOEM_NYS | Exposure / latency tables | missing occupational history prompt | Exposure prompt does not establish causation. | occupational_exposure_missing_evidence_matrix_v1.md | mapped_for_missing_evidence_visibility | blocks_diagnostic_authority |
| V08_CLAIM_OCC_004 | Occupational ILDs often have latency periods that may be years to decades depending on exposure type. | V08_SRC_OCCUPATIONAL_ILD_ACOEM_NYS | latency / exposure table | temporal reasoning prompt | Does not assign causality or compensation status. | occupational_ild_mimic_prompt_parity_v1.md | mapped_for_prompt_visibility | blocks_domain_parity |
| V08_CLAIM_OCC_005 | Occupational exposure history must remain visible when fibrosis, granulomatous disease, or pneumoconiosis-like patterns are considered. | V08_SRC_OCCUPATIONAL_ILD_ACOEM_NYS; V08_INTERNAL_V080_ENTRY_GATE | source plus internal governance | missing evidence governance | Internal prompt only. | high_risk_mimic_family_matrix_v1.md | mapped_for_missing_evidence_visibility | clears_source_mapping |
| V08_CLAIM_BERYL_001 | Beryllium exposure can lead to beryllium sensitization and chronic beryllium disease. | V08_SRC_ATS_BERYLLIUM_2014 | ATS statement rationale / overview | beryllium mimic visibility | Does not diagnose BeS or CBD. | beryllium_sarcoid_mimic_prompt_parity_v1.md | mapped_for_mimic_visibility | blocks_domain_parity |
| V08_CLAIM_BERYL_002 | BeLPT is a cornerstone test in BeS/CBD surveillance and diagnosis context. | V08_SRC_ATS_BERYLLIUM_2014 | BeLPT overview | test context prompt | Platform cannot interpret BeLPT. | beryllium_missing_evidence_matrix_v1.md | mapped_for_missing_evidence_visibility | blocks_test_order_authority |
| V08_CLAIM_BERYL_003 | BeS and CBD require distinction; CBD requires lung disease/granulomatous inflammation context in addition to sensitization. | V08_SRC_ATS_BERYLLIUM_2014 | diagnostic criteria for BeS/CBD | sarcoidosis mimic boundary | Does not diagnose CBD. | beryllium_sarcoid_mimic_prompt_parity_v1.md | mapped_for_prompt_visibility | blocks_diagnostic_authority |
| V08_CLAIM_BERYL_004 | Beryllium disease may mimic sarcoidosis or granulomatous ILD. | V08_SRC_ATS_BERYLLIUM_2014; V07_SRC_2020_ATS_SARCOIDOSIS_GUIDELINE | beryllium granulomatous disease context | sarcoid mimic visibility | Requires occupational exposure context. | granulomatous_mimic_source_map_v1.md | mapped_for_mimic_visibility | blocks_domain_parity |
| V08_CLAIM_BERYL_005 | Missing occupational or beryllium exposure context should keep berylliosis visible where granulomatous disease is considered. | V08_SRC_ATS_BERYLLIUM_2014; V08_INTERNAL_V080_ENTRY_GATE | source plus governance | missing evidence prompt | Prompt only. | high_risk_mimic_family_matrix_v1.md | mapped_for_missing_evidence_visibility | clears_source_mapping |
| V08_CLAIM_TB_001 | TB may be a granulomatous infection mimic and must remain visible when microbiology is incomplete. | V08_SRC_ATS_CDC_IDSA_TB_DIAGNOSIS_2016 | TB diagnosis guideline | infection mimic visibility | Does not diagnose or exclude TB. | tb_ntm_fungal_mimic_prompt_parity_v1.md | mapped_for_mimic_visibility | blocks_domain_parity |
| V08_CLAIM_TB_002 | A negative AFB smear does not exclude pulmonary TB. | V08_SRC_ATS_CDC_IDSA_TB_DIAGNOSIS_2016 | pulmonary TB testing remarks | test limitation prompt | Platform cannot interpret smear. | microbiology_missing_evidence_matrix_v1.md | mapped_for_missing_evidence_visibility | blocks_test_order_authority |
| V08_CLAIM_TB_003 | A positive AFB smear does not by itself confirm pulmonary TB. | V08_SRC_ATS_CDC_IDSA_TB_DIAGNOSIS_2016 | pulmonary TB testing remarks | test limitation prompt | Platform cannot confirm TB. | microbiology_missing_evidence_matrix_v1.md | mapped_for_missing_evidence_visibility | blocks_diagnostic_authority |
| V08_CLAIM_TB_004 | Culture remains a central microbiologic anchor for suspected TB disease. | V08_SRC_ATS_CDC_IDSA_TB_DIAGNOSIS_2016 | culture recommendation | missing microbiology prompt | Platform cannot order culture. | tb_ntm_fungal_mimic_prompt_parity_v1.md | mapped_for_missing_evidence_visibility | blocks_test_order_authority |
| V08_CLAIM_TB_005 | NAAT may support presumptive evidence in selected contexts but negative NAAT cannot exclude TB in smear-negative intermediate/high-suspicion cases. | V08_SRC_ATS_CDC_IDSA_TB_DIAGNOSIS_2016 | NAAT recommendation / rationale | test limitation prompt | No NAAT interpretation authority. | microbiology_missing_evidence_matrix_v1.md | mapped_for_missing_evidence_visibility | blocks_diagnostic_authority |
| V08_CLAIM_TB_006 | Laboratory testing does not replace clinical judgment in TB diagnosis. | V08_SRC_ATS_CDC_IDSA_TB_DIAGNOSIS_2016 | cautions and limitations | review prompt | Supports clinician/MDD review, not diagnosis. | high_risk_mimic_review_prompt_matrix_v1.md | mapped_for_review_prompt | clears_source_mapping |
| V08_CLAIM_NTM_001 | NTM lung disease requires clinical, radiographic, and microbiologic criteria together. | V08_SRC_ATS_IDSA_NTM_2007 | diagnostic criteria summary | NTM mimic boundary | Platform cannot diagnose NTM. | tb_ntm_fungal_mimic_prompt_parity_v1.md | mapped_for_prompt_visibility | blocks_diagnostic_authority |
| V08_CLAIM_NTM_002 | NTM evaluation includes exclusion of other diagnoses such as TB and malignancy. | V08_SRC_ATS_IDSA_NTM_2007 | diagnostic criteria | mimic visibility | Does not exclude TB/malignancy. | high_risk_mimic_family_matrix_v1.md | mapped_for_mimic_visibility | blocks_domain_parity |
| V08_CLAIM_NTM_003 | Multiple sputum cultures or bronchial wash/lavage/pathology contexts may be part of NTM diagnostic reasoning. | V08_SRC_ATS_IDSA_NTM_2007 | microbiologic criteria | missing microbiology prompt | Platform cannot order tests. | microbiology_missing_evidence_matrix_v1.md | mapped_for_missing_evidence_visibility | blocks_test_order_authority |
| V08_CLAIM_NTM_004 | Suspected NTM cases that do not meet criteria may require follow-up until diagnosis is established or excluded. | V08_SRC_ATS_IDSA_NTM_2007 | diagnostic criteria table | uncertainty prompt | Platform cannot set follow-up interval. | high_risk_mimic_review_prompt_matrix_v1.md | mapped_for_review_prompt | blocks_test_order_authority |
| V08_CLAIM_NTM_005 | Diagnosis of NTM lung disease does not automatically require therapy. | V08_SRC_ATS_IDSA_NTM_2007 | diagnostic criteria table | treatment-authority guard | No treatment decision. | high_risk_mimic_claim_to_source_mapping_table_v1.md | mapped_for_prompt_visibility | blocks_treatment_authority |
| V08_CLAIM_FUNGAL_001 | Fungal infections may mimic sarcoidosis, granulomatous disease, OP-like consolidation, or therapy-related lung injury. | V08_SRC_IDSA_ASPERGILLOSIS_2016; V08_SRC_IDSA_HISTOPLASMOSIS_2025; V08_SRC_COCCIDIOIDOMYCOSIS_SARCOID_MIMIC_CASE | fungal source family | fungal mimic visibility | Mixed authority; case reports cautionary only. | tb_ntm_fungal_mimic_prompt_parity_v1.md | mapped_for_mimic_visibility | blocks_domain_parity |
| V08_CLAIM_FUNGAL_002 | Histoplasmosis is an endemic fungal infection source relevant to granulomatous/sarcoid-like mimic visibility. | V08_SRC_IDSA_HISTOPLASMOSIS_2025 | guideline scope / histoplasmosis context | endemic fungal mimic prompt | Treatment-heavy source; treatment content excluded. | endemic_fungal_mimic_source_map_v1.md | mapped_limited_treatment_heavy_source | blocks_treatment_authority |
| V08_CLAIM_FUNGAL_003 | Aspergillosis source may support fungal mimic visibility in immunocompromised or compatible clinical contexts. | V08_SRC_IDSA_ASPERGILLOSIS_2016 | guideline diagnostic context | fungal mimic prompt | Treatment-heavy; no antifungal recommendation. | fungal_mimic_prompt_parity_v1.md | mapped_limited_treatment_heavy_source | blocks_treatment_authority |
| V08_CLAIM_FUNGAL_004 | Coccidioidomycosis may be used only as a cautionary sarcoidosis mimic example unless stronger source mapping is added. | V08_SRC_COCCIDIOIDOMYCOSIS_SARCOID_MIMIC_CASE | case report | cautionary example | Cannot generalize to domain parity. | future_test_cases/high_risk_mimic_pack | mapped_cautionary_case_only | cautionary_only |
| V08_CLAIM_FUNGAL_005 | Missing travel, endemic exposure, immunosuppression, microbiology, or fungal test context should keep fungal mimics visible. | V08_SRC_IDSA_HISTOPLASMOSIS_2025; V08_SRC_IDSA_ASPERGILLOSIS_2016; V08_INTERNAL_V080_ENTRY_GATE | source plus governance | missing evidence prompt | No diagnosis/exclusion. | microbiology_missing_evidence_matrix_v1.md | mapped_for_missing_evidence_visibility | clears_source_mapping |
| V08_CLAIM_ASP_001 | Aspiration-related disease may mimic infection, OP-like consolidation, or dependent lung injury. | V08_SRC_BTS_ASPIRATION_2023 | aspiration clinical statement | aspiration mimic visibility | Does not diagnose aspiration pneumonia. | aspiration_mimic_prompt_parity_v1.md | mapped_for_mimic_visibility | blocks_domain_parity |
| V08_CLAIM_ASP_002 | Silent aspiration or microaspiration context may be clinically relevant where supported by source review. | V08_SRC_BTS_ASPIRATION_2023 | aspiration clinical context | missing aspiration risk prompt | No swallow/airway decision. | aspiration_missing_evidence_matrix_v1.md | mapped_for_missing_evidence_visibility | blocks_test_order_authority |
| V08_CLAIM_ASP_003 | Aspiration risk must remain visible when OP-like or dependent consolidation is present. | V08_SRC_BTS_ASPIRATION_2023; V07_INTERNAL_V076_NSIP_OP_UNCLASSIFIABLE_PARITY | source plus internal OP parity | OP/aspiration overlap | Prompt only. | high_risk_mimic_family_matrix_v1.md | mapped_for_mimic_visibility | clears_source_mapping |
| V08_CLAIM_ASP_004 | Aspiration source may not be used to recommend antibiotics, swallow testing, feeding changes, or follow-up schedule. | V08_SRC_BTS_ASPIRATION_2023; V08_INTERNAL_V080_ENTRY_GATE | source limitation / governance | authority guard | Explicitly blocked. | high_risk_mimic_claim_to_source_mapping_table_v1.md | not_allowed | blocks_treatment_authority |
| V08_CLAIM_DILD_001 | Drug-induced ILD can be considered when medication or therapy exposure temporally overlaps lung findings. | V08_SRC_DRUG_INDUCED_ILD_REVIEWS | DI-ILD reviews | therapy-related mimic visibility | Review-level, lower authority. | drug_induced_ild_mimic_prompt_parity_v1.md | mapped_for_mimic_visibility | blocks_domain_parity |
| V08_CLAIM_DILD_002 | DI-ILD often requires consideration of temporal relationship and exclusion of alternative causes. | V08_SRC_DRUG_INDUCED_ILD_REVIEWS | diagnostic discussion in reviews | missing evidence prompt | Does not assign causality. | medication_therapy_history_missing_evidence_matrix_v1.md | mapped_for_missing_evidence_visibility | blocks_diagnostic_authority |
| V08_CLAIM_DILD_003 | DI-ILD may mimic NSIP-like, OP-like, acute injury, infection, or progression patterns. | V08_SRC_DRUG_INDUCED_ILD_REVIEWS; V07_INTERNAL_V076_NSIP_OP_UNCLASSIFIABLE_PARITY | review plus internal parity | mimic visibility | No diagnosis. | high_risk_mimic_family_matrix_v1.md | mapped_for_mimic_visibility | blocks_domain_parity |
| V08_CLAIM_DILD_004 | Drug discontinuation, steroid therapy, rechallenge, or oncologic therapy change are outside platform authority. | V08_SRC_DRUG_INDUCED_ILD_REVIEWS; V08_INTERNAL_V080_ENTRY_GATE | treatment-heavy source guard | authority guard | Explicitly blocked. | high_risk_mimic_claim_to_source_mapping_table_v1.md | not_allowed | blocks_treatment_authority |
| V08_CLAIM_RP_001 | Radiation pneumonitis / radiation-induced lung injury may mimic infection, tumor progression, drug toxicity, or ILD worsening. | V08_SRC_ESTRO_RADIATION_PNEUMONITIS_2025; V08_SRC_CHEST_RILI_2019 | RP/RILI guideline and review | therapy-related mimic visibility | No RP diagnosis. | radiation_pneumonitis_mimic_prompt_parity_v1.md | mapped_for_mimic_visibility | blocks_domain_parity |
| V08_CLAIM_RP_002 | Radiation timing, field, dose context, and prior imaging may be important missing evidence domains. | V08_SRC_ESTRO_RADIATION_PNEUMONITIS_2025; V08_SRC_CHEST_RILI_2019 | radiation context sections | missing evidence prompt | No radiotherapy decision. | radiation_history_missing_evidence_matrix_v1.md | mapped_for_missing_evidence_visibility | blocks_test_order_authority |
| V08_CLAIM_RP_003 | Acute radiation pneumonitis and chronic radiation fibrosis are temporally distinct source concepts for future mapping. | V08_SRC_CHEST_RILI_2019 | RILI temporal review | temporal reasoning prompt | No diagnosis or treatment. | therapy_related_temporal_reasoning_matrix_v1.md | mapped_for_prompt_visibility | blocks_domain_parity |
| V08_CLAIM_RP_004 | Radiation-related sources may not be used to recommend steroids, radiotherapy modification, or follow-up interval. | V08_SRC_ESTRO_RADIATION_PNEUMONITIS_2025; V08_INTERNAL_V080_ENTRY_GATE | treatment-heavy guard | authority guard | Explicitly blocked. | high_risk_mimic_claim_to_source_mapping_table_v1.md | not_allowed | blocks_treatment_authority |
| V08_CLAIM_CIP_001 | Checkpoint inhibitor exposure may support therapy-related pneumonitis mimic visibility. | V08_SRC_PREEXISTING_ILD_RP_CIP_META_2025; V08_SRC_ICI_SARCOID_LIKE_REACTION_2026 | ICI toxicity / SLR sources | ICI mimic prompt | No CIP diagnosis. | checkpoint_inhibitor_pneumonitis_mimic_prompt_parity_v1.md | mapped_for_mimic_visibility | blocks_domain_parity |
| V08_CLAIM_CIP_002 | Pre-existing ILD may increase caution for radiation pneumonitis or checkpoint inhibitor pneumonitis risk context. | V08_SRC_PREEXISTING_ILD_RP_CIP_META_2025 | meta-analysis | risk context only | Does not calculate risk or decide therapy. | therapy_related_risk_context_matrix_v1.md | mapped_for_prompt_visibility | blocks_treatment_authority |
| V08_CLAIM_CIP_003 | ICI-related pneumonitis may overlap with infection, progression, radiation pneumonitis, or drug toxicity. | V08_SRC_PREEXISTING_ILD_RP_CIP_META_2025; V08_INTERNAL_V080_ENTRY_GATE | source plus governance | mimic overlap prompt | No diagnosis/exclusion. | high_risk_mimic_family_matrix_v1.md | mapped_for_mimic_visibility | blocks_domain_parity |
| V08_CLAIM_CIP_004 | Immunotherapy hold/restart, steroid use, grading, or oncology management remain outside platform authority. | V08_SRC_ICI_SARCOID_LIKE_REACTION_2026; V08_INTERNAL_V080_ENTRY_GATE | treatment-heavy guard | authority guard | Explicitly blocked. | high_risk_mimic_claim_to_source_mapping_table_v1.md | not_allowed | blocks_treatment_authority |
| V08_CLAIM_PLC_001 | Pulmonary lymphangitic carcinomatosis may mimic ILD, infection, edema, or sarcoid-like disease. | V08_SRC_PLC_HRCT_PET_DIAGNOSTIC_PERFORMANCE_2020; V08_SRC_PLC_MIMICKING_ILD_CASE_2025 | diagnostic performance study and case report | malignancy mimic visibility | Does not diagnose PLC. | malignancy_plc_mimic_prompt_parity_v1.md | mapped_for_mimic_visibility | blocks_domain_parity |
| V08_CLAIM_PLC_002 | Septal thickening, peribronchovascular thickening/infiltration, nodularity, lymphadenopathy, pleural effusion, or asymmetric disease may support PLC mimic prompt visibility. | V08_SRC_PLC_HRCT_PET_DIAGNOSTIC_PERFORMANCE_2020; V08_SRC_PLC_MIMICKING_ILD_CASE_2025 | HRCT/PET features / case discussion | imaging feature prompt | Feature prompt only; no interpretation authority. | malignancy_plc_mimic_prompt_parity_v1.md | mapped_diagnostic_performance_limited | blocks_diagnostic_authority |
| V08_CLAIM_PLC_003 | PET/CT or HRCT ambiguity may support malignancy mimic visibility but cannot settle recurrence or PLC diagnosis. | V08_SRC_PLC_HRCT_PET_DIAGNOSTIC_PERFORMANCE_2020 | diagnostic performance source | imaging ambiguity prompt | No PET/CT interpretation authority. | pet_ct_ambiguity_prompt_matrix_v1.md | mapped_diagnostic_performance_limited | blocks_test_order_authority |
| V08_CLAIM_PLC_004 | Progressive unexplained dyspnea with nonspecific CT findings and nonresponse to empiric therapy should preserve malignancy mimic re-review prompt. | V08_SRC_PLC_MIMICKING_ILD_CASE_2025 | cautionary case | cautionary test design | Case-only; not general rule alone. | future_test_cases/high_risk_mimic_pack | mapped_cautionary_case_only | cautionary_only |
| V08_CLAIM_SLR_001 | Sarcoid-like reaction can occur in neoplastic patients and may mimic malignancy recurrence or metastatic disease. | V08_SRC_SARCOID_LIKE_REACTION_NEOPLASTIC_PATIENTS; V08_SRC_SARCOIDOSIS_AFTER_LYMPHOMA_2014; V08_SRC_SARCOIDOSIS_LYMPHOMA_REVIEW_2025 | sarcoid-like reaction / lymphoma sources | malignancy mimic visibility | Does not diagnose SLR or exclude malignancy. | sarcoid_like_reaction_malignancy_mimic_prompt_parity_v1.md | mapped_for_mimic_visibility | blocks_domain_parity |
| V08_CLAIM_SLR_002 | FDG-avid lymphadenopathy can be ambiguous between sarcoid-like reaction, sarcoidosis, lymphoma, or recurrence. | V08_SRC_SARCOIDOSIS_AFTER_LYMPHOMA_2014; V08_SRC_ICI_SARCOID_LIKE_REACTION_2026 | CT/PET follow-up / imaging ambiguity | PET ambiguity prompt | No recurrence decision. | pet_ct_ambiguity_prompt_matrix_v1.md | mapped_for_prompt_visibility | blocks_diagnostic_authority |
| V08_CLAIM_SLR_003 | Histologic confirmation may be important in recurrence-vs-sarcoid-like uncertainty, but platform cannot decide biopsy. | V08_SRC_SARCOID_LIKE_REACTION_NEOPLASTIC_PATIENTS; V08_SRC_SARCOIDOSIS_AFTER_LYMPHOMA_2014 | histologic confirmation discussion | review prompt | Biopsy decision blocked. | malignancy_mimic_review_prompt_matrix_v1.md | mapped_for_review_prompt | blocks_test_order_authority |
| V08_CLAIM_SLR_004 | ICI-associated sarcoidosis-like reaction may present with thoracic lymphadenopathy, pulmonary nodules, FDG avidity, and recurrence mimic ambiguity. | V08_SRC_ICI_SARCOID_LIKE_REACTION_2026 | ICI-SLR review | therapy-related sarcoid-like mimic | Treatment-heavy; oncology management blocked. | ici_sarcoid_like_reaction_prompt_parity_v1.md | mapped_for_mimic_visibility | blocks_domain_parity |
| V08_CLAIM_SLR_005 | Sarcoid-like reaction sources may support mimic visibility, but not malignancy exclusion, lymphoma relapse exclusion, or SLR diagnosis. | V08_SRC_SARCOID_LIKE_REACTION_NEOPLASTIC_PATIENTS; V08_INTERNAL_V080_ENTRY_GATE | source plus governance | authority guard | Explicitly blocked. | high_risk_mimic_claim_to_source_mapping_table_v1.md | not_allowed | blocks_diagnostic_authority |
| V08_CLAIM_URGENT_001 | Acute hypoxemia, rapid dyspnea, fever/systemic illness, immunosuppression, hemoptysis, or known malignancy with new findings should preserve urgent review visibility. | V08_INTERNAL_V080_ENTRY_GATE; V07_INTERNAL_V073_FAMILY_MATRIX | internal governance plus prior family matrix | urgent review prompt | Does not triage, diagnose, or treat. | high_risk_mimic_review_prompt_matrix_v1.md | mapped_for_review_prompt | clears_source_mapping |
| V08_CLAIM_MDD_001 | High-risk mimic uncertainty may require pulmonology, radiology, pathology, microbiology, occupational medicine, oncology, radiation oncology, or MDD review visibility. | V08_INTERNAL_V080_ENTRY_GATE; V08_INTERNAL_V081_SOURCE_ROLE_MAP | internal governance | review prompt | Does not replace specialist review. | high_risk_mimic_review_prompt_matrix_v1.md | mapped_for_review_prompt | clears_source_mapping |
| V08_CLAIM_AUTH_001 | Source intake does not open domain parity. | V08_INTERNAL_V080_ENTRY_GATE; V08_INTERNAL_V081_SOURCE_ROLE_MAP | internal governance | authority boundary | Applies to all v0.8 files. | all v0.8 files | source_role_only | clears_source_mapping |
| V08_CLAIM_AUTH_002 | Source claims do not create diagnostic authority. | V08_INTERNAL_V080_ENTRY_GATE; V08_INTERNAL_V081_SOURCE_ROLE_MAP | internal governance | authority boundary | Applies to all v0.8 files. | all v0.8 files | source_role_only | blocks_diagnostic_authority |
| V08_CLAIM_AUTH_003 | Treatment-heavy sources may support mimic visibility but may not import treatment recommendations. | V08_INTERNAL_V080_ENTRY_GATE; V08_INTERNAL_V081_SOURCE_ROLE_MAP | internal governance | treatment boundary | Applies to all treatment-heavy sources. | all v0.8 files | source_role_only | blocks_treatment_authority |
| V08_CLAIM_AUTH_004 | Case reports may inspire test cases but cannot support generalized platform rules alone. | V08_INTERNAL_V081_SOURCE_ROLE_MAP | internal governance | evidence hierarchy boundary | Applies to all case-example sources. | all v0.8 test cases | source_role_only | cautionary_only |
| V08_CLAIM_AUTH_005 | Public readiness and clinically reviewed status remain false. | V08_INTERNAL_V080_ENTRY_GATE; checkpoint-v0.7 | internal governance | deployment boundary | Applies globally. | all v0.8 files | source_role_only | blocks_public_ready |

---

## 5. Claims Cleared for Non-Authoritative Structural Use

The following claim families are cleared only for internal, non-authoritative structural drafting.

| Claim Family | Status |
|---|---|
| Occupational exposure missing-evidence prompt | cleared_for_structural_use |
| Pneumoconiosis / asbestosis mimic visibility | cleared_for_structural_use |
| Beryllium / CBD sarcoidosis mimic visibility | cleared_for_structural_use |
| BeLPT context visibility without interpretation | cleared_for_structural_use |
| TB mimic visibility with AFB/NAAT/culture limitations | cleared_for_structural_use |
| NTM mimic visibility with clinical-radiographic-microbiologic integration | cleared_for_structural_use |
| Fungal mimic visibility with treatment-heavy restriction | cleared_for_structural_use_limited |
| Aspiration risk prompt | cleared_for_structural_use_limited |
| Drug-induced / therapy-related ILD mimic visibility | cleared_for_structural_use_review_level |
| Radiation pneumonitis / RILI mimic visibility | cleared_for_structural_use_limited |
| Checkpoint inhibitor pneumonitis / ICI toxicity prompt | cleared_for_structural_use_review_level |
| Pulmonary lymphangitic carcinomatosis mimic visibility | cleared_for_structural_use_limited |
| Sarcoid-like reaction / malignancy recurrence ambiguity | cleared_for_structural_use_limited |
| PET/CT ambiguity prompt | cleared_for_structural_use_limited |
| Urgent review visibility | cleared_for_structural_use |
| MDD / specialist review visibility | cleared_for_structural_use |

---

## 6. Claims Not Cleared

The following claim types are not cleared.

| Claim Type | Reason |
|---|---|
| Occupational ILD diagnosis | diagnostic_authority none |
| Asbestosis / silicosis / CWP diagnosis | diagnostic_authority none |
| BeS / CBD diagnosis | diagnostic_authority none |
| BeLPT interpretation | test interpretation authority blocked |
| TB diagnosis or exclusion | diagnostic_authority none |
| NTM diagnosis or exclusion | diagnostic_authority none |
| Fungal infection diagnosis or exclusion | diagnostic_authority none |
| Aspiration pneumonia diagnosis | diagnostic_authority none |
| Drug-induced ILD causality assignment | diagnostic_authority none |
| Drug discontinuation | treatment_authority none |
| Radiation pneumonitis diagnosis | diagnostic_authority none |
| Steroid recommendation | treatment_authority none |
| Checkpoint inhibitor hold/restart | oncology management blocked |
| Pulmonary lymphangitic carcinomatosis diagnosis | diagnostic_authority none |
| Malignancy recurrence diagnosis | diagnostic_authority none |
| Lymphoma relapse exclusion | diagnostic_authority none |
| Sarcoid-like reaction diagnosis | diagnostic_authority none |
| PET/CT interpretation authority | test interpretation authority blocked |
| Biopsy / bronchoscopy / BAL decision | test/procedure authority blocked |
| Follow-up interval | management authority blocked |
| Public-ready output | public_ready false |
| Clinically reviewed output | clinically_reviewed false |

---

## 7. Source Debt Status After v0.8.2

| Debt ID | Domain | v0.8.1 Status | v0.8.2 Status | Still Blocks |
|---|---|---|---|---|
| V08_DEBT_OCC_001 | Occupational ILD / pneumoconiosis / asbestosis | role_mapped | key_prompt_claims_mapped | domain parity; test cases |
| V08_DEBT_BERYL_001 | Chronic beryllium disease | role_mapped | key_prompt_claims_mapped | domain parity; test cases |
| V08_DEBT_TB_001 | Tuberculosis mimic | role_mapped | key_prompt_claims_mapped | domain parity; test cases |
| V08_DEBT_NTM_001 | NTM mimic | role_mapped | key_prompt_claims_mapped | domain parity; test cases |
| V08_DEBT_FUNGAL_001 | Aspergillosis / fungal mimic | role_mapped_limited | limited_claims_mapped | domain parity; stronger sources if needed |
| V08_DEBT_HISTO_001 | Histoplasmosis / endemic fungal mimic | role_mapped_limited | limited_claims_mapped | domain parity; treatment import blocked |
| V08_DEBT_COCCI_001 | Coccidioidomycosis mimic | cautionary_role_mapped | cautionary_claim_only | domain parity blocked |
| V08_DEBT_ASP_001 | Aspiration-related disease | role_mapped_limited | limited_claims_mapped | domain parity; test cases |
| V08_DEBT_DILD_001 | Drug-induced ILD | auxiliary_role_mapped | review_level_claims_mapped | domain parity; higher authority if needed |
| V08_DEBT_RP_001 | Radiation pneumonitis / RILI | role_mapped_limited | limited_claims_mapped | domain parity; test cases |
| V08_DEBT_CIP_001 | Checkpoint inhibitor pneumonitis | auxiliary_role_mapped | review_level_claims_mapped | domain parity; test cases |
| V08_DEBT_PLC_001 | Pulmonary lymphangitic carcinomatosis | role_mapped | feature_visibility_claims_mapped | domain parity; test cases |
| V08_DEBT_SLR_001 | Sarcoid-like reaction / malignancy mimic | role_mapped | ambiguity_claims_mapped | domain parity; test cases |
| V08_DEBT_LYMPHOMA_001 | Lymphoma / sarcoidosis overlap | role_mapped | ambiguity_claims_mapped | domain parity; test cases |

Debt rule:

> v0.8.2 reduces claim mapping debt, but does not open domain parity.

---

## 8. Future Structural Use

v0.8.2 permits future drafting of:

- high-risk mimic family matrix,
- missing evidence matrix,
- urgent review matrix,
- MDD / specialist review prompt matrix,
- source-limited mimic prompt parity,
- high-risk mimic test case pack.

v0.8.2 does not permit:

- diagnostic algorithms,
- treatment pathways,
- order recommendations,
- procedure decisions,
- public-ready outputs,
- clinical review claims.

---

## 9. Acceptance Criteria

v0.8.2 is accepted only if:

- claim-to-source mapping exists for all major v0.8 source families,
- claim types are non-authoritative,
- source limitations remain visible,
- treatment-heavy sources remain constrained,
- diagnostic performance sources remain constrained,
- cautionary case sources remain constrained,
- source debt status is updated,
- domain parity remains closed,
- diagnostic_authority remains none,
- treatment_authority remains none,
- public_ready remains false,
- clinically_reviewed remains false.

---

## 10. Next Step

The next recommended step is:

- v0.8.3 — High-Risk Mimic Family Matrix / Missing Evidence and Review Prompt Model

v0.8.3 should define mimic families, missing evidence states, overlap states, urgent review states, and specialist/MDD review prompts.

It should not yet create domain-specific parity locks.

It must preserve:

- diagnostic_authority: none,
- treatment_authority: none,
- public_ready: false,
- clinically_reviewed: false.

---

## 11. Governance Statement

This claim-to-source mapping table reduces v0.8 source debt while preserving non-authority.

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