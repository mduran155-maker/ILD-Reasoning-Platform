# ILD Reasoning Platform — UIP Mimic and Superimposed Process Parity v1

Version: v0.6.4  
Status: mimic_superimposed_process_parity  
Scope: UIP-facing mimic and overlap reasoning parity  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Source Review Date: 2026-06-04  

---

## 1. Purpose

This document defines mimic and superimposed-process parity for UIP-facing reasoning in the ILD Reasoning Platform.

It follows the UIP Reasoning Parity Rules.

It does not diagnose UIP.  
It does not diagnose IPF.  
It does not diagnose mimics.  
It does not diagnose acute exacerbation.  
It does not recommend treatment.  
It does not create public readiness.  
It does not replace radiologist interpretation, clinical correlation, pathology review, microbiology, cardiology review, MDD, or urgent clinical assessment.

Its purpose is to ensure that UIP-facing reasoning does not erase mimics or overlapping processes.

The platform principle remains:

> “It teaches clinicians to read change before naming disease.”

For v0.6.4, this becomes:

> “Read mimic, overlap, acute change, and uncertainty before naming UIP.”

---

## 2. Relationship to Prior v0.6 Files

This file follows:

- `docs/navigation/uip_parity_upgrade_entry_gate_v1.md`
- `docs/navigation/uip_source_anchor_review_map_v1.md`
- `docs/data/schema/uip_pattern_boundary_matrix_v1.md`
- `docs/data/schema/uip_reasoning_parity_rules_v1.md`

v0.6.0 opened UIP parity as reasoning parity.

v0.6.1 mapped source anchors.

v0.6.2 defined pattern-boundary states.

v0.6.3 defined testable reasoning parity rules.

v0.6.4 deepens the mimic and superimposed-process layer.

This document does not add diagnostic authority.

---

## 3. Source Anchors Used

| Source Anchor ID | Role |
|---|---|
| UIP_SRC_2018_ATS_ERS_JRS_ALAT_DX | HRCT pattern categories, alternative diagnosis features, acute exacerbation imaging context |
| UIP_SRC_2022_ATS_ERS_JRS_ALAT_IPF_PPF | Current update / source hierarchy anchor |
| UIP_SRC_2018_FLEISCHNER_WHITE_PAPER | Verified comparative expert consensus anchor from uploaded Lynch et al. 2018 Fleischner Society White Paper |
| UIP_SRC_INTERNAL_V03_SUPERIMPOSED_EVENTS_CORE | Internal overlap / simultaneous-process reasoning inheritance |
| UIP_SRC_INTERNAL_V04_SOURCE_GOVERNANCE | Source review and limitation governance |
| UIP_SRC_INTERNAL_V05_TEST_COVERAGE_SEAL | Mimic, missing evidence, MDD, urgent review inheritance |
| UIP_INTERNAL_V062_PATTERN_BOUNDARY_MATRIX | Pattern-state dependency |
| UIP_INTERNAL_V063_REASONING_PARITY_RULES | Immediate parity-rule dependency |

---

## 4. Authority Constraints

The following constraints are mandatory:

| Constraint | Required State |
|---|---|
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| automated_UIP_diagnosis | not allowed |
| automated_IPF_diagnosis | not allowed |
| automated_mimic_diagnosis | not allowed |
| automated_acute_exacerbation_diagnosis | not allowed |
| treatment_selection | not allowed |
| patient_facing_use | not allowed |
| replacement_of_radiologist | not allowed |
| replacement_of_pathology | not allowed |
| replacement_of_microbiology | not allowed |
| replacement_of_clinical_context | not allowed |
| replacement_of_MDD | not allowed |
| replacement_of_urgent_review | not allowed |

No mimic row creates a diagnosis.

No superimposed-process row creates a diagnosis.

Each row creates a visibility requirement, review prompt, or closure block.

---

## 5. Core Mimic and Superimposed-Process Principle

UIP-facing reasoning must not collapse complex findings into a single preferred label.

The platform must allow:

- chronic fibrotic background,
- UIP-compatible pattern reasoning,
- probable UIP reasoning,
- indeterminate UIP reasoning,
- alternative pattern reasoning,
- infection,
- edema,
- hemorrhage,
- vascular concern,
- drug toxicity,
- aspiration / organizing pneumonia concern,
- HP-like alternative pattern,
- CTD-ILD-like alternative pattern,
- NSIP-like alternative pattern,
- sarcoid-like alternative pattern,
- pneumoconiosis / asbestosis-like alternative pattern,
- acute exacerbation prompt,

to remain visible when relevant.

Central rule:

> A mimic prompt is not a diagnosis.  
> A superimposed-process prompt is not a diagnosis.  
> But hiding either is a reasoning failure.

---

## 6. Mimic and Overlap State Model

The platform should treat mimic and overlap findings as modifiers, not automatic replacements.

| State | Meaning | Required Behavior |
|---|---|---|
| MIMIC_VISIBLE | A competing explanation is plausible or cannot be excluded because evidence is missing | Keep mimic visible; do not diagnose it automatically |
| MIMIC_DOMINANT_PROMPT | Features strongly suggest a competing pathway over UIP-facing closure | Block premature UIP/IPF closure; prompt review |
| SUPERIMPOSED_PROCESS_VISIBLE | Acute or secondary process may coexist with chronic fibrosis | Preserve both baseline and overlay |
| ACUTE_OVERLAY_PROMPT | New or acute findings suggest active process over chronic fibrotic background | Trigger urgent review visibility where relevant |
| MISSING_EVIDENCE_MIMIC_RISK | Missing data prevents safe exclusion of mimic | List missing evidence explicitly |
| MDD_ESCALATION_PROMPT | Integrated review is needed because pattern, mimic, and context are discordant or incomplete | Preserve MDD visibility |
| URGENT_REVIEW_PROMPT | Acute, vascular, hemorrhagic, infectious, or unstable context may be clinically dangerous | Preserve urgent review visibility |

These states may coexist.

Example:

- `PROBABLE_UIP_PATTERN_CANDIDATE`
- plus `MISSING_EVIDENCE_MIMIC_RISK`
- plus `SUPERIMPOSED_PROCESS_VISIBLE`
- plus `MDD_ESCALATION_PROMPT`

is valid.

The platform must not force a single label.

---

## 7. Mimic Parity Matrix

| Mimic / Overlap Family | Possible Interference With UIP Reasoning | Visibility Trigger | Required Platform Response | Blocked Closure |
|---|---|---|---|---|
| Infection | May add GGO, consolidation, nodules, acute worsening, fever/inflammatory context | New GGO/consolidation, acute symptoms, microbiology missing, inflammatory markers missing | Keep infection visible; prompt microbiology and clinical correlation | “UIP progression” or “acute exacerbation” by default |
| Edema | May mimic bilateral GGO, septal thickening, acute dyspnea, worsening oxygenation | Cardiac/volume data missing, bilateral GGO/septal thickening, acute symptoms | Keep edema visible; prompt cardiac/volume status review | Infection/UIP/exacerbation closure without volume review |
| Hemorrhage | May mimic diffuse or patchy GGO and acute respiratory decline | Hemoptysis, anticoagulation risk, anemia context missing, diffuse GGO | Keep hemorrhage visible; prompt urgent review where relevant | GGO assigned to UIP progression by default |
| Vascular process | May explain acute hypoxemia or dyspnea without directly being UIP progression | Acute dyspnea, hypoxemia, vascular concern, unstable context | Keep vascular concern visible; prompt urgent review where relevant | Chronic ILD progression assumed without acute review |
| Acute exacerbation prompt | May present as new bilateral GGO/consolidation on fibrotic background | Acute deterioration with new GGO/consolidation | Keep acute exacerbation as possibility; require mimic review | “AE-IPF confirmed” by imaging alone |
| Hypersensitivity pneumonitis | May show mosaic attenuation, air-trapping, bronchocentric or upper/mid-lung features | Mosaic attenuation, air-trapping, exposure history missing | Keep HP-like alternative visible; prompt exposure review | UIP/IPF closure while exposure missing |
| CTD-ILD | May mimic or modify fibrotic ILD pattern | Autoimmune context missing, extrapulmonary clues, esophageal dilation, RA-related clues | Keep CTD-ILD visible; prompt autoimmune/clinical correlation | IPF closure without CTD review |
| NSIP | May show GGO, subpleural sparing, or less typical UIP distribution | Predominant GGO, subpleural sparing, diffuse symmetric pattern concern | Trigger alternative / indeterminate prompt | UIP label despite NSIP-like features |
| Sarcoidosis | May show upper-lung/perilymphatic features, lymphadenopathy, hilar distortion | Lymphadenopathy, upper-lung predominance, perilymphatic pattern | Keep sarcoid-like alternative visible | UIP/IPF closure despite alternative distribution |
| Pneumoconiosis / asbestosis | May overlap with basal fibrosis; pleural plaques matter | Occupational history missing, pleural plaques, dust exposure context | Keep occupational mimic visible; prompt exposure review | IPF closure while occupational evidence missing |
| Drug toxicity | May create GGO, organizing pneumonia-like findings, or acute/chronic ILD | Medication history missing, new GGO/consolidation, temporal drug exposure concern | Keep drug toxicity visible; prompt medication review | UIP progression / AE label without medication review |
| Aspiration / organizing pneumonia concern | May create consolidation, GGO, peribronchial or migratory opacity | Aspiration risk missing, consolidation, organizing pattern concern | Keep aspiration/OP-like alternative visible | UIP/IPF closure despite consolidation-dominant process |

---

## 8. Superimposed-Process Rules

Superimposed processes must be treated as possible overlays on chronic fibrotic background.

| Rule ID | Rule | Required Behavior |
|---|---|---|
| UIP_MIMIC_001 | Chronic fibrosis and acute process may coexist | Do not force a single-process explanation |
| UIP_MIMIC_002 | New GGO/consolidation requires overlay review | Trigger infection, edema, hemorrhage, vascular, drug toxicity, and acute exacerbation prompts where relevant |
| UIP_MIMIC_003 | Acute worsening is not automatically UIP progression | Preserve acute overlay and urgent review visibility |
| UIP_MIMIC_004 | Mimic visibility does not diagnose mimic | Use prompt language, not final diagnostic language |
| UIP_MIMIC_005 | Missing data preserves mimic risk | Do not exclude mimic without evidence |
| UIP_MIMIC_006 | Alternative features veto premature UIP/IPF closure | Alternative pattern prompt must remain visible |
| UIP_MIMIC_007 | MDD remains visible when overlap is complex | Integrated review is required for uncertain or discordant cases |
| UIP_MIMIC_008 | Urgent danger outranks pattern classification | Acute instability, hemorrhage, severe infection, or vascular concern triggers urgent review prompt |
| UIP_MIMIC_009 | Treatment logic remains blocked | No output may recommend therapy |
| UIP_MIMIC_010 | Public readiness remains false | No output may imply patient-facing readiness |

---

## 9. Priority Order for Mimic and Overlay Review

When UIP-facing reasoning is performed, the following priority order applies:

1. urgent clinical danger,
2. acute superimposed process,
3. vascular / hemorrhage / severe infection concern,
4. alternative diagnosis features,
5. missing evidence that prevents mimic exclusion,
6. temporal comparison uncertainty,
7. chronic fibrotic pattern-state reasoning.

This means chronic pattern classification cannot safely erase acute or dangerous overlay prompts.

Pattern reasoning comes after safety visibility.

---

## 10. Missing Evidence Required for Mimic Exclusion

The following missing evidence categories must remain visible when relevant.

| Missing Evidence | Mimic Risk Preserved |
|---|---|
| Microbiology missing | infection |
| Fever / inflammatory markers missing | infection or inflammatory process |
| Cardiac function / BNP / volume status missing | edema |
| Hemoptysis / anemia / anticoagulation context missing | hemorrhage |
| Acute oxygen trend missing | acute overlay severity |
| Vascular risk / PE assessment missing | vascular process |
| Medication history missing | drug toxicity |
| Exposure history missing | HP / pneumoconiosis / occupational ILD |
| Autoimmune history/serology missing | CTD-ILD |
| Aspiration risk missing | aspiration / organizing pneumonia concern |
| Prior HRCT missing | progression or new overlay cannot be confidently assessed |
| HRCT technique incomplete | dependent opacity, motion, or acquisition limitation may alter confidence |
| MDD unavailable | integrated diagnosis not established |

Required rule:

> Missing evidence must not be silently converted into exclusion.

---

## 11. UIP-State Interaction Matrix

| UIP-Facing State | Mimic / Overlay Interaction Requirement |
|---|---|
| UIP_PATTERN_CANDIDATE | UIP-compatible features may be acknowledged, but mimics and known-cause exclusion remain visible |
| PROBABLE_UIP_PATTERN_CANDIDATE | Probable UIP must not suppress infection, edema, hemorrhage, HP, CTD-ILD, or drug toxicity prompts |
| INDETERMINATE_FOR_UIP | Mimic and missing evidence prompts should be especially visible because confidence is limited |
| ALTERNATIVE_PATTERN_PROMPT | Alternative features block UIP/IPF closure until reviewed |
| ACUTE_SUPERIMPOSED_MODIFIER | Acute overlay prompts must separate acute change from chronic fibrosis progression |

No UIP-facing state has authority to hide mimic risk.

---

## 12. Allowed Language

Allowed output posture:

- “infection remains a visible superimposed-process prompt”
- “edema remains a visible mimic / overlap prompt”
- “hemorrhage cannot be excluded from imaging pattern alone”
- “vascular concern should remain review-visible where clinically relevant”
- “acute exacerbation is a possibility, not confirmed by imaging alone”
- “HP-like alternative pattern prompt is triggered”
- “CTD-ILD context is missing”
- “drug toxicity review is incomplete”
- “mimic exclusion requires clinical correlation”
- “MDD review remains appropriate”
- “urgent clinical review may be appropriate depending on context”

---

## 13. Blocked Language

Blocked output posture:

- “infection excluded” when microbiology/clinical data are missing
- “edema excluded” when cardiac/volume status is missing
- “hemorrhage excluded” when clinical risk context is missing
- “acute exacerbation confirmed by imaging alone”
- “UIP progression confirmed” when acute overlay is possible
- “IPF confirmed” from UIP-facing pattern alone
- “alternative diagnosis excluded” without evidence
- “no urgent review needed” despite acute danger signals
- “treatment should be started”
- “patient-facing result”
- “public-ready”

---

## 14. Testable Mimic Parity Expectations

Future v0.6 test cases should evaluate the following expectations.

| Expectation ID | Expectation |
|---|---|
| UMP_001 | Mimic visibility is preserved |
| UMP_002 | Superimposed-process visibility is preserved |
| UMP_003 | Acute overlay is not collapsed into chronic progression |
| UMP_004 | Infection remains visible when infection evidence is missing or supportive |
| UMP_005 | Edema remains visible when cardiac/volume data are missing or supportive |
| UMP_006 | Hemorrhage remains visible when hemorrhage context is missing or supportive |
| UMP_007 | Vascular concern remains visible when acute hypoxemia/dyspnea or instability is present |
| UMP_008 | HP-like alternative pattern remains visible with mosaic attenuation/air-trapping/exposure uncertainty |
| UMP_009 | CTD-ILD remains visible when autoimmune context is missing |
| UMP_010 | Drug toxicity remains visible when medication history is missing |
| UMP_011 | Occupational/asbestos mimic remains visible when exposure or pleural plaque context exists |
| UMP_012 | Alternative-pattern prompt blocks UIP/IPF closure |
| UMP_013 | Missing evidence is listed rather than assumed |
| UMP_014 | MDD prompt remains visible in complex overlap |
| UMP_015 | Urgent review prompt remains visible where relevant |
| UMP_016 | Diagnostic authority remains none |
| UMP_017 | Treatment authority remains none |
| UMP_018 | Public readiness remains false |

---

## 15. Example Reasoning Scenarios

### 15.1 Chronic Fibrosis With New GGO

Input reasoning context:

- chronic fibrotic background,
- new bilateral GGO,
- acute dyspnea,
- microbiology missing,
- cardiac/volume status missing,
- prior comparison available.

Allowed platform output:

- “Acute superimposed process prompt is triggered.”
- “Infection, edema, hemorrhage, vascular concern, drug toxicity, and acute exacerbation remain visible.”
- “Do not collapse acute change into chronic UIP progression.”
- “Urgent clinical review may be appropriate depending on clinical context.”

Blocked output:

- “UIP progression confirmed.”
- “Acute exacerbation confirmed by imaging alone.”
- “Infection and edema excluded.”

---

### 15.2 Probable UIP Pattern With Missing Exposure History

Input reasoning context:

- probable UIP-pattern candidate,
- no honeycombing,
- exposure history missing,
- mild mosaic attenuation described.

Allowed platform output:

- “Probable UIP-pattern reasoning may be considered.”
- “HP-like alternative pattern remains visible.”
- “Exposure history is missing.”
- “MDD and clinical correlation remain appropriate.”

Blocked output:

- “Definite UIP.”
- “IPF confirmed.”
- “HP excluded.”

---

### 15.3 UIP-Compatible Pattern With Pleural Plaques

Input reasoning context:

- basal/subpleural fibrosis,
- honeycombing,
- pleural plaques,
- occupational exposure history not documented.

Allowed platform output:

- “UIP-compatible features are present.”
- “Occupational/asbestos-related mimic or contributor remains visible.”
- “Exposure history is missing.”
- “Final diagnosis requires clinical correlation / MDD.”

Blocked output:

- “IPF confirmed.”
- “Asbestosis excluded.”
- “No further review needed.”

---

### 15.4 Indeterminate Pattern With Missing Technique Context

Input reasoning context:

- subtle subpleural opacity,
- limited reticulation,
- no clear honeycombing,
- prone imaging unavailable,
- technique context incomplete.

Allowed platform output:

- “Indeterminate for UIP-pattern reasoning.”
- “Dependent atelectasis / technique limitation remains visible.”
- “Missing evidence limits confidence.”
- “MDD prompt remains visible.”

Blocked output:

- “UIP likely.”
- “Alternative diagnosis excluded.”
- “Pattern resolved automatically.”

---

### 15.5 Alternative Pattern With Consolidation

Input reasoning context:

- fibrotic abnormality,
- consolidation-dominant region,
- infection data missing,
- aspiration risk unknown.

Allowed platform output:

- “Alternative pattern prompt is triggered.”
- “Infection and aspiration/organizing pneumonia concern remain visible.”
- “UIP/IPF closure is blocked until reviewed.”
- “Clinical correlation and MDD remain appropriate.”

Blocked output:

- “UIP dominates.”
- “IPF confirmed.”
- “Consolidation irrelevant.”

---

## 16. Required Metadata for Future Test Cases

Each UIP mimic / superimposed-process test case should carry:

| Field | Required |
|---|---|
| test_case_id | yes |
| baseline_pattern_state | yes |
| mimic_state | yes |
| superimposed_process_state | yes |
| acute_overlay_present | yes |
| source_anchor_id | yes |
| input_features | yes |
| supporting_features | yes |
| weakening_features | yes |
| boundary_vetoes | yes |
| missing_evidence | yes |
| mimic_prompts | yes |
| temporal_comparison_status | yes |
| mdd_prompt_visible | yes |
| urgent_review_prompt_visible_where_relevant | yes |
| expected_allowed_output | yes |
| expected_blocked_output | yes |
| diagnostic_authority | yes |
| treatment_authority | yes |
| public_ready | yes |

Required authority values:

| Field | Required Value |
|---|---|
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |

---

## 17. Failure Modes

The following are explicit v0.6.4 failures:

| Failure Mode | Why It Fails |
|---|---|
| Mimic omitted despite missing evidence | Hides uncertainty |
| Acute overlay collapsed into chronic UIP progression | Erases superimposed process |
| Infection excluded without clinical/microbiology evidence | Creates unsupported exclusion |
| Edema excluded without cardiac/volume review | Creates unsupported exclusion |
| Hemorrhage excluded without clinical context | Creates unsupported exclusion |
| Vascular concern hidden despite acute instability | Weakens urgent review visibility |
| HP-like feature ignored | Hides alternative pattern |
| CTD-ILD context missing but not shown | Hides clinical differential |
| Drug toxicity not visible when medication history missing | Hides medication-related mimic |
| Alternative pattern features ignored | Premature UIP/IPF closure |
| MDD prompt absent in complex overlap | Weakens integrated review governance |
| Urgent review prompt absent in acute danger | Weakens safety prompt visibility |
| Treatment recommendation appears | Violates treatment_authority none |
| Public readiness implied | Violates public_ready false |

---

## 18. Acceptance Criteria

v0.6.4 is accepted only if:

- mimic visibility is explicitly preserved,
- superimposed-process visibility is explicitly preserved,
- acute overlay is not collapsed into chronic progression,
- infection remains visible where relevant,
- edema remains visible where relevant,
- hemorrhage remains visible where relevant,
- vascular concern remains visible where relevant,
- HP-like alternative pattern remains visible where relevant,
- CTD-ILD context remains visible where relevant,
- NSIP/sarcoid/occupational/drug/aspiration alternatives remain visible where relevant,
- missing evidence remains visible,
- temporal uncertainty remains visible,
- MDD prompt remains visible,
- urgent review prompt remains visible where relevant,
- diagnostic_authority remains none,
- treatment_authority remains none,
- public_ready remains false.

---

## 19. Next Step

The next recommended step is:

- v0.6.5 — UIP Temporal Comparison Parity

v0.6.5 should make temporal reasoning stricter:

- baseline vs new abnormality,
- stable fibrosis vs progression,
- acute overlay vs chronic worsening,
- prior unavailable vs comparison possible,
- progression claim limits,
- change-before-label enforcement.

It should not create diagnostic authority.

---

## 20. Governance Statement

UIP Mimic and Superimposed Process Parity protects the platform from single-label closure.

It does not diagnose.  
It does not treat.  
It does not exclude mimics.  
It does not confirm acute exacerbation.  
It does not replace radiologist interpretation.  
It does not replace clinical correlation.  
It does not replace microbiology, cardiology review, pathology, MDD, or urgent clinical assessment.  
It does not claim public readiness.

The platform remains an evidence-governed clinical reasoning platform.

It teaches clinicians to read mimic, overlap, acute change, uncertainty, and evidence before naming UIP.