# ILD Reasoning Platform — UIP Source Anchor Review Map v1

Version: v0.6.1  
Status: source_anchor_review_map  
Scope: UIP parity source governance  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Source Review Date: 2026-06-04  

---

## 1. Purpose

This document maps the source anchors required for the v0.6 UIP Parity Upgrade.

It does not define final UIP criteria.  
It does not create diagnostic authority.  
It does not create treatment authority.  
It does not create public readiness.  
It does not replace guideline review, radiologist interpretation, pathology review, clinical judgment, or multidisciplinary discussion.

Its purpose is to ensure that any UIP parity upgrade remains evidence-governed.

The platform principle remains:

> “It teaches clinicians to read change before naming disease.”

For v0.6, this becomes:

> “Read pattern, boundary, uncertainty, evidence, and change before naming UIP.”

---

## 2. Relationship to v0.6.0

This file follows:

- `docs/navigation/uip_parity_upgrade_entry_gate_v1.md`

v0.6.0 opened the UIP Parity Upgrade as a non-authoritative reasoning-quality upgrade.

v0.6.1 adds source governance.

This means that later v0.6 files must not introduce UIP pattern categories, guideline-sensitive terms, imaging criteria, pathology criteria, biopsy logic, MDD logic, or differential diagnosis logic without connecting them to an appropriate source anchor and review status.

---

## 3. Source Anchor Philosophy

UIP parity must be source-anchored because UIP reasoning is guideline-sensitive.

However, source anchoring does not create diagnostic authority.

A source anchor means:

- the claim has a traceable evidence or guideline source,
- the source type is visible,
- the source date is visible,
- the claim scope is visible,
- limitations are visible,
- uncertainty is preserved,
- disagreement or evolution between sources remains review-visible.

A source anchor does not mean:

- the platform diagnoses UIP,
- the platform diagnoses IPF,
- the platform selects treatment,
- the platform becomes public-ready,
- the platform replaces radiology, pathology, clinical correlation, or MDD.

---

## 4. Primary Source Anchors

The following source anchors are provisionally accepted for v0.6 source mapping.

They may be used only as anchors for reasoning parity, not as autonomous diagnostic rules.

| Anchor ID | Source Type | Source Name | Primary Use in v0.6 | Review Status |
|---|---|---|---|---|
| UIP_SRC_2022_ATS_ERS_JRS_ALAT_IPF_PPF | Official clinical practice guideline update | ATS/ERS/JRS/ALAT 2022 IPF Update and Progressive Pulmonary Fibrosis Guideline | Current guideline-sensitive framing, updated IPF/PPF context, source hierarchy | primary_anchor |
| UIP_SRC_2018_ATS_ERS_JRS_ALAT_DX | Official clinical practice guideline | ATS/ERS/JRS/ALAT 2018 Diagnosis of Idiopathic Pulmonary Fibrosis Guideline | HRCT pattern category framework, diagnostic reasoning boundaries, MDD framing | primary_anchor |
| UIP_SRC_2018_FLEISCHNER_WHITE_PAPER | Society white paper / expert consensus | Lynch et al. 2018 Fleischner Society Diagnostic Criteria for IPF White Paper | Verified comparative HRCT/IPF diagnostic criteria anchor, clinical probability framing, multidisciplinary diagnosis context | verified_comparative_anchor |
| UIP_SRC_INTERNAL_V04_SOURCE_GOVERNANCE | Internal platform governance | v0.4 Evidence Layer / Source Review Governance | Source review rules, uncertainty preservation, citation sensitivity | internal_governance_anchor |
| UIP_SRC_INTERNAL_V05_TEST_COVERAGE_SEAL | Internal platform governance | v0.5 Test Case Coverage Seal | Test coverage constraints, mimics, missing evidence, MDD/urgent review visibility | internal_governance_anchor |

---

## 5. Source Role Boundaries

### 5.1 Official Guideline Anchors

Official guideline anchors may support:

- terminology mapping,
- pattern category mapping,
- diagnostic pathway framing,
- multidisciplinary discussion requirements,
- biopsy / pathology reasoning context,
- source-sensitive parity tests.

They must not be converted into automated diagnosis.

### 5.2 White Paper / Consensus Anchors

White paper or consensus anchors may support:

- comparison of diagnostic frameworks,
- clinical probability reasoning,
- expert terminology alignment,
- boundary reasoning.

They must not override official guideline anchors without explicit review.

### 5.3 Internal Governance Anchors

Internal governance anchors may support:

- non-authority constraints,
- uncertainty preservation,
- missing evidence visibility,
- mimic visibility,
- MDD / urgent review visibility,
- test coverage synchronization.

They must not create external clinical authority.

---

## 6. Claim Sensitivity Map

The following claim types require source anchoring before use in v0.6.

| Claim Type | Source Required | Minimum Review Requirement |
|---|---|---|
| UIP HRCT category definitions | official guideline anchor | source citation + date + limitation visible |
| Probable UIP boundary claims | official guideline anchor + comparative anchor if needed | ambiguity visible |
| Indeterminate for UIP claims | official guideline anchor | uncertainty visible |
| Alternative diagnosis pattern claims | official guideline anchor | mimic / differential visible |
| Histopathology UIP category claims | official guideline anchor | pathology context visible |
| Biopsy-related pathway claims | official guideline anchor | risk and case-by-case framing visible |
| MDD requirement claims | official guideline anchor | clinician/MDD authority preserved |
| IPF diagnosis pathway claims | official guideline anchor | imaging-alone inference blocked |
| PPF-related claims | 2022 guideline anchor | progression context visible |
| Treatment-related claims | not allowed in v0.6 reasoning docs | treatment_authority remains none |
| Public readiness claims | not allowed | public_ready remains false |

---

## 7. Non-Allowed Claim Map

The following claims are not allowed in v0.6 documents.

| Not Allowed Claim | Reason |
|---|---|
| The platform diagnoses UIP | diagnostic_authority is none |
| The platform diagnoses IPF | diagnostic_authority is none |
| UIP pattern equals IPF | imaging-alone inference is blocked |
| Probable UIP equals final diagnosis | uncertainty and clinical context required |
| Indeterminate UIP can be resolved automatically | uncertainty must remain visible |
| Alternative diagnosis can be ignored | mimic and differential visibility required |
| MDD is optional in uncertain cases | MDD prompt must remain visible |
| Treatment should be selected from platform output | treatment_authority is none |
| Patient-facing use is ready | public_ready is false |
| Guideline-sensitive claims can be made without source review | v0.4 source governance applies |

---

## 8. UIP Reasoning Domains Requiring Anchors

Later v0.6 documents must connect each reasoning domain to a source anchor.

| Reasoning Domain | Required Anchor Type | Later v0.6 Target |
|---|---|---|
| HRCT pattern category framework | official guideline anchor | v0.6.2 |
| UIP / probable / indeterminate / alternative boundary logic | official guideline anchor | v0.6.2 / v0.6.3 |
| Mimics and alternative explanations | official guideline anchor + v0.5 coverage seal | v0.6.4 |
| Superimposed acute change | official guideline anchor + v0.3/v0.5 governance | v0.6.4 / v0.6.5 |
| Temporal comparison | v0.5 coverage seal + source-sensitive review | v0.6.5 |
| MDD prompt parity | official guideline anchor + internal governance | v0.6.6 |
| Missing evidence prompt parity | internal governance + source-sensitive review | v0.6.6 |
| Test case upgrade | all relevant anchors | v0.6.7 |
| Lock checklist | all anchors | v0.6.8 |
| UIP parity seal | all anchors | v0.6.9 |

---

## 9. Source Review Fields Required for Later v0.6 Files

Any later v0.6 document that uses external guideline-sensitive content should include the following fields:

- source_anchor_id
- source_type
- source_title
- source_year
- source_status
- claim_scope
- claim_limitations
- diagnostic_authority
- treatment_authority
- public_ready
- uncertainty_preserved
- missing_pieces_visible
- mimics_visible
- mdd_prompt_visible
- urgent_review_prompt_visible_where_relevant

Recommended format:

| Field | Required State |
|---|---|
| source_anchor_id | present |
| source_type | present |
| source_year | present |
| claim_scope | present |
| claim_limitations | present |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |

---

## 10. Source Drift Risks

This source map blocks the following source drift risks.

| Drift Risk | Governance Block |
|---|---|
| Outdated criteria are silently reused | source year and review status required |
| Guideline-sensitive claims appear without anchor | source_anchor_id required |
| White paper overrides official guideline silently | source role boundary required |
| Imaging category becomes final diagnosis | diagnostic authority blocked |
| IPF is inferred from HRCT alone | imaging-alone inference blocked |
| MDD disappears from diagnostic reasoning | MDD prompt required |
| Treatment logic leaks into parity docs | treatment authority blocked |
| Missing evidence is filled by assumption | missing evidence visibility required |
| Mimics disappear from UIP framing | mimic visibility required |
| Public readiness is implied | public_ready false |

---

## 11. Provisional Anchor Details

### 11.1 UIP_SRC_2022_ATS_ERS_JRS_ALAT_IPF_PPF

Role:

- current high-level guideline anchor,
- IPF update context,
- PPF context,
- source hierarchy reference for v0.6.

Allowed use:

- source map,
- guideline-sensitive review pointer,
- PPF-related framing,
- later parity source cross-check.

Not allowed use:

- automated treatment recommendation,
- autonomous diagnostic decision,
- public deployment claim.

---

### 11.2 UIP_SRC_2018_ATS_ERS_JRS_ALAT_DX

Role:

- HRCT category source anchor,
- histopathology category source anchor,
- diagnostic pathway source anchor,
- MDD context source anchor.

Allowed use:

- UIP / probable UIP / indeterminate / alternative diagnosis category mapping,
- reasoning boundary design,
- MDD prompt parity,
- later test case parity upgrade.

Not allowed use:

- final diagnosis automation,
- imaging-only IPF conclusion,
- replacement of radiologist or MDD.

---

### 11.3 UIP_SRC_2018_FLEISCHNER_WHITE_PAPER

Role:

- comparative diagnostic criteria anchor,
- HRCT interpretation framework comparison,
- clinical probability and multidisciplinary reasoning support.

Allowed use:

- comparison with ATS/ERS/JRS/ALAT framework,
- ambiguity review,
- source disagreement visibility,
- expert consensus context.

Not allowed use:

- silent override of official guideline anchor,
- automatic diagnosis,
- treatment authority.

---

### 11.4 UIP_SRC_INTERNAL_V04_SOURCE_GOVERNANCE

Role:

- governs how source claims are reviewed,
- prevents unsupported authority,
- preserves uncertainty,
- keeps source limitations visible.

Allowed use:

- source review checklist,
- claim sensitivity scoring,
- source limitation prompts.

Not allowed use:

- external clinical authority creation.

---

### 11.5 UIP_SRC_INTERNAL_V05_TEST_COVERAGE_SEAL

Role:

- preserves v0.5 test coverage constraints,
- keeps mimics visible,
- keeps missing evidence visible,
- keeps MDD / urgent review prompts visible.

Allowed use:

- parity test upgrade design,
- mimic and overlap reasoning,
- missing evidence prompts,
- test coverage lock inheritance.

Not allowed use:

- clinical validation claim,
- public readiness claim.

---

## 12. Required Source Review Before v0.6.2

Before v0.6.2 introduces a UIP Pattern Boundary Matrix, the following must be true:

- primary source anchors are listed,
- official guideline source is identified,
- comparative white paper source is identified,
- internal governance anchors are identified,
- claim sensitivity map exists,
- non-allowed claim map exists,
- source drift risks are visible,
- diagnostic_authority remains none,
- treatment_authority remains none,
- public_ready remains false,
- UIP pattern is not treated as final diagnosis,
- IPF is not inferred from imaging alone,
- MDD remains visible,
- missing evidence remains visible,
- mimics remain visible.

---

## 13. Acceptance Criteria

v0.6.1 is accepted only if:

- source anchors are mapped,
- source roles are separated,
- official guideline anchors are not conflated with internal governance anchors,
- white paper / consensus anchors are comparative, not overriding by default,
- claim sensitivity is visible,
- non-allowed claims are explicit,
- source drift risks are blocked,
- later v0.6 files are required to carry source review fields,
- diagnostic_authority remains none,
- treatment_authority remains none,
- public_ready remains false.

---

## 14. Governance Statement

The UIP Source Anchor Review Map exists to keep v0.6 evidence-governed.

It does not define final UIP criteria.  
It does not diagnose UIP.  
It does not diagnose IPF.  
It does not recommend treatment.  
It does not claim public readiness.

It prepares the platform for a safer next step:

- v0.6.2 — UIP Pattern Boundary Matrix

The platform remains an evidence-governed clinical reasoning platform.

It teaches clinicians to read pattern, boundary, uncertainty, evidence, and change before naming UIP.