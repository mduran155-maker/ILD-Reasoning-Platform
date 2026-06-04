# ILD Reasoning Platform — Non-UIP Differential Claim-to-Source Mapping Table v1

Version: v0.7.2  
Status: claim_to_source_mapping_table  
Scope: Non-UIP fibrotic ILD differential reasoning claim-to-source mapping  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This document maps initial v0.7 non-UIP fibrotic ILD differential reasoning claims to source anchors.

It follows:

- `docs/navigation/non_uip_fibrotic_ild_differential_reasoning_entry_gate_v1.md`
- `docs/navigation/non_uip_fibrotic_ild_source_anchor_map_v1.md`

This document does not diagnose hypersensitivity pneumonitis.  
This document does not diagnose CTD-ILD.  
This document does not diagnose fibrotic NSIP.  
This document does not diagnose organizing pneumonia.  
This document does not diagnose sarcoidosis.  
This document does not diagnose occupational ILD.  
This document does not diagnose drug toxicity.  
This document does not recommend treatment.  
This document does not decide biopsy.  
This document does not create public readiness.  
This document does not make v0.7 clinically reviewed.

Its purpose is to make claim provenance visible before differential reasoning rules are written.

The controlling v0.7 principle remains:

> “Differential reasoning is not differential diagnosis authority.”

The inherited source-governance rule remains:

> “Available source is not mapped source. Mapped source is not clinical review.”

---

## 2. Source Status at v0.7.2

| Source ID | Source | Role | Status |
|---|---|---|---|
| V07_SRC_2020_ATS_JRS_ALAT_HP_GUIDELINE | Raghu et al. 2020 ATS/JRS/ALAT Diagnosis of Hypersensitivity Pneumonitis in Adults | primary HP source | targeted_mapping_started |
| V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION | Travis et al. 2013 ATS/ERS IIP Classification Update | primary IIP / NSIP / OP / unclassifiable source | targeted_mapping_started |
| V07_SRC_2023_ACR_CHEST_SARD_ILD_SCREEN_MONITOR | 2023 ACR/CHEST SARD-ILD Screening and Monitoring Guideline | primary SARD-ILD / CTD-ILD source | targeted_mapping_started |
| V07_SRC_2020_ATS_SARCOIDOSIS_GUIDELINE | Crouser et al. 2020 ATS Sarcoidosis Diagnosis and Detection Guideline | primary sarcoidosis / granulomatous differential source | targeted_mapping_started |
| V07_SRC_2020_HP_CLINICIAN_SUMMARY | Koster et al. 2021 HP clinician summary | auxiliary HP source | auxiliary_available |
| UIP_SRC_2018_ATS_ERS_JRS_ALAT_DX | 2018 IPF Diagnosis Guideline | UIP inheritance source | mapped_in_v0_6_R2 |
| UIP_SRC_2022_ATS_ERS_JRS_ALAT_IPF_PPF | 2022 IPF Update / PPF Guideline | PPF inheritance source | mapped_in_v0_6_R2 |
| V07_SRC_INTERNAL_V06_R1_R2_R3_BACKFILL | Internal v0.6 source-debt/backfill chain | source-governance inheritance | sealed_internal_governance |

Status rule:

- targeted mapping supports internal structural reasoning only,
- targeted mapping does not equal full guideline extraction,
- targeted mapping does not equal clinical review,
- clinically_reviewed remains false.

---

## 3. Mapping Status Legend

| Mapping Status | Meaning |
|---|---|
| mapped_targeted_review | Specific source section or passage family supports the claim for internal structural use |
| mapped_partial | Source relationship is identified but requires fuller extraction before stronger use |
| auxiliary_mapped | Source supports adjacent reasoning but is not the primary source |
| source_needed | Primary source not yet selected or uploaded |
| internal_governance_only | Claim comes from platform governance rather than external clinical source |
| not_allowed | Claim is outside v0.7 authority |

---

## 4. Blocking Status Legend

| Blocking Status | Meaning |
|---|---|
| clears_structural_use | Sufficient for internal non-authoritative structural drafting |
| blocks_domain_lock | Must be resolved before domain parity lock |
| blocks_structural_seal | Must be resolved before v0.7 structural seal |
| blocks_clinical_reviewed | Must be resolved before any clinically_reviewed status |
| blocks_public_ready | Public readiness remains blocked |
| blocks_treatment_authority | Treatment authority not allowed |
| auxiliary_only | Can support context but cannot be primary domain authority |

---

## 5. Claim-to-Source Mapping Table

| Claim ID | Claim Text | Source ID | Source Passage or Section | Claim Scope | Limitation | Affects File(s) | Mapping Status | Blocking Status |
|---|---|---|---|---|---|---|---|---|
| V07_CLAIM_HP_001 | HP must be considered in the differential diagnosis of newly identified ILD. | V07_SRC_2020_ATS_JRS_ALAT_HP_GUIDELINE | Summary of Recommendations | HP differential entry | Differential prompt only; does not diagnose HP. | future HP parity; differential family matrix | mapped_targeted_review | clears_structural_use |
| V07_CLAIM_HP_002 | HP is categorized into nonfibrotic and fibrotic phenotypes. | V07_SRC_2020_ATS_JRS_ALAT_HP_GUIDELINE | Summary of Recommendations; Definition; Subtypes of HP | HP phenotype boundary | Phenotype category is not platform diagnosis. | future HP parity | mapped_targeted_review | clears_structural_use |
| V07_CLAIM_HP_003 | Thorough exposure history is central to HP evaluation, but exposure may remain unidentified. | V07_SRC_2020_ATS_JRS_ALAT_HP_GUIDELINE | Summary of Recommendations; Introduction; Definition | Exposure evidence prompt | Missing exposure does not exclude HP. | future HP parity; missing evidence prompts | mapped_targeted_review | clears_structural_use |
| V07_CLAIM_HP_004 | Serum IgG testing may support identification of potential HP antigens, but does not diagnose HP alone. | V07_SRC_2020_ATS_JRS_ALAT_HP_GUIDELINE | Summary of Recommendations; Question 2 | Exposure-supporting evidence | Cannot become automated diagnosis. | future HP parity | mapped_targeted_review | clears_structural_use |
| V07_CLAIM_HP_005 | BAL lymphocyte cellular analysis is part of HP diagnostic evaluation depending on phenotype context. | V07_SRC_2020_ATS_JRS_ALAT_HP_GUIDELINE | Summary of Recommendations; Questions 3–6 | BAL evidence prompt | Platform may show evidence gap, not order BAL. | future HP parity | mapped_targeted_review | blocks_clinical_reviewed |
| V07_CLAIM_HP_006 | Fibrotic HP can be misdiagnosed as IPF or another IIP. | V07_SRC_2020_ATS_JRS_ALAT_HP_GUIDELINE | Introduction; How to Use These Guidelines | HP/UIP/IIP overlap | Supports mimic visibility only. | differential family matrix; HP parity | mapped_targeted_review | clears_structural_use |
| V07_CLAIM_HP_007 | Guideline selection between HP and IPF pathways depends on exposure context and MDD redirection. | V07_SRC_2020_ATS_JRS_ALAT_HP_GUIDELINE | How to Use These Guidelines | Differential pathway humility | Does not create automated guideline routing. | source anchor map; HP parity | mapped_targeted_review | clears_structural_use |
| V07_CLAIM_HP_008 | HP HRCT protocol includes inspiratory and expiratory imaging; air trapping is an expiratory finding. | V07_SRC_2020_ATS_JRS_ALAT_HP_GUIDELINE | Chest HRCT Scanning Protocol | Imaging technique prompt | Platform may expose technique limitation, not require scan. | HP parity; temporal/technique prompts | mapped_targeted_review | clears_structural_use |
| V07_CLAIM_HP_009 | Nonfibrotic HP typical HRCT includes parenchymal infiltration plus small airway disease features such as centrilobular nodules or air trapping. | V07_SRC_2020_ATS_JRS_ALAT_HP_GUIDELINE | Radiological Features; Table 5 | Nonfibrotic HP pattern prompt | Pattern is not disease diagnosis. | HP parity | mapped_targeted_review | clears_structural_use |
| V07_CLAIM_HP_010 | Fibrotic HP may show fibrosis plus bronchiolar obstruction features such as mosaic attenuation, air trapping, and three-density pattern. | V07_SRC_2020_ATS_JRS_ALAT_HP_GUIDELINE | Radiological Features; Table 4; Table 6 | Fibrotic HP prompt | Three-density supports suspicion, not diagnosis. | HP parity; mimic visibility | mapped_targeted_review | clears_structural_use |
| V07_CLAIM_HP_011 | UIP pattern alone can be indeterminate for fibrotic HP when HP-supporting features are absent. | V07_SRC_2020_ATS_JRS_ALAT_HP_GUIDELINE | Fibrotic HP HRCT pattern; Table 6 | HP vs UIP boundary | Prevents forced HP or IPF closure. | HP parity; differential matrix | mapped_targeted_review | clears_structural_use |
| V07_CLAIM_HP_012 | Fibrotic HP histology can overlap with UIP pattern, creating differential difficulty. | V07_SRC_2020_ATS_JRS_ALAT_HP_GUIDELINE | Histopathological Features of Fibrotic HP | Histology overlap | Requires MDD/pathology integration. | HP parity | mapped_targeted_review | blocks_clinical_reviewed |
| V07_CLAIM_HP_013 | HP diagnosis requires multidisciplinary integration. | V07_SRC_2020_ATS_JRS_ALAT_HP_GUIDELINE | Introduction; How to Use These Guidelines | MDD prompt | MDD prompt is review routing, not diagnosis. | HP parity; test cases | mapped_targeted_review | clears_structural_use |
| V07_CLAIM_IIP_001 | IIP classification includes major IIPs, rare IIPs, and unclassifiable IIPs. | V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION | Executive Summary; Table 1 | IIP family framework | Classification source does not diagnose individual patient. | differential family matrix | mapped_targeted_review | clears_structural_use |
| V07_CLAIM_IIP_002 | Major IIPs include IPF, idiopathic NSIP, RB-ILD, DIP, COP, and AIP. | V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION | Table 1; Table 2 | IIP taxonomy | v0.7 focuses reasoning prompts, not diagnosis. | differential family matrix | mapped_targeted_review | clears_structural_use |
| V07_CLAIM_IIP_003 | Multidisciplinary diagnosis of IIP is dynamic and integrates clinical, radiologic, and pathologic data. | V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION | General Progress in IIPs; Multidisciplinary Approach | MDD integration | Platform cannot replace MDD. | all v0.7 domain files | mapped_targeted_review | clears_structural_use |
| V07_CLAIM_IIP_004 | IIP diagnosis requires exclusion of known causes such as drug exposure, inhalational exposure, and collagen vascular disease. | V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION | Observer Agreement / Important Differential Considerations | Known-cause exclusion | Platform may expose gaps, not exclude causes. | differential family matrix; missing evidence prompts | mapped_targeted_review | clears_structural_use |
| V07_CLAIM_IIP_005 | HP and IIPs are frequently confused, especially when exposure is not readily apparent. | V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION | Important Differential Diagnostic Considerations: Hypersensitivity Pneumonitis | HP/IIP mimic | Supports differential visibility. | HP parity; IIP matrix | mapped_targeted_review | clears_structural_use |
| V07_CLAIM_IIP_006 | HRCT features suggesting HP include centrilobular nodules, mosaic air trapping, and upper-lobe distribution. | V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION | Hypersensitivity Pneumonitis section | HP mimic cue | Auxiliary to HP guideline; not sole HP authority. | HP parity | auxiliary_mapped | auxiliary_only |
| V07_CLAIM_IIP_007 | CVD is a frequent cause of interstitial pneumonia patterns, especially NSIP. | V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION | Collagen Vascular Disease section | CTD-ILD prompt | Must be paired with SARD-ILD source. | CTD-ILD prompt parity | mapped_targeted_review | clears_structural_use |
| V07_CLAIM_IIP_008 | NSIP is accepted as a distinct clinicopathologic entity. | V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION | Executive Summary; Chronic Fibrosing IIPs | NSIP boundary | Does not diagnose idiopathic NSIP automatically. | NSIP/OP/unclassifiable parity | mapped_targeted_review | clears_structural_use |
| V07_CLAIM_IIP_009 | NSIP can occur in CVD, HP, drug toxicity, and familial fibrosis contexts. | V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION | Idiopathic NSIP section | NSIP mimic / secondary cause prompt | Idiopathic NSIP requires exclusion of secondary causes. | NSIP/OP/unclassifiable parity | mapped_targeted_review | clears_structural_use |
| V07_CLAIM_IIP_010 | NSIP HRCT often includes bilateral GGO, traction bronchiectasis, and possible subpleural sparing. | V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION | Idiopathic NSIP section; Figure 2 | NSIP-like imaging prompt | Pattern prompt only. | NSIP parity | mapped_targeted_review | clears_structural_use |
| V07_CLAIM_IIP_011 | OP may be idiopathic or secondary, and the generic OP term should use modifiers as appropriate. | V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION | Cryptogenic organizing pneumonia section | OP boundary | OP pattern does not equal COP diagnosis. | NSIP/OP/unclassifiable parity | mapped_targeted_review | clears_structural_use |
| V07_CLAIM_IIP_012 | OP HRCT may show patchy or migratory consolidation in subpleural, peribronchial, or bandlike pattern. | V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION | COP section; Figure 4 | OP imaging prompt | Must preserve infection/aspiration/drug/CTD alternatives. | OP overlap parity | mapped_targeted_review | clears_structural_use |
| V07_CLAIM_IIP_013 | Multiple HRCT/pathologic patterns may coexist in the same patient. | V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION | Coexisting Patterns section | Overlap reasoning | Supports v0.3 superimposed-events inheritance. | differential matrix; test cases | mapped_targeted_review | clears_structural_use |
| V07_CLAIM_IIP_014 | Unclassifiable IIP may result from inadequate data or major clinical-radiologic-pathologic discordance. | V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION | Table 1 footnote; Unclassifiable IIP section | Unclassifiable reasoning | Must preserve uncertainty, not force diagnosis. | unclassifiable parity | mapped_targeted_review | clears_structural_use |
| V07_CLAIM_IIP_015 | Acute exacerbation can occur in chronic fibrosing IIPs and requires exclusion of infection, left heart failure, and other causes before diagnosis. | V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION | Acute exacerbation of IIP section | Acute overlay | Imaging alone cannot confirm acute exacerbation. | temporal/urgent review prompts | mapped_targeted_review | clears_structural_use |
| V07_CLAIM_SARD_001 | SARD-ILD guideline scope includes RA, systemic sclerosis, idiopathic inflammatory myopathies, MCTD, and Sjögren disease. | V07_SRC_2023_ACR_CHEST_SARD_ILD_SCREEN_MONITOR | Objective; Scope; Table 1 | SARD-ILD scope | Does not include every autoimmune condition. | CTD-ILD prompt parity | mapped_targeted_review | clears_structural_use |
| V07_CLAIM_SARD_002 | SARD-ILD guideline does not guide evaluation for SARDs in newly diagnosed ILD without known SARD diagnosis. | V07_SRC_2023_ACR_CHEST_SARD_ILD_SCREEN_MONITOR | Scope section | Scope boundary | Prevents overuse for general ILD autoimmunity workup. | CTD-ILD prompt parity | mapped_targeted_review | clears_structural_use |
| V07_CLAIM_SARD_003 | HRCT and PFTs are conditionally recommended for screening people with SARDs at increased ILD risk. | V07_SRC_2023_ACR_CHEST_SARD_ILD_SCREEN_MONITOR | Results; Screening recommendations; Table 2 | Screening context | Platform cannot order screening. | CTD-ILD prompt parity | mapped_targeted_review | blocks_treatment_authority |
| V07_CLAIM_SARD_004 | HRCT and PFTs are conditionally recommended for monitoring SARD-ILD progression. | V07_SRC_2023_ACR_CHEST_SARD_ILD_SCREEN_MONITOR | Monitoring recommendations; Table 3 | Monitoring context | Platform cannot define monitoring schedule. | CTD-ILD prompt parity | mapped_targeted_review | blocks_treatment_authority |
| V07_CLAIM_SARD_005 | ACR/CHEST recommendations are voluntary guidance and must be applied by clinicians in individual patient context. | V07_SRC_2023_ACR_CHEST_SARD_ILD_SCREEN_MONITOR | Guideline disclaimer; Methods | Authority boundary | Strongly supports diagnostic_authority none. | all v0.7 CTD/SARD files | mapped_targeted_review | clears_structural_use |
| V07_CLAIM_SARD_006 | SARD-ILD risk factors include disease manifestations and antibody profiles, varying by disease. | V07_SRC_2023_ACR_CHEST_SARD_ILD_SCREEN_MONITOR | Introduction; Table 1 | Risk context prompt | Risk factor absence does not exclude ILD. | CTD-ILD prompt parity | mapped_targeted_review | clears_structural_use |
| V07_CLAIM_SARD_007 | HRCT and PFTs provide complementary information: HRCT for presence/pattern and PFTs for physiologic impact. | V07_SRC_2023_ACR_CHEST_SARD_ILD_SCREEN_MONITOR | Screening with HRCT and PFTs section | Evidence complementarity | Platform may show missing evidence, not order tests. | CTD-ILD prompt parity | mapped_targeted_review | clears_structural_use |
| V07_CLAIM_SARD_008 | HRCT technique can help distinguish dependent atelectasis from early fibrosis and assess air trapping. | V07_SRC_2023_ACR_CHEST_SARD_ILD_SCREEN_MONITOR | HRCT screening section | Technique limitation prompt | Supports missing technique evidence visibility. | CTD-ILD prompt parity; technique prompts | mapped_targeted_review | clears_structural_use |
| V07_CLAIM_SARD_009 | Surgical lung biopsy is strongly recommended against for routine screening in people with SARDs at increased ILD risk. | V07_SRC_2023_ACR_CHEST_SARD_ILD_SCREEN_MONITOR | Table 2 | Biopsy boundary | Platform cannot decide biopsy. | CTD-ILD prompt parity | mapped_targeted_review | blocks_clinical_reviewed |
| V07_CLAIM_SARC_001 | Sarcoidosis diagnosis is based on compatible clinical presentation, nonnecrotizing granulomatous inflammation, and exclusion of alternative granulomatous causes. | V07_SRC_2020_ATS_SARCOIDOSIS_GUIDELINE | Abstract; Diagnosis section | Sarcoidosis criteria prompt | Platform cannot confirm criteria are satisfied. | sarcoidosis differential parity | mapped_targeted_review | clears_structural_use |
| V07_CLAIM_SARC_002 | Sarcoidosis diagnosis is never fully secure because objective measures for satisfying each criterion are not established. | V07_SRC_2020_ATS_SARCOIDOSIS_GUIDELINE | Abstract; Diagnosis section | Diagnostic uncertainty | Supports uncertainty preservation. | sarcoidosis differential parity | mapped_targeted_review | clears_structural_use |
| V07_CLAIM_SARC_003 | Alternative granulomatous causes must be considered and reliably excluded in suspected or atypical sarcoidosis. | V07_SRC_2020_ATS_SARCOIDOSIS_GUIDELINE | Exclusion of alternative causes section | Mimic visibility | Platform cannot exclude alternatives. | sarcoidosis differential parity | mapped_targeted_review | clears_structural_use |
| V07_CLAIM_SARC_004 | Histopathology alone cannot distinguish sarcoidosis from all other granulomatous diseases. | V07_SRC_2020_ATS_SARCOIDOSIS_GUIDELINE | Histopathology; Exclusion of alternative causes | Pathology limitation | Requires clinical/MDD integration. | sarcoidosis differential parity | mapped_targeted_review | clears_structural_use |
| V07_CLAIM_SARC_005 | Infectious mimics of sarcoidosis include tuberculosis, nontuberculous mycobacteria, fungi, and other infections. | V07_SRC_2020_ATS_SARCOIDOSIS_GUIDELINE | Exclusion of alternative causes; Table 3 | Infection mimic prompt | Infection source still needed for broader v0.7 infection parity. | sarcoidosis differential parity | mapped_targeted_review | clears_structural_use |
| V07_CLAIM_SARC_006 | Noninfectious mimics include lymphoma, sarcoid-like reaction to tumor, HP, pneumoconiosis/beryllium, drug-induced granulomatous disease, and immune disorders. | V07_SRC_2020_ATS_SARCOIDOSIS_GUIDELINE | Table 3; Table 4 | Noninfectious mimic prompt | Some domains need primary sources before their own parity. | sarcoidosis differential parity | mapped_targeted_review | clears_structural_use |
| V07_CLAIM_SARC_007 | Some high-suspicion sarcoidosis presentations may not require lymph node sampling, but follow-up is required. | V07_SRC_2020_ATS_SARCOIDOSIS_GUIDELINE | Summary of Recommendations; Question 1 | Sampling boundary | Platform cannot decide sampling. | sarcoidosis differential parity | mapped_targeted_review | blocks_clinical_reviewed |
| V07_CLAIM_SARC_008 | In asymptomatic bilateral hilar lymphadenopathy, the guideline makes no recommendation for or against lymph node sampling and close follow-up may be reasonable. | V07_SRC_2020_ATS_SARCOIDOSIS_GUIDELINE | Summary of Recommendations; Question 1 | Sampling uncertainty | Platform cannot decide biopsy or follow-up. | sarcoidosis differential parity | mapped_targeted_review | blocks_clinical_reviewed |
| V07_CLAIM_OCC_001 | Occupational ILD / pneumoconiosis / asbestosis reasoning requires a dedicated primary source before parity expansion. | internal_governance_only | v0.7.1 source debt register | Source-needed boundary | Cannot open occupational parity yet. | future occupational ILD parity | internal_governance_only | blocks_domain_lock |
| V07_CLAIM_DRUG_001 | Drug toxicity reasoning requires a dedicated primary source before domain parity expansion. | internal_governance_only | v0.7.1 source debt register | Source-needed boundary | Drug toxicity may remain visible as mimic but not expanded as domain. | future drug toxicity parity | internal_governance_only | blocks_domain_lock |
| V07_CLAIM_ASP_001 | Aspiration-related ILD reasoning requires a dedicated primary source before domain parity expansion. | internal_governance_only | v0.7.1 source debt register | Source-needed boundary | Aspiration may remain visible as mimic but not expanded as domain. | future aspiration parity | internal_governance_only | blocks_domain_lock |
| V07_CLAIM_AUTH_001 | Differential reasoning is not differential diagnosis authority. | internal_governance_only | v0.7.0 entry gate; v0.7.1 source anchor map | Authority boundary | Applies across all v0.7 files. | all v0.7 files | internal_governance_only | clears_structural_use |
| V07_CLAIM_AUTH_002 | Available source is not mapped source; mapped source is not clinical review. | internal_governance_only | v0.7.1 source anchor map | Source governance | Applies across all v0.7 files. | all v0.7 files | internal_governance_only | clears_structural_use |
| V07_CLAIM_AUTH_003 | Treatment-related claims are not allowed in v0.7 differential reasoning. | internal_governance_only | v0.7.0 authority constraints | Treatment boundary | Even if source discusses treatment, v0.7 does not. | all v0.7 files | internal_governance_only | blocks_treatment_authority |
| V07_CLAIM_AUTH_004 | Public-ready claims are not allowed in v0.7. | internal_governance_only | v0.7.0 authority constraints | Public readiness boundary | No patient-facing use. | all v0.7 files | internal_governance_only | blocks_public_ready |

---

## 6. Claim Families Cleared for Internal Structural Use

The following claim families are now cleared for internal, non-authoritative structural drafting.

| Claim Family | Status |
|---|---|
| HP as newly identified ILD differential | cleared_for_structural_use |
| Fibrotic vs nonfibrotic HP distinction | cleared_for_structural_use |
| HP exposure history prompt | cleared_for_structural_use |
| HP serum IgG / BAL evidence prompt | cleared_for_structural_use_with_non_authority |
| HP HRCT small-airway features | cleared_for_structural_use |
| Fibrotic HP vs IPF/IIP overlap | cleared_for_structural_use |
| IIP family taxonomy | cleared_for_structural_use |
| NSIP as distinct clinicopathologic entity | cleared_for_structural_use |
| NSIP secondary cause visibility | cleared_for_structural_use |
| OP pattern and fibrotic OP overlap | cleared_for_structural_use |
| Coexisting patterns | cleared_for_structural_use |
| Unclassifiable IIP | cleared_for_structural_use |
| SARD-ILD risk/scope context | cleared_for_structural_use |
| SARD-ILD HRCT/PFT screening-monitoring context | cleared_for_structural_use_with_no_ordering_authority |
| Sarcoidosis criteria prompt | cleared_for_structural_use |
| Sarcoidosis diagnostic uncertainty | cleared_for_structural_use |
| Granulomatous mimic visibility | cleared_for_structural_use |

---

## 7. Claims Not Cleared for Domain Lock

The following are not yet cleared for domain lock.

| Claim Area | Reason |
|---|---|
| Full HP parity seal | needs HP parity file and test cases |
| Full CTD-ILD parity seal | needs CTD-ILD prompt parity file and test cases |
| Full NSIP/OP/unclassifiable parity seal | needs domain parity file and test cases |
| Full sarcoidosis differential parity seal | needs domain parity file and test cases |
| Occupational ILD parity | primary source needed |
| Drug toxicity parity | primary source needed |
| Aspiration-related ILD parity | primary source needed |
| Infection overlay parity | broader infection source needed |
| Treatment or management recommendations | not allowed |
| Biopsy decision automation | not allowed |
| Public-ready output | not allowed |
| Clinically reviewed status | false |

---

## 8. Updated v0.7 Source Debt Status

| Debt ID | Previous Status | v0.7.2 Status | Still Blocks |
|---|---|---|---|
| V07_DEBT_HP_001 | mapping_pending | initial key claims mapped | HP parity lock; HP seal |
| V07_DEBT_IIP_001 | mapping_pending | initial key claims mapped | IIP parity lock; IIP seal |
| V07_DEBT_SARD_001 | mapping_pending | initial key claims mapped | CTD-ILD parity lock; CTD-ILD seal |
| V07_DEBT_SARC_001 | mapping_pending | initial key claims mapped | sarcoidosis parity lock; sarcoidosis seal |
| V07_DEBT_OCC_001 | source_needed | source_needed | occupational ILD parity |
| V07_DEBT_DRUG_001 | source_needed | source_needed | drug toxicity parity |
| V07_DEBT_ASP_001 | source_needed | source_needed | aspiration parity |
| V07_DEBT_INF_001 | source_needed | source_needed | infection mimic/overlay parity |

---

## 9. Authority Status After v0.7.2

| Field | Status |
|---|---|
| v0_7_structural_entry | active |
| v0_7_source_anchor_map | present |
| v0_7_claim_mapping | initial_partial_complete |
| clinically_reviewed | false |
| public_ready | false |
| diagnostic_authority | none |
| treatment_authority | none |
| biopsy_decision_authority | none |
| patient_facing_use | not_allowed |
| MDD_replacement | not_allowed |
| clinician_replacement | not_allowed |

---

## 10. Next Step Decision

Because initial claim mapping is now present, v0.7 may proceed to a family matrix.

The next recommended step is:

- v0.7.3 — Non-UIP Differential Reasoning Family Matrix

v0.7.3 should define differential families, reasoning states, missing evidence states, and overlap relationships.

It should not yet write full HP, CTD-ILD, NSIP/OP, or sarcoidosis parity rules.

It should remain:

- diagnostic_authority: none,
- treatment_authority: none,
- public_ready: false,
- clinically_reviewed: false.

---

## 11. Governance Statement

This claim-to-source table reduces v0.7 source-review debt before domain rules are written.

It does not diagnose.  
It does not treat.  
It does not decide biopsy.  
It does not confirm HP.  
It does not confirm CTD-ILD.  
It does not confirm NSIP.  
It does not confirm OP.  
It does not confirm sarcoidosis.  
It does not confirm occupational ILD.  
It does not confirm drug toxicity.  
It does not claim public readiness.

Current v0.7 status:

- non_uip_differential_structural_entry: active
- source_review: targeted_partial
- claim_mapping: initial_partial_complete
- clinically_reviewed: false
- public_ready: false
- diagnostic_authority: none
- treatment_authority: none

The platform remains an evidence-governed clinical reasoning platform.

The v0.7 rule remains:

> “Differential reasoning is not differential diagnosis authority.”