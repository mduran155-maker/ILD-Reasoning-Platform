# ILD Reasoning Platform — UIP Source Review Debt Register / Claim-to-Source Backfill Gate v1

Version: v0.6.R1  
Status: source_review_debt_register  
Scope: UIP parity source-review debt and claim-to-source backfill gate  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This document records source-review debt created during v0.6 — UIP Parity Upgrade.

It does not invalidate the v0.6 structural governance chain.

It clarifies that v0.6 was structurally sealed as a reasoning-governance layer, not clinically reviewed as a public-ready or diagnostic source layer.

This document prevents architectural momentum from being mistaken for completed clinical source review.

The platform principle remains:

> “It teaches clinicians to read change before naming disease.”

For source governance, the added rule is:

> “A structural seal is not a clinical source-review seal.”

---

## 2. Why This Register Exists

v0.6 created a complete UIP parity governance chain:

- entry gate,
- source anchor map,
- pattern boundary matrix,
- reasoning parity rules,
- mimic and superimposed-process parity,
- temporal comparison parity,
- MDD and missing-evidence parity,
- upgraded test cases,
- lock checklist,
- structural seal.

However, not every external source anchor has been fully claim-mapped.

Therefore, v0.6 must be treated as:

- structural_governance_complete: true
- clinical_source_review_complete: false
- public_ready: false
- diagnostic_authority: none
- treatment_authority: none

This register makes that distinction explicit.

---

## 3. Source Review Status Summary

| Source ID | Source | Current Status | Use Allowed Now |
|---|---|---|---|
| UIP_SRC_2018_FLEISCHNER_WHITE_PAPER | Lynch et al. 2018 Fleischner Society IPF Diagnostic Criteria White Paper | uploaded_available_verified_for_current_workflow | yes, as verified comparative anchor |
| UIP_SRC_2020_FLEISCHNER_ILA_POSITION_PAPER | Fleischner Society 2020 ILA Position Paper | uploaded_available_verified_for_current_workflow | yes, as auxiliary ILA / early fibrotic abnormality anchor |
| UIP_SRC_2018_ATS_ERS_JRS_ALAT_DX | ATS/ERS/JRS/ALAT 2018 IPF Diagnosis Guideline | referenced_anchor_pending_claim_mapping | limited pending backfill |
| UIP_SRC_2022_ATS_ERS_JRS_ALAT_IPF_PPF | ATS/ERS/JRS/ALAT 2022 IPF Update and PPF Guideline | referenced_anchor_pending_targeted_review | limited pending backfill |

---

## 4. Source Review Debt Items

### 4.1 Debt Item: ATS/ERS/JRS/ALAT 2022 IPF/PPF Guideline

source_review_debt_item:

- source_id: UIP_SRC_2022_ATS_ERS_JRS_ALAT_IPF_PPF
- source_role_in_v0_6: current_update_source_hierarchy_anchor
- affected_claims:
  - PPF context
  - updated IPF/PPF source hierarchy
  - current guideline-sensitive framing
  - progression-related terminology
  - any claim implying 2022 guideline alignment
- current_status: targeted_review_pending
- full_text_reviewed: false
- claim_to_source_mapping_complete: false
- blocking:
  - any public-facing guideline parity claim
  - any clinical_reviewed status
  - any treatment-related or management-related extension
  - any claim that v0.6 is guideline-complete
- not_blocking:
  - structural governance seal
  - internal reasoning draft status
  - non-authoritative test design
- priority: high

Required action:

- identify all v0.6 claims that depend on ATS/ERS/JRS/ALAT 2022,
- isolate the sections needed for those claims,
- review only the necessary source sections,
- create claim-to-source mapping rows,
- update source status from `targeted_review_pending` to `targeted_review_complete` only after review.

---

### 4.2 Debt Item: ATS/ERS/JRS/ALAT 2018 IPF Diagnosis Guideline

source_review_debt_item:

- source_id: UIP_SRC_2018_ATS_ERS_JRS_ALAT_DX
- source_role_in_v0_6: official_guideline_anchor_for_uip_pattern_categories
- affected_claims:
  - UIP HRCT category definitions
  - probable UIP boundary
  - indeterminate for UIP
  - alternative diagnosis pattern
  - MDD-sensitive diagnostic pathway framing
- current_status: claim_mapping_pending
- full_text_reviewed: partial_or_pending
- claim_to_source_mapping_complete: false
- blocking:
  - clinical_reviewed status for pattern-boundary matrix
  - public-facing UIP parity claim
  - any claim that v0.6 fully reflects official guideline categories
- not_blocking:
  - structural pattern-boundary draft
  - non-authoritative parity testing
- priority: high

Required action:

- map each UIP pattern-boundary claim to source passage,
- mark whether claim comes from official guideline, Fleischner comparative paper, or internal governance,
- keep disagreement or terminology differences visible.

---

### 4.3 Debt Item: Fleischner 2018 IPF Diagnostic Criteria White Paper

source_review_debt_item:

- source_id: UIP_SRC_2018_FLEISCHNER_WHITE_PAPER
- source_role_in_v0_6: verified_comparative_anchor
- affected_claims:
  - probable UIP as possible high-confidence pathway in correct clinical context
  - clinical context dependency
  - MDD importance
  - working diagnosis reviewability
  - re-review over time
  - alternative cause exclusion
- current_status: uploaded_and_review_usable
- full_text_reviewed: partial_targeted_review_complete
- claim_to_source_mapping_complete: partial
- blocking:
  - none for internal structural governance use
- still_required:
  - formal claim-to-source table
  - exact claim scope limits
  - distinction from ATS official guideline authority
- priority: medium_high

Required action:

- convert current use into explicit claim-to-source rows,
- maintain it as comparative anchor, not sole official guideline authority.

---

### 4.4 Debt Item: Fleischner 2020 ILA Position Paper

source_review_debt_item:

- source_id: UIP_SRC_2020_FLEISCHNER_ILA_POSITION_PAPER
- source_role_in_v0_6: auxiliary_ila_early_fibrotic_abnormality_anchor
- affected_claims:
  - incidental ILA is not automatically clinical ILD
  - subpleural fibrotic ILA progression risk
  - follow-up uncertainty
  - clinical evaluation requirement
  - non-diagnostic handling of incidental findings
- current_status: uploaded_and_review_usable
- full_text_reviewed: partial_targeted_review_complete
- claim_to_source_mapping_complete: partial
- blocking:
  - any future ILA parity seal
  - any public-facing ILA management claim
- not_blocking:
  - v0.6 auxiliary ILA test case framing
- priority: medium

Required action:

- keep ILA as auxiliary source,
- do not let ILA source become UIP diagnostic criteria source,
- map incidental ILA claims separately if expanded later.

---

## 5. Claim-to-Source Mapping Required Before Clinical Review

Before any v0.6 file can be marked `clinically_reviewed: true`, the following mapping must exist.

| Claim Family | Required Source Mapping |
|---|---|
| UIP HRCT category definitions | official guideline source passage |
| Probable UIP boundary | official guideline source passage plus comparative Fleischner context if used |
| Indeterminate for UIP | official guideline source passage |
| Alternative diagnosis pattern | official guideline source passage |
| MDD role | official guideline and/or Fleischner source passage |
| Working diagnosis reviewability | Fleischner source passage |
| PPF context | ATS/ERS/JRS/ALAT 2022 source passage |
| ILA incidental finding distinction | Fleischner 2020 source passage |
| ILA progression / follow-up uncertainty | Fleischner 2020 source passage |
| Treatment-related claims | not allowed in v0.6 |

---

## 6. Backfill Gate Rules

The following rules apply immediately.

- v0_6_structural_seal_valid: true
- v0_6_clinical_reviewed: false
- v0_6_public_ready: false
- v0_6_diagnostic_authority: none
- v0_6_treatment_authority: none
- v0_7_entry_allowed: deferred_until_source_review_debt_triaged

v0.7 should not open until at least the high-priority source debt items are triaged.

Required before v0.7:

- ATS 2022 affected claims listed,
- ATS 2018 UIP category claims mapped or explicitly deferred,
- Fleischner 2018 claim-to-source rows created,
- status labels clarified across v0.6 documents,
- no file implies clinical source review completion.

---

## 7. Status Label Correction

The following status distinction must be preserved.

| Label | Meaning |
|---|---|
| structural_sealed | The document chain is organized, internally consistent, and governance-constrained |
| source_reviewed | The relevant source passages have been reviewed for specific claims |
| claim_mapped | Each claim is linked to a source passage and limitation |
| clinically_reviewed | A qualified clinical review has assessed the content |
| public_ready | Not allowed at current stage |

v0.6 currently supports:

- structural_sealed: true
- source_reviewed: partial
- claim_mapped: partial
- clinically_reviewed: false
- public_ready: false

---

## 8. Drift Risks Blocked

This register blocks the following risks:

| Drift Risk | Register Block |
|---|---|
| Architecture substitutes for source review | debt explicitly listed |
| Seal is mistaken for clinical validation | structural vs clinical seal separated |
| Referenced source becomes reviewed source | source status visible |
| ATS 2022 anchor is overclaimed | targeted review required |
| Fleischner 2018 becomes official guideline substitute | comparative role preserved |
| ILA source becomes UIP diagnostic source | auxiliary role preserved |
| v0.7 opens on unpaid source debt | v0.7 deferred until triage |
| public_ready implied | public_ready false |
| diagnostic authority appears | diagnostic_authority none |
| treatment authority appears | treatment_authority none |

---

## 9. Required Next Work

The next work should not be v0.7.

The next work should be:

v0.6.R2 — UIP Claim-to-Source Mapping Table

Minimum rows:

- UIP HRCT category definitions,
- probable UIP boundary,
- indeterminate for UIP,
- alternative diagnosis pattern,
- MDD role,
- working diagnosis reviewability,
- prior / longitudinal re-review,
- ILA non-diagnostic handling,
- ILA progression / follow-up uncertainty,
- PPF context.

Each row should include:

- claim_id,
- claim_text,
- source_id,
- source_status,
- source_passage_or_section,
- claim_scope,
- limitation,
- affects_file,
- review_status,
- blocking_status.

---

## 10. Governance Statement

This register preserves the integrity of v0.6.

It does not weaken the UIP Parity Upgrade.

It prevents the structural seal from being mistaken for clinical review.

The platform remains an evidence-governed clinical reasoning platform.

It does not diagnose.  
It does not treat.  
It is not public-ready.  
It does not replace radiologist interpretation, clinical correlation, pathology, microbiology, pulmonology, rheumatology, occupational medicine, MDD, or urgent clinical assessment.

Its current status is:

- uip_parity_structural_governance: sealed
- uip_source_review: partial
- uip_claim_mapping: pending_backfill
- clinically_reviewed: false
- public_ready: false
- diagnostic_authority: none
- treatment_authority: none

The next correct move is not expansion.

The next correct move is source-review backfill.