# ILD Reasoning Platform — UIP Source Status Correction / Backfill Lock v1

Version: v0.6.R3  
Status: source_status_correction_backfill_lock  
Scope: UIP parity source-status correction after R1/R2 backfill  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This document locks the source-status correction created by v0.6.R1 and v0.6.R2.

It follows:

- `docs/navigation/uip_source_review_debt_register_v1.md`
- `docs/navigation/uip_claim_to_source_mapping_table_v1.md`

v0.6.R1 made source-review debt visible.

v0.6.R2 partially paid down that debt through claim-to-source mapping.

v0.6.R3 corrects the source-status layer and defines what may happen next.

This document does not create diagnostic authority.  
This document does not create treatment authority.  
This document does not create public readiness.  
This document does not make v0.6 clinically reviewed.

The platform principle remains:

> “It teaches clinicians to read change before naming disease.”

For source governance, the controlling rule remains:

> “A structural seal is not a clinical source-review seal.”

---

## 2. Why This Correction Exists

v0.6 was structurally sealed before full claim-to-source backfill was complete.

That created a risk:

- structural completeness could be mistaken for clinical source review,
- source anchors could appear stronger than their reviewed status,
- v0.7 could open while source debt was still ambiguous.

R1 corrected this by creating a debt register.

R2 corrected this further by mapping key UIP claims to source anchors.

R3 now locks the corrected status.

---

## 3. Corrected Source Status Table

| Source ID | Previous Risk | Corrected Status | Role After R3 |
|---|---|---|---|
| UIP_SRC_2018_ATS_ERS_JRS_ALAT_DX | referenced but not fully claim-mapped | uploaded_available_targeted_review_ready; key UIP claims mapped in R2 | primary official diagnostic framework anchor for UIP-facing pattern categories |
| UIP_SRC_2022_ATS_ERS_JRS_ALAT_IPF_PPF | referenced as source hierarchy anchor but not claim-mapped | uploaded_available_targeted_review_ready; key update and PPF claims mapped in R2 | current update and PPF anchor |
| UIP_SRC_2018_FLEISCHNER_WHITE_PAPER | verified comparative anchor but partial mapping | uploaded_available_verified_comparative_anchor; mapping partial | comparative IPF/UIP diagnostic reasoning anchor |
| UIP_SRC_2020_FLEISCHNER_ILA_POSITION_PAPER | auxiliary ILA source but partial mapping | uploaded_available_auxiliary_ila_anchor; mapping partial | incidental ILA / early fibrotic abnormality anchor |
| UIP_SRC_2020_HP_CLINICIAN_SUMMARY | not present in original v0.6 source map | uploaded_available_auxiliary_hp_mimic_anchor | HP mimic and future v0.7 differential reasoning support |
| UIP_SRC_INTERNAL_V03_SUPERIMPOSED_EVENTS_CORE | internal prior seal | sealed_internal_governance | overlap / simultaneous-process reasoning |
| UIP_SRC_INTERNAL_V04_SOURCE_GOVERNANCE | internal prior seal | sealed_internal_governance | source review and limitation governance |
| UIP_SRC_INTERNAL_V05_TEST_COVERAGE_SEAL | internal prior seal | sealed_internal_governance | test coverage, missing evidence, mimic, MDD, urgent review inheritance |
| UIP_INTERNAL_V06_STRUCTURAL_CHAIN | structural seal could be overread | structurally_sealed_not_clinically_reviewed | UIP parity governance chain only |

---

## 4. R1 Debt Register Status After R2

The R1 debt register remains valid.

However, after R2, the following changes are locked:

| Debt Area | R1 State | R3 Locked Interpretation |
|---|---|---|
| ATS 2018 UIP category claims | claim_mapping_pending | key UIP category claims now mapped for internal structural use |
| ATS 2022 update / PPF claims | targeted_review_pending | key update and PPF claims now mapped for internal structural use |
| Fleischner 2018 comparative claims | partial | remains partial verified comparative mapping |
| Fleischner 2020 ILA claims | partial | remains partial auxiliary mapping |
| HP mimic source | not listed | added as auxiliary HP mimic source |
| clinical_reviewed | false | remains false |
| public_ready | false | remains false |
| diagnostic_authority | none | remains none |
| treatment_authority | none | remains none |

---

## 5. What R2 Cleared

R2 clears the following for internal structural use only:

- UIP HRCT category framework,
- UIP pattern boundary,
- probable UIP boundary,
- indeterminate for UIP boundary,
- alternative diagnosis pattern prompts,
- known-cause exclusion prompts,
- exposure and medication history prompts,
- CTD / autoimmune context prompts,
- MDD prompt role,
- acute overlay / new GGO distinction,
- PPF context,
- PPF radiological progression framework,
- HP mimic auxiliary visibility,
- ILA auxiliary non-diagnostic handling.

This clearance is limited.

It does not create:

- clinical review,
- public readiness,
- diagnostic authority,
- treatment authority,
- biopsy decision authority,
- patient-facing use.

---

## 6. What R2 Did Not Clear

R2 does not clear:

| Area | Status |
|---|---|
| Full ATS guideline parity | not cleared |
| Full Fleischner 2018 formal extraction | not cleared |
| Full Fleischner 2020 ILA management parity | not cleared |
| Full HP diagnostic parity | not cleared |
| Treatment or management recommendations | not allowed |
| Biopsy decision automation | not allowed |
| Clinical validation | not performed |
| Patient-facing interpretation | not allowed |
| public_ready | false |
| clinically_reviewed | false |

---

## 7. Source Role Corrections

The following source roles are now locked.

### 7.1 ATS 2018 Role

ATS 2018 is the primary official source for:

- UIP HRCT category framework,
- probable UIP boundary,
- indeterminate for UIP,
- alternative diagnosis pattern,
- exclusion of known causes,
- exposure and medication history requirement,
- CTD serology requirement,
- MDD prompt role,
- BAL / SLB pathway boundaries where relevant.

Allowed role:

- source-governed internal reasoning structure.

Blocked role:

- platform diagnosis,
- treatment selection,
- public-ready clinical protocol.

---

### 7.2 ATS 2022 Role

ATS 2022 is the current update source for:

- retained four HRCT categories,
- probable UIP / UIP diagnostic approach nuance,
- current source hierarchy,
- PPF definition,
- PPF physiological and radiological progression criteria,
- alternative explanation requirement in PPF.

Allowed role:

- source-governed update and PPF context.

Blocked role:

- treatment authority inside v0.6,
- public-ready PPF management tool,
- automatic progression diagnosis.

---

### 7.3 Fleischner 2018 Role

Fleischner 2018 remains:

- verified comparative anchor,
- useful for clinical context,
- useful for probable UIP nuance,
- useful for MDD / working diagnosis / re-review reasoning.

Allowed role:

- comparative reasoning support.

Blocked role:

- replacement of ATS official guideline source,
- sole authority for v0.6 clinical status,
- public-ready claim.

---

### 7.4 Fleischner 2020 ILA Role

Fleischner 2020 ILA remains:

- auxiliary ILA / early fibrotic abnormality source,
- useful for incidental ILA non-diagnostic handling,
- useful for future ILA parity.

Allowed role:

- auxiliary test case support.

Blocked role:

- UIP diagnostic category authority,
- ILA management automation,
- public-facing follow-up instruction.

---

### 7.5 Koster 2021 HP Summary Role

Koster 2021 is added as:

- auxiliary HP mimic anchor,
- future v0.7 differential reasoning source,
- support for HP-like features such as mosaic attenuation, air trapping, three-density pattern, fibrotic HP overlap, and exposure-sensitive reasoning.

Allowed role:

- HP mimic visibility support.

Blocked role:

- primary UIP diagnostic source,
- full HP parity seal,
- HP diagnosis automation.

---

## 8. Documentation Interpretation Overlay

This R3 document applies as an interpretation overlay across v0.6.

Whenever a v0.6 document says:

- sealed,
- source-governed,
- source-anchored,
- parity,
- testable,
- lock,
- structural seal,

it must be interpreted as:

- structurally organized,
- internally governed,
- non-authoritative,
- source-aware,
- not clinically reviewed,
- not public-ready.

It must not be interpreted as:

- clinically validated,
- diagnostic,
- treatment-guiding,
- patient-facing,
- public-ready,
- fully guideline-complete.

---

## 9. Corrected Global Status

The corrected global status after R3 is:

| Field | Corrected Status |
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
| patient_facing_use | not_allowed |
| biopsy_decision_authority | none |
| treatment_guidance_authority | none |

---

## 10. v0.7 Entry Decision

R3 permits v0.7 entry only under strict limits.

| Question | Decision |
|---|---|
| Can v0.7 open as a structural/source-governed draft phase? | yes |
| Can v0.7 claim clinical review? | no |
| Can v0.7 claim public readiness? | no |
| Can v0.7 diagnose non-UIP fibrotic ILD? | no |
| Can v0.7 recommend treatment? | no |
| Can v0.7 build differential reasoning governance? | yes |
| Must v0.7 inherit R1/R2/R3 source-debt discipline? | yes |

Allowed next step:

- v0.7.0 — Non-UIP Fibrotic ILD Differential Reasoning Entry Gate / Source-Governed Scope Contract

Blocked next step:

- any public-ready clinical product claim,
- any diagnostic engine claim,
- any treatment pathway claim,
- any clinically_reviewed seal.

---

## 11. Required Carryover into v0.7

v0.7 must inherit:

- diagnostic_authority: none,
- treatment_authority: none,
- public_ready: false,
- clinically_reviewed: false,
- source_review_debt_visible: true,
- claim_to_source_mapping_required: true,
- missing evidence visible,
- mimics visible,
- MDD prompts visible,
- urgent review prompts visible where relevant,
- no single-label closure,
- no disease naming before evidence review.

v0.7 must also carry forward the phrase:

> “A structural seal is not a clinical source-review seal.”

---

## 12. Remaining Source Debt After R3

Remaining source debt is now explicit and non-blocking for structural v0.7 entry, but blocking for clinical review.

| Debt | Blocks Structural v0.7 Entry? | Blocks Clinical Review? |
|---|---|---|
| Full ATS 2018 guideline extraction | no | yes |
| Full ATS 2022 guideline extraction | no | yes |
| Exact Fleischner 2018 passage table | no | yes |
| Exact Fleischner 2020 ILA passage table | no | yes for ILA parity |
| Full HP guideline source review | no | yes for HP parity |
| Treatment guidance mapping | not allowed in v0.6/v0.7 | yes |
| Public-readiness validation | not allowed | yes |

---

## 13. Drift Risks Blocked

This R3 lock blocks the following risks:

| Drift Risk | R3 Block |
|---|---|
| R2 mapping mistaken for clinical review | clinically_reviewed remains false |
| v0.6 seal mistaken for public readiness | public_ready remains false |
| ATS 2018/2022 mapping overclaimed | targeted_partial status locked |
| Fleischner 2018 replaces ATS | comparative role locked |
| Fleischner 2020 ILA becomes UIP diagnostic source | auxiliary role locked |
| Koster 2021 HP summary becomes UIP authority | auxiliary HP mimic role locked |
| v0.7 opens as diagnostic product | v0.7 entry limited to structural/source-governed draft |
| treatment logic leaks in | treatment_authority none |
| biopsy decision logic leaks in | biopsy_decision_authority none |
| single-label differential closure returns | no single-label closure inherited |

---

## 14. Acceptance Criteria

v0.6.R3 is accepted only if:

- R1 debt register remains valid,
- R2 claim-to-source mapping is recognized,
- ATS 2018 status is corrected,
- ATS 2022 status is corrected,
- Fleischner 2018 remains comparative,
- Fleischner 2020 remains auxiliary ILA,
- Koster 2021 is added only as auxiliary HP mimic source,
- v0.6 remains structurally sealed,
- v0.6 remains not clinically reviewed,
- public_ready remains false,
- diagnostic_authority remains none,
- treatment_authority remains none,
- v0.7 entry is allowed only as source-governed structural draft.

---

## 15. Next Step

The next recommended step is:

- v0.7.0 — Non-UIP Fibrotic ILD Differential Reasoning Entry Gate / Source-Governed Scope Contract

v0.7.0 should open the differential reasoning expansion cautiously.

Initial candidate domains:

- fibrotic hypersensitivity pneumonitis,
- CTD-ILD,
- fibrotic NSIP,
- sarcoidosis,
- occupational ILD / pneumoconiosis / asbestosis,
- drug toxicity,
- aspiration / organizing pneumonia overlap,
- smoking-related fibrosis / CPFE contexts.

v0.7.0 must not create diagnosis or treatment authority.

---

## 16. Governance Statement

This backfill lock preserves the integrity of v0.6.

It confirms that source debt has been made visible and partially paid down.

It does not convert v0.6 into clinical review.

It does not diagnose.  
It does not treat.  
It does not decide biopsy.  
It does not confirm UIP.  
It does not confirm IPF.  
It does not exclude mimics.  
It does not confirm acute exacerbation.  
It does not claim public readiness.

Current locked status:

- uip_parity_structural_governance: sealed
- uip_source_review: targeted_partial
- uip_claim_mapping: partial_backfill_complete
- clinically_reviewed: false
- public_ready: false
- diagnostic_authority: none
- treatment_authority: none

The platform remains an evidence-governed clinical reasoning platform.

It teaches clinicians to read evidence status before trusting the structure.