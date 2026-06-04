# ILD Reasoning Platform — Non-UIP Fibrotic ILD Source Anchor Map / Differential Source Debt Register v1

Version: v0.7.1  
Status: source_anchor_map_and_differential_source_debt_register  
Scope: Non-UIP fibrotic ILD source roles, differential families, and source debt  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This document defines the source anchor map and source-debt register for v0.7 — Non-UIP Fibrotic ILD Differential Reasoning Expansion.

It follows:

- `docs/navigation/non_uip_fibrotic_ild_differential_reasoning_entry_gate_v1.md`

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

Its purpose is to map source roles before differential reasoning rules are written.

The controlling v0.7 principle remains:

> “Differential reasoning is not differential diagnosis authority.”

The inherited source-governance rule remains:

> “A structural seal is not a clinical source-review seal.”

---

## 2. Relationship to Prior Layers

v0.7.1 inherits:

- v0.3 Superimposed Events Core,
- v0.4 Evidence Layer / Source Review Governance,
- v0.5 Test Case Coverage Expansion,
- v0.6 UIP Parity Seal,
- v0.6.R1 Source Review Debt Register,
- v0.6.R2 Claim-to-Source Mapping Table,
- v0.6.R3 Source Status Correction / Backfill Lock,
- v0.7.0 Non-UIP Fibrotic ILD Differential Reasoning Entry Gate.

Required inherited constraints:

| Constraint | Required State |
|---|---|
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| clinically_reviewed | false |
| source_review_debt_visible | true |
| claim_to_source_mapping_required | true |
| missing_evidence_visible | true |
| mimics_visible | true |
| MDD_prompt_visible_where_relevant | true |
| urgent_review_prompt_visible_where_relevant | true |

---

## 3. Source Anchor Status Summary

| Source ID | Source | Source Role | Initial Status |
|---|---|---|---|
| V07_SRC_2020_ATS_JRS_ALAT_HP_GUIDELINE | Raghu et al. 2020 ATS/JRS/ALAT Diagnosis of Hypersensitivity Pneumonitis in Adults | primary HP source | uploaded_available_primary_source_mapping_pending |
| V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION | Travis et al. 2013 ATS/ERS Update of the International Multidisciplinary Classification of the Idiopathic Interstitial Pneumonias | primary IIP / NSIP / OP / unclassifiable source | uploaded_available_primary_source_mapping_pending |
| V07_SRC_2023_ACR_CHEST_SARD_ILD_SCREEN_MONITOR | 2023 ACR/CHEST Guideline for Screening and Monitoring ILD in Systemic Autoimmune Rheumatic Diseases | primary SARD-ILD / CTD-ILD source | uploaded_available_primary_source_mapping_pending |
| V07_SRC_2020_ATS_SARCOIDOSIS_GUIDELINE | Crouser et al. 2020 ATS Diagnosis and Detection of Sarcoidosis Guideline | primary sarcoidosis / granulomatous differential source | uploaded_available_primary_source_mapping_pending |
| V07_SRC_2020_HP_CLINICIAN_SUMMARY | Koster et al. 2021 clinician summary of 2020 ATS/JRS/ALAT HP guideline | auxiliary HP summary source | uploaded_available_auxiliary_source |
| UIP_SRC_2018_ATS_ERS_JRS_ALAT_DX | Raghu et al. 2018 ATS/ERS/JRS/ALAT IPF Diagnosis Guideline | UIP boundary inheritance source | mapped_in_v0_6_R2 |
| UIP_SRC_2022_ATS_ERS_JRS_ALAT_IPF_PPF | Raghu et al. 2022 ATS/ERS/JRS/ALAT IPF Update and PPF Guideline | PPF / progression context inheritance source | mapped_in_v0_6_R2 |
| UIP_SRC_INTERNAL_V06_R1_R2_R3_BACKFILL | Internal v0.6.R1/R2/R3 backfill chain | source debt discipline inheritance | sealed_internal_governance |

Status rule:

- uploaded_available does not mean claim_mapped,
- claim_mapped does not mean clinically_reviewed,
- clinically_reviewed remains false,
- public_ready remains false.

---

## 4. Source Role Boundaries

### 4.1 HP Guideline Source Boundary

Allowed role:

- primary source for HP differential reasoning,
- fibrotic vs nonfibrotic HP distinction,
- exposure history and inciting antigen reasoning,
- serum IgG exposure-support reasoning,
- BAL lymphocytosis reasoning,
- HP HRCT feature mapping,
- fibrotic HP vs UIP/IPF/NSIP overlap reasoning,
- HP MDD prompt logic.

Blocked role:

- automated HP diagnosis,
- automated biopsy decision,
- treatment recommendation,
- public-ready HP triage,
- replacement of radiologist/pathologist/pulmonologist/MDD.

---

### 4.2 IIP Classification Source Boundary

Allowed role:

- primary source for IIP family structure,
- idiopathic NSIP reasoning,
- organizing pneumonia reasoning,
- smoking-related IIP reasoning,
- acute/subacute IIP context,
- unclassifiable IIP reasoning,
- coexisting pattern reasoning,
- disease behavior classification,
- MDD/dynamic integrated diagnosis support.

Blocked role:

- automated IIP diagnosis,
- treatment-goal automation,
- disease behavior as treatment recommendation,
- biopsy decision automation,
- clinical product status.

---

### 4.3 SARD-ILD Source Boundary

Allowed role:

- primary source for SARD-ILD context,
- RA / systemic sclerosis / idiopathic inflammatory myopathy / MCTD / Sjögren ILD risk framing,
- HRCT and PFT screening/monitoring context,
- shared decision-making and patient-specific application,
- CTD-ILD missing evidence prompts,
- rheumatology/pulmonology co-management visibility.

Blocked role:

- automated CTD-ILD diagnosis,
- automated screening order,
- automated monitoring schedule,
- treatment recommendation,
- replacement of rheumatology or pulmonology review.

---

### 4.4 Sarcoidosis Source Boundary

Allowed role:

- primary source for sarcoidosis / granulomatous differential reasoning,
- compatible clinical presentation prompt,
- nonnecrotizing granulomatous inflammation prompt,
- alternative granulomatous cause exclusion prompt,
- sarcoidosis uncertainty framing,
- lymphadenopathy / perilymphatic / extrapulmonary clue visibility,
- infection / malignancy / berylliosis / HP / drug reaction mimic visibility.

Blocked role:

- automated sarcoidosis diagnosis,
- automated tissue sampling decision,
- treatment recommendation,
- exclusion of alternative granulomatous causes without evidence,
- replacement of MDD or clinical follow-up.

---

## 5. Differential Family Source Map

| Differential Family | Primary Source | Auxiliary Source(s) | Mapping Status | v0.7 Status |
|---|---|---|---|---|
| Fibrotic hypersensitivity pneumonitis | V07_SRC_2020_ATS_JRS_ALAT_HP_GUIDELINE | V07_SRC_2020_HP_CLINICIAN_SUMMARY; V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION | mapping_pending | candidate_domain |
| Nonfibrotic HP as overlap/mimic | V07_SRC_2020_ATS_JRS_ALAT_HP_GUIDELINE | V07_SRC_2020_HP_CLINICIAN_SUMMARY | mapping_pending | candidate_domain |
| CTD-ILD / SARD-ILD | V07_SRC_2023_ACR_CHEST_SARD_ILD_SCREEN_MONITOR | UIP_SRC_2018_ATS_ERS_JRS_ALAT_DX; V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION | mapping_pending | candidate_domain |
| Fibrotic NSIP | V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION | V07_SRC_2023_ACR_CHEST_SARD_ILD_SCREEN_MONITOR | mapping_pending | candidate_domain |
| Organizing pneumonia / fibrotic OP overlap | V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION | V07_SRC_2023_ACR_CHEST_SARD_ILD_SCREEN_MONITOR | mapping_pending | candidate_domain |
| Unclassifiable IIP / mixed pattern ILD | V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION | internal v0.3 overlap governance | mapping_pending | candidate_domain |
| Sarcoidosis / sarcoid-like granulomatous disease | V07_SRC_2020_ATS_SARCOIDOSIS_GUIDELINE | V07_SRC_2020_ATS_JRS_ALAT_HP_GUIDELINE | mapping_pending | candidate_domain |
| Smoking-related IIP / CPFE context | V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION | UIP_SRC_2022_ATS_ERS_JRS_ALAT_IPF_PPF | mapping_pending | candidate_or_deferred |
| Occupational ILD / pneumoconiosis / asbestosis | source_needed | V07_SRC_2020_ATS_SARCOIDOSIS_GUIDELINE for granulomatous differential only | source_needed | deferred_candidate_domain |
| Drug toxicity / therapy-related ILD | source_needed | V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION; V07_SRC_2020_ATS_SARCOIDOSIS_GUIDELINE | source_needed | deferred_candidate_domain |
| Aspiration-related ILD / OP overlap | source_needed | V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION; V07_SRC_2020_ATS_SARCOIDOSIS_GUIDELINE | source_needed | deferred_candidate_domain |
| Infection as mimic / overlay | source_needed | V07_SRC_2020_ATS_SARCOIDOSIS_GUIDELINE for granulomatous infection differential | source_needed | deferred_candidate_domain |

---

## 6. Claim Families Requiring Mapping

### 6.1 HP Claim Families

| Claim Family | Required Source | Mapping Status |
|---|---|---|
| HP must be considered in newly identified ILD differential | V07_SRC_2020_ATS_JRS_ALAT_HP_GUIDELINE | pending |
| HP classified into fibrotic and nonfibrotic phenotypes | V07_SRC_2020_ATS_JRS_ALAT_HP_GUIDELINE | pending |
| Exposure history is central but exposure may remain unidentified | V07_SRC_2020_ATS_JRS_ALAT_HP_GUIDELINE | pending |
| Serum IgG supports exposure investigation but does not diagnose alone | V07_SRC_2020_ATS_JRS_ALAT_HP_GUIDELINE | pending |
| BAL lymphocytosis supports HP evaluation | V07_SRC_2020_ATS_JRS_ALAT_HP_GUIDELINE | pending |
| Fibrotic HP may mimic IPF or other IIP | V07_SRC_2020_ATS_JRS_ALAT_HP_GUIDELINE | pending |
| Mosaic attenuation / air trapping / three-density pattern support HP-like reasoning | V07_SRC_2020_ATS_JRS_ALAT_HP_GUIDELINE | pending |
| HP requires MDD integration | V07_SRC_2020_ATS_JRS_ALAT_HP_GUIDELINE | pending |

---

### 6.2 IIP / NSIP / OP Claim Families

| Claim Family | Required Source | Mapping Status |
|---|---|---|
| IIP classification includes major, rare, and unclassifiable IIP | V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION | pending |
| Idiopathic NSIP is a distinct clinicopathologic entity | V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION | pending |
| NSIP may occur in CVD, HP, drug toxicity, and familial fibrosis contexts | V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION | pending |
| OP may be idiopathic or secondary and may overlap fibrosis | V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION | pending |
| Coexisting HRCT/pathologic patterns can occur | V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION | pending |
| Unclassifiable IIP may result from insufficient data or discordance | V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION | pending |
| MDD is dynamic and integrates clinical, radiologic, and pathologic data | V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION | pending |

---

### 6.3 SARD-ILD / CTD-ILD Claim Families

| Claim Family | Required Source | Mapping Status |
|---|---|---|
| RA, systemic sclerosis, IIM, MCTD, and Sjögren are SARDs at risk for ILD | V07_SRC_2023_ACR_CHEST_SARD_ILD_SCREEN_MONITOR | pending |
| HRCT and PFTs are used in SARD-ILD screening/monitoring context | V07_SRC_2023_ACR_CHEST_SARD_ILD_SCREEN_MONITOR | pending |
| SARD-ILD recommendations are voluntary guidance applied by clinicians | V07_SRC_2023_ACR_CHEST_SARD_ILD_SCREEN_MONITOR | pending |
| Screening and monitoring should involve patient-specific context and shared decision-making | V07_SRC_2023_ACR_CHEST_SARD_ILD_SCREEN_MONITOR | pending |
| Surgical lung biopsy is not for routine screening in SARD-ILD | V07_SRC_2023_ACR_CHEST_SARD_ILD_SCREEN_MONITOR | pending |
| CTD-ILD context must not be hidden when autoimmune evidence is missing | V07_SRC_2023_ACR_CHEST_SARD_ILD_SCREEN_MONITOR plus internal governance | pending |

---

### 6.4 Sarcoidosis Claim Families

| Claim Family | Required Source | Mapping Status |
|---|---|---|
| Sarcoidosis diagnosis is based on compatible clinical presentation | V07_SRC_2020_ATS_SARCOIDOSIS_GUIDELINE | pending |
| Sarcoidosis diagnosis often involves nonnecrotizing granulomatous inflammation | V07_SRC_2020_ATS_SARCOIDOSIS_GUIDELINE | pending |
| Alternative granulomatous causes must be excluded | V07_SRC_2020_ATS_SARCOIDOSIS_GUIDELINE | pending |
| Sarcoidosis diagnosis is never fully secure | V07_SRC_2020_ATS_SARCOIDOSIS_GUIDELINE | pending |
| Infection, malignancy, berylliosis, HP, drug reaction, and immune disorders can mimic sarcoidosis | V07_SRC_2020_ATS_SARCOIDOSIS_GUIDELINE | pending |
| Lymph node sampling decisions are context-dependent and not automatic | V07_SRC_2020_ATS_SARCOIDOSIS_GUIDELINE | pending |

---

## 7. Source Debt Register

| Debt ID | Source | Debt Description | Current Status | Blocks |
|---|---|---|---|---|
| V07_DEBT_HP_001 | V07_SRC_2020_ATS_JRS_ALAT_HP_GUIDELINE | HP claim-to-source mapping not yet created | mapping_pending | HP parity rules; HP test cases; HP seal |
| V07_DEBT_IIP_001 | V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION | IIP/NSIP/OP/unclassifiable claim mapping not yet created | mapping_pending | IIP parity rules; NSIP/OP test cases; IIP seal |
| V07_DEBT_SARD_001 | V07_SRC_2023_ACR_CHEST_SARD_ILD_SCREEN_MONITOR | SARD-ILD claim mapping not yet created | mapping_pending | CTD-ILD prompt parity; CTD-ILD test cases |
| V07_DEBT_SARC_001 | V07_SRC_2020_ATS_SARCOIDOSIS_GUIDELINE | Sarcoidosis claim mapping not yet created | mapping_pending | sarcoidosis differential parity; sarcoidosis test cases |
| V07_DEBT_OCC_001 | occupational ILD source not selected | occupational/asbestos/pneumoconiosis source missing | source_needed | occupational ILD parity |
| V07_DEBT_DRUG_001 | drug-induced ILD source not selected | drug toxicity / therapy-related ILD source missing | source_needed | drug toxicity parity |
| V07_DEBT_ASP_001 | aspiration/OP source not selected | aspiration-related ILD / OP overlap source missing | source_needed | aspiration parity |
| V07_DEBT_INF_001 | infection mimic source not selected | infection overlay source not selected | source_needed | infection mimic parity |

Debt rule:

- mapping_pending does not block structural entry,
- mapping_pending blocks structural seal,
- source_needed blocks domain parity expansion,
- clinically_reviewed remains false.

---

## 8. Domains Cleared for Structural Drafting

The following domains are cleared only for structural draft work:

| Domain | Cleared For Drafting? | Conditions |
|---|---|---|
| Fibrotic HP | yes | claim mapping required before parity lock |
| CTD-ILD / SARD-ILD | yes | claim mapping required before parity lock |
| Fibrotic NSIP | yes | claim mapping required before parity lock |
| Organizing pneumonia / fibrotic OP overlap | yes | claim mapping required before parity lock |
| Sarcoidosis / granulomatous differential | yes | claim mapping required before parity lock |
| Unclassifiable IIP | yes | claim mapping required before parity lock |
| Occupational ILD | no | primary source required first |
| Drug toxicity | no | primary source required first |
| Aspiration-related ILD | no | primary source required first |
| Infection mimic / overlay | no | primary source required first |

---

## 9. Required Status Labels for Future v0.7 Files

Every future v0.7 file must include:

| Field | Required Value |
|---|---|
| Public Ready | false |
| Diagnostic Authority | none |
| Treatment Authority | none |
| Clinically Reviewed | false |
| Source Review Status | declared |
| Claim Mapping Status | declared |
| Missing Evidence Visible | true |
| Mimics Visible | true |
| MDD Prompt Visible Where Relevant | true |
| Urgent Review Prompt Visible Where Relevant | true |

No v0.7 file may omit source status.

---

## 10. v0.7 Claim Mapping Requirements

Before any v0.7 domain-specific parity file can be locked, it must include or reference:

- claim_id,
- claim_text,
- source_id,
- source_passage_or_section,
- claim_scope,
- limitation,
- affected_file,
- review_status,
- blocking_status.

Mapped claims must distinguish:

- primary source claim,
- auxiliary source claim,
- internal governance claim,
- source-needed claim,
- deferred claim,
- not-allowed claim.

---

## 11. Authority Locks

The following remain locked across v0.7:

| Claim Type | Status |
|---|---|
| final diagnosis | not_allowed |
| disease confirmation | not_allowed |
| treatment recommendation | not_allowed |
| biopsy decision | not_allowed |
| public-ready interpretation | not_allowed |
| patient-facing use | not_allowed |
| guideline-complete claim | not_allowed |
| clinically_reviewed claim | not_allowed |
| MDD replacement | not_allowed |
| clinician replacement | not_allowed |

---

## 12. Drift Risks Blocked

| Drift Risk | Source Map Block |
|---|---|
| v0.7 repeats v0.6 source debt problem | source debt register created at entry |
| differential reasoning becomes diagnosis | authority locks |
| source availability mistaken for source mapping | status distinction |
| claim mapping mistaken for clinical review | clinically_reviewed false |
| HP guideline used to diagnose HP automatically | role boundary |
| SARD-ILD guideline used to order screening automatically | role boundary |
| sarcoidosis guideline used to confirm sarcoidosis | role boundary |
| IIP classification used to force NSIP/OP labels | role boundary |
| occupational/drug/aspiration domains opened without sources | deferred source-needed status |
| treatment logic leaks in | treatment_authority none |
| public readiness implied | public_ready false |

---

## 13. Acceptance Criteria

v0.7.1 is accepted only if:

- all uploaded v0.7 sources are listed,
- source roles are defined,
- primary vs auxiliary vs deferred sources are separated,
- differential family source map exists,
- source debt register exists,
- HP / IIP / SARD-ILD / sarcoidosis claim families are listed,
- occupational / drug / aspiration / infection sources are marked as needed,
- structural drafting boundaries are clear,
- claim mapping is required before domain locks,
- diagnostic_authority remains none,
- treatment_authority remains none,
- public_ready remains false,
- clinically_reviewed remains false.

---

## 14. Next Step

The next recommended step is:

- v0.7.2 — Non-UIP Differential Claim-to-Source Mapping Table

v0.7.2 should map initial claim families for:

- HP,
- IIP / NSIP / OP / unclassifiable IIP,
- SARD-ILD / CTD-ILD,
- sarcoidosis / granulomatous differential.

It should not yet create differential behavior rules.

It should not create diagnostic authority.

---

## 15. Governance Statement

This source anchor map opens v0.7 source governance.

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

The platform remains an evidence-governed clinical reasoning platform.

The source-governance rule is:

> “Available source is not mapped source. Mapped source is not clinical review.”

The v0.7 reasoning rule is:

> “Differential reasoning is not differential diagnosis authority.”