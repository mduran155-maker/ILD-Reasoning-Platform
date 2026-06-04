# ILD Reasoning Platform — UIP MDD and Missing Evidence Prompt Parity v1

Version: v0.6.6  
Status: mdd_missing_evidence_prompt_parity  
Scope: UIP-facing MDD, clinical context, missing evidence, and review-trigger reasoning  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Source Review Date: 2026-06-04  

---

## 1. Purpose

This document defines MDD and missing-evidence prompt parity for UIP-facing reasoning in the ILD Reasoning Platform.

It follows UIP Temporal Comparison Parity.

It does not diagnose UIP.  
It does not diagnose IPF.  
It does not diagnose alternative ILD.  
It does not recommend treatment.  
It does not create public readiness.  
It does not replace radiologist interpretation, clinical correlation, pathology review, microbiology, pulmonology, rheumatology, occupational medicine, MDD, or urgent clinical assessment.

Its purpose is to ensure that UIP-facing reasoning keeps missing evidence and review needs visible.

The platform principle remains:

> “It teaches clinicians to read change before naming disease.”

For v0.6.6, this becomes:

> “Read missing evidence, clinical context, review need, and uncertainty before naming UIP.”

---

## 2. Relationship to Prior v0.6 Files

This file follows:

- `docs/navigation/uip_parity_upgrade_entry_gate_v1.md`
- `docs/navigation/uip_source_anchor_review_map_v1.md`
- `docs/data/schema/uip_pattern_boundary_matrix_v1.md`
- `docs/data/schema/uip_reasoning_parity_rules_v1.md`
- `docs/data/schema/uip_mimic_superimposed_process_parity_v1.md`
- `docs/data/schema/uip_temporal_comparison_parity_v1.md`

v0.6.0 opened UIP parity as reasoning parity.

v0.6.1 mapped source anchors.

v0.6.2 defined pattern-boundary states.

v0.6.3 defined reasoning parity rules.

v0.6.4 preserved mimic and superimposed-process visibility.

v0.6.5 governed temporal comparison.

v0.6.6 now governs missing evidence and MDD prompt visibility.

This document does not add diagnostic authority.

---

## 3. Source Anchors Used

| Source Anchor ID | Role |
|---|---|
| UIP_SRC_2018_ATS_ERS_JRS_ALAT_DX | Official guideline anchor for UIP-facing diagnostic pathway and MDD-sensitive reasoning |
| UIP_SRC_2018_FLEISCHNER_WHITE_PAPER | Verified comparative IPF/UIP diagnostic criteria anchor; clinical context, working diagnosis, MDD, and re-review support |
| UIP_SRC_2020_FLEISCHNER_ILA_POSITION_PAPER | Incidental ILA / early fibrotic abnormality / clinical evaluation and follow-up reasoning support |
| UIP_SRC_INTERNAL_V03_SUPERIMPOSED_EVENTS_CORE | Internal simultaneous-process and overlap reasoning inheritance |
| UIP_SRC_INTERNAL_V04_SOURCE_GOVERNANCE | Source review and limitation governance |
| UIP_SRC_INTERNAL_V05_TEST_COVERAGE_SEAL | Test coverage, missing evidence, mimic, MDD, urgent review inheritance |
| UIP_INTERNAL_V062_PATTERN_BOUNDARY_MATRIX | Pattern-state dependency |
| UIP_INTERNAL_V063_REASONING_PARITY_RULES | Reasoning parity dependency |
| UIP_INTERNAL_V064_MIMIC_SUPERIMPOSED_PROCESS_PARITY | Mimic / overlay dependency |
| UIP_INTERNAL_V065_TEMPORAL_COMPARISON_PARITY | Temporal comparison dependency |

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
| automated_MDD_decision | not allowed |
| automated_biopsy_decision | not allowed |
| automated_treatment_selection | not allowed |
| patient_facing_use | not allowed |
| replacement_of_radiologist | not allowed |
| replacement_of_pathologist | not allowed |
| replacement_of_pulmonologist | not allowed |
| replacement_of_rheumatologist | not allowed |
| replacement_of_occupational_medicine_review | not allowed |
| replacement_of_microbiology | not allowed |
| replacement_of_MDD | not allowed |
| replacement_of_urgent_review | not allowed |

No missing-evidence prompt creates a diagnosis.

No MDD prompt creates a treatment plan.

No review prompt creates clinical deployment authority.

---

## 5. Core Missing Evidence Principle

UIP-facing reasoning must not fill missing evidence by assumption.

Central rule:

> Missing evidence is not negative evidence.

If exposure history is missing, HP or occupational disease is not excluded.

If autoimmune context is missing, CTD-ILD is not excluded.

If infection markers are missing, infection is not excluded.

If cardiac/volume status is missing, edema is not excluded.

If prior imaging is missing, progression is not established.

If MDD is missing, integrated diagnosis is not established.

The platform must show the gap.

---

## 6. Core MDD Principle

MDD prompt parity is context-aware.

The platform must not mechanically force MDD for every classic-looking case if the case is otherwise well-characterized and reviewed by appropriate specialists.

However, the platform must preserve MDD or re-review prompt visibility when:

- clinical context is incomplete,
- CT pattern is indeterminate,
- CT pattern suggests alternative diagnosis,
- probable UIP is being used to support high-confidence reasoning,
- pathology is unavailable but working diagnosis is considered,
- clinical, imaging, pathology, exposure, or temporal data are discordant,
- acute overlay or superimposed process is possible,
- prior working diagnosis becomes inconsistent with new evidence,
- alternative etiologies remain plausible,
- urgent danger or instability is possible.

Central rule:

> MDD is not a checkbox.  
> MDD is the review surface for uncertainty, discordance, and integration.

---

## 7. Missing Evidence State Model

| State | Meaning | Required Platform Behavior |
|---|---|---|
| MISSING_PRIOR_IMAGING | Prior comparison unavailable or incomplete | Block confident progression/stability claims |
| MISSING_CLINICAL_TIMELINE | Symptom duration, pace, or onset unclear | Preserve acute/chronic uncertainty |
| MISSING_HRCT_TECHNIQUE_CONTEXT | Acquisition quality or technique unclear | Preserve pattern confidence limitation |
| MISSING_EXPOSURE_HISTORY | HP, occupational, environmental, or avocational exposure not assessed | Keep HP/occupational mimic visible |
| MISSING_AUTOIMMUNE_CONTEXT | CTD symptoms, signs, or serology not assessed | Keep CTD-ILD visible |
| MISSING_MEDICATION_HISTORY | Drug toxicity or therapy-related ILD not assessed | Keep drug toxicity visible |
| MISSING_INFECTION_DATA | Fever, inflammatory markers, microbiology, BAL context missing where relevant | Keep infection visible |
| MISSING_CARDIAC_VOLUME_DATA | Cardiac function, BNP, volume status, edema context unclear | Keep edema visible |
| MISSING_HEMORRHAGE_CONTEXT | Hemoptysis, anemia, anticoagulation, bleeding risk unknown | Keep hemorrhage visible |
| MISSING_VASCULAR_CONTEXT | PE/vascular risk, acute hypoxemia context unclear | Keep vascular concern visible |
| MISSING_PATHOLOGY_CONTEXT | Biopsy/pathology unavailable or not integrated where relevant | Preserve pathology uncertainty |
| MISSING_MDD_CONTEXT | Integrated clinical-radiologic-pathologic discussion absent where relevant | Preserve MDD prompt |
| MISSING_LONGITUDINAL_BEHAVIOUR | Follow-up behaviour unavailable or discordant | Preserve re-review prompt |

Multiple missing-evidence states may coexist.

The platform must not collapse them into a single generic warning.

---

## 8. MDD Prompt State Model

| MDD State | Meaning | Required Platform Behavior |
|---|---|---|
| MDD_NOT_TRIGGERED_BY_CONTEXT | Case appears well-characterized and no uncertainty trigger is present | Keep non-authority language; do not force universal MDD |
| MDD_PROMPT_VISIBLE | Review is appropriate because uncertainty or incomplete context exists | Show MDD prompt clearly |
| MDD_ESCALATION_PROMPT | Discordance, alternative diagnosis, indeterminate pattern, or complex overlap exists | Elevate MDD visibility |
| MDD_REVIEW_AFTER_BIOPSY_PROMPT | Tissue/pathology must be integrated with imaging and clinical context | Preserve integration prompt |
| MDD_WORKING_DIAGNOSIS_PROMPT | Diagnosis may be provisional because diagnostic tissue or full criteria are unavailable | Require confidence level / reviewability |
| MDD_RE_REVIEW_PROMPT | Prior working diagnosis conflicts with new evidence or disease behaviour | Prompt re-review |
| MDD_URGENT_CONTEXT_PROMPT | Acute danger overlaps with uncertain ILD reasoning | Preserve urgent review and MDD visibility without delaying clinical urgency |

MDD prompt states are not diagnoses.

They are review-routing states.

---

## 9. Missing Evidence Matrix

| Missing Evidence | Why It Matters | Required Prompt | Blocked Closure |
|---|---|---|---|
| Prior HRCT unavailable | Progression/stability cannot be confidently assessed | “Prior imaging comparison is missing.” | “progression confirmed” |
| Clinical timeline unavailable | Acute vs chronic cannot be separated | “Clinical time course is missing.” | “acute/chronic certainty” |
| HRCT technique incomplete | Pattern confidence may be limited | “Technique/acquisition context is incomplete.” | confident pattern boundary |
| Prone imaging unavailable where dependent opacity matters | Dependent opacity may be overcalled as fibrosis | “Dependent atelectasis remains possible.” | confident subpleural fibrosis claim |
| Expiratory imaging unavailable where air trapping matters | HP-like clue may be under-assessed | “Air trapping assessment is incomplete.” | HP exclusion |
| Exposure history missing | HP, occupational disease, pneumoconiosis may be hidden | “Exposure history is missing.” | IPF closure |
| Autoimmune context missing | CTD-ILD may be hidden | “Autoimmune/CTD context is missing.” | IPF closure |
| Medication history missing | Drug toxicity may be hidden | “Medication-related ILD review is incomplete.” | drug toxicity exclusion |
| Infection data missing | Infection may mimic or overlay fibrosis | “Infection evaluation is incomplete.” | infection exclusion |
| Cardiac/volume data missing | Edema may mimic GGO/acute worsening | “Cardiac/volume assessment is incomplete.” | edema exclusion |
| Hemorrhage context missing | Hemorrhage may mimic GGO | “Hemorrhage context is incomplete.” | hemorrhage exclusion |
| Vascular context missing | Acute dyspnea/hypoxemia may have vascular explanation | “Vascular concern remains review-visible.” | chronic progression closure |
| Pathology unavailable | Integrated confidence may be limited in selected cases | “Pathology context is unavailable or not integrated.” | final diagnosis in uncertain case |
| MDD unavailable | Integrated diagnosis not established where review is needed | “MDD review is not documented.” | integrated diagnosis claim |
| Longitudinal behaviour unavailable | Working diagnosis cannot be tested over time | “Longitudinal behaviour is not yet established.” | immutable working diagnosis |

---

## 10. MDD Trigger Matrix

| Trigger | Required MDD / Review Response |
|---|---|
| Indeterminate for UIP pattern | MDD prompt visible |
| Alternative pattern prompt | MDD escalation prompt |
| Probable UIP with incomplete clinical context | MDD prompt visible |
| Typical UIP pattern but exposure/autoimmune/medication context missing | Missing evidence prompt + MDD prompt where relevant |
| UIP-facing pattern with acute overlay | MDD + urgent review visibility |
| Discordant clinical and imaging data | MDD escalation prompt |
| Discordant imaging and pathology | MDD review after biopsy prompt |
| Diagnostic tissue unavailable but working diagnosis considered | Working diagnosis prompt + confidence level visible |
| Prior working diagnosis conflicts with new clinical evidence | Re-review prompt |
| New exposure history appears after prior IPF label | Re-review prompt |
| Autoimmune disease becomes apparent after prior IPF label | Re-review prompt |
| Longitudinal behaviour is unexpected | Re-review prompt |
| Complex overlap of fibrosis, mimic, and acute change | MDD escalation prompt |
| Unclassifiable or mixed pattern concern | MDD prompt visible |

---

## 11. Context-Aware MDD Non-Overcall Rule

MDD prompt should not become a meaningless universal phrase.

The platform should distinguish:

| Situation | MDD Posture |
|---|---|
| Classic CT pattern, correct clinical context, reviewed by experienced radiologist and clinician, no missing major evidence | MDD may be not triggered by context; non-authority still preserved |
| Classic CT pattern but clinical context incomplete | MDD / missing evidence prompt visible |
| Probable UIP pattern with complete clinical context | MDD prompt may be lower intensity but uncertainty remains visible |
| Probable UIP pattern with missing clinical context | MDD prompt visible |
| Indeterminate pattern | MDD prompt visible |
| Alternative pattern | MDD escalation prompt |
| Acute overlay | urgent review + MDD/review prompt visible |
| Working diagnosis without tissue | MDD working diagnosis prompt visible |
| Longitudinal discordance | MDD re-review prompt visible |

This avoids both extremes:

- hiding MDD when it is needed,
- mechanically forcing MDD language when the case is already well-characterized.

---

## 12. Working Diagnosis Safeguards

A working diagnosis prompt must preserve reviewability.

Required safeguards:

| Safeguard | Required State |
|---|---|
| working_diagnosis_not_final | true |
| confidence_level_visible | true |
| missing_evidence_visible | true |
| alternative_explanations_visible | true |
| review_interval_or_re_review_need_visible | true |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |

Allowed output posture:

- “A working diagnosis may be considered only through clinical/MDD integration.”
- “Confidence level should be declared.”
- “The working diagnosis may change with new evidence or longitudinal behaviour.”
- “Alternative explanations remain visible.”

Blocked output posture:

- “Working diagnosis equals final diagnosis.”
- “No further review needed.”
- “Treatment should be started.”
- “Prior working diagnosis is permanent.”

---

## 13. Pathology and Biopsy Evidence Prompt Parity

The platform must not make biopsy decisions.

It may show when pathology context is relevant.

| Pathology / Biopsy Context | Required Prompt |
|---|---|
| CT pattern indeterminate | “Pathology or additional assessment may be relevant through clinical/MDD decision.” |
| CT pattern alternative | “Additional assessment may be considered through clinical/MDD decision.” |
| Pathology available but not integrated | “Pathology must be integrated with clinical and imaging context.” |
| Pathology discordant with CT | “MDD review after biopsy prompt is triggered.” |
| Diagnostic tissue unavailable | “Working diagnosis, if considered, remains provisional and reviewable.” |
| Biopsy risk context unknown | “Biopsy decision cannot be inferred; clinical risk assessment required.” |

Blocked language:

- “Biopsy should be performed.”
- “Biopsy is unnecessary” in uncertain cases without context.
- “Pathology confirms IPF” without integrated review.
- “Platform decides biopsy pathway.”

---

## 14. Clinical Domain Prompt Matrix

| Clinical Domain | Missing Context Prompt | Mimic / Alternative Protected |
|---|---|---|
| Age / demographic context | “Clinical probability context incomplete.” | prevents overconfident IPF framing |
| Smoking history | “Smoking context incomplete.” | smoking-related fibrosis / emphysema confounder |
| Exposure history | “Exposure history incomplete.” | HP / occupational / pneumoconiosis |
| Autoimmune symptoms/signs | “Autoimmune review incomplete.” | CTD-ILD |
| Serology | “Serologic context incomplete.” | CTD-ILD / autoimmune features |
| Medication history | “Medication review incomplete.” | drug toxicity |
| Family history | “Familial fibrosis context incomplete.” | familial ILD |
| Infection context | “Infection data incomplete.” | infection overlay |
| Cardiac/volume context | “Cardiac/volume data incomplete.” | edema |
| Hemorrhage context | “Bleeding/hemorrhage context incomplete.” | hemorrhage |
| Occupational context | “Occupational history incomplete.” | pneumoconiosis/asbestosis |
| Aspiration context | “Aspiration risk incomplete.” | aspiration / OP-like process |
| Pulmonary function trend | “Physiology trend incomplete.” | progression / severity uncertainty |
| Oxygen requirement trend | “Oxygen trend incomplete.” | urgent/acute overlay |
| Prior treatment history | “Treatment history incomplete.” | treated course / longitudinal behaviour uncertainty |

---

## 15. Review Prompt Priority Order

When multiple prompts are present, the platform should prioritize visibility as follows:

1. urgent clinical danger,
2. acute overlay or unstable clinical context,
3. major alternative diagnosis feature,
4. missing evidence that blocks safe closure,
5. MDD escalation prompt,
6. pathology/biopsy integration prompt,
7. temporal comparison prompt,
8. chronic pattern-state description,
9. working diagnosis caveat.

This means:

- safety visibility outranks pattern naming,
- missing evidence can block closure,
- MDD prompt is elevated when integration is needed,
- pattern state remains subordinate to clinical context.

---

## 16. Output Language Guardrails

Allowed language:

- “clinical context is incomplete”
- “missing evidence limits confidence”
- “MDD prompt remains visible”
- “MDD escalation prompt is triggered”
- “working diagnosis, if considered, remains provisional and reviewable”
- “alternative explanations remain visible”
- “pathology context is unavailable or not integrated”
- “prior working diagnosis should be re-reviewed if new evidence conflicts”
- “urgent clinical review may be appropriate depending on context”
- “diagnostic authority remains none”

Blocked language:

- “IPF confirmed by platform”
- “UIP diagnosed”
- “MDD unnecessary” when uncertainty triggers exist
- “exposure history irrelevant”
- “autoimmune disease excluded” without evidence
- “infection excluded” without data
- “edema excluded” without data
- “biopsy should be performed”
- “biopsy is unnecessary” in uncertain cases without context
- “working diagnosis is final”
- “treatment should be started”
- “public-ready”

---

## 17. Testable MDD and Missing Evidence Expectations

Future v0.6 test cases should evaluate:

| Expectation ID | Expectation |
|---|---|
| UME_001 | Missing evidence is explicitly listed |
| UME_002 | Missing evidence is not treated as exclusion |
| UME_003 | MDD prompt appears when uncertainty triggers exist |
| UME_004 | MDD is not mechanically forced when context does not trigger it |
| UME_005 | Alternative explanations remain visible |
| UME_006 | Clinical context dependency remains visible |
| UME_007 | Exposure history gap protects HP/occupational mimic visibility |
| UME_008 | Autoimmune context gap protects CTD-ILD visibility |
| UME_009 | Medication history gap protects drug toxicity visibility |
| UME_010 | Infection data gap protects infection visibility |
| UME_011 | Cardiac/volume gap protects edema visibility |
| UME_012 | Pathology context gap preserves uncertainty where relevant |
| UME_013 | Biopsy decision is not automated |
| UME_014 | Working diagnosis remains provisional and reviewable |
| UME_015 | Prior working diagnosis can be re-reviewed |
| UME_016 | Urgent review prompt remains visible where relevant |
| UME_017 | Diagnostic authority remains none |
| UME_018 | Treatment authority remains none |
| UME_019 | Public readiness remains false |

---

## 18. Example Reasoning Scenarios

### 18.1 Typical UIP Pattern With Complete Clinical Context

Input reasoning context:

- typical UIP-compatible CT features,
- appropriate clinical context documented,
- exposure/autoimmune/medication review documented,
- experienced radiologist and clinician review documented,
- no acute overlay.

Allowed platform output:

- “UIP-pattern compatible features are present.”
- “Clinical context appears sufficiently characterized for pattern reasoning.”
- “MDD may not be mechanically triggered by this context, but diagnostic authority remains none.”
- “No treatment recommendation is made.”

Blocked output:

- “IPF confirmed by platform.”
- “Treatment should begin.”
- “Public-ready diagnosis.”

---

### 18.2 Probable UIP With Missing Exposure History

Input reasoning context:

- probable UIP-pattern candidate,
- no honeycombing,
- exposure history missing,
- HP-like mimic not excluded.

Allowed platform output:

- “Probable UIP-pattern reasoning may be considered.”
- “Exposure history is missing.”
- “HP or occupational mimic remains visible.”
- “MDD prompt remains visible.”

Blocked output:

- “IPF confirmed.”
- “HP excluded.”
- “MDD unnecessary.”

---

### 18.3 Indeterminate Pattern With Missing Technique Context

Input reasoning context:

- indeterminate for UIP,
- prone imaging unavailable,
- HRCT technique incomplete,
- clinical context incomplete.

Allowed platform output:

- “Indeterminate for UIP-pattern reasoning.”
- “Technique/acquisition context is incomplete.”
- “Dependent opacity remains possible where relevant.”
- “MDD prompt remains visible.”

Blocked output:

- “UIP likely.”
- “Indeterminate resolved.”
- “No further review needed.”

---

### 18.4 Alternative Pattern With Autoimmune Gap

Input reasoning context:

- fibrotic ILD,
- extrapulmonary clue or CTD-compatible feature,
- autoimmune symptoms/serology not documented.

Allowed platform output:

- “Alternative or competing pattern prompt is triggered.”
- “Autoimmune/CTD context is missing.”
- “MDD escalation prompt is visible.”
- “UIP/IPF closure is blocked until reviewed.”

Blocked output:

- “IPF diagnosis.”
- “CTD-ILD excluded.”
- “Alternative explanation irrelevant.”

---

### 18.5 Working Diagnosis Without Tissue

Input reasoning context:

- diagnostic tissue unavailable,
- clinical and imaging data suggest possible IPF pathway,
- alternative causes incompletely excluded,
- longitudinal behaviour not yet established.

Allowed platform output:

- “Working diagnosis, if considered, remains provisional and reviewable.”
- “Confidence level should be declared.”
- “Alternative explanations and missing evidence remain visible.”
- “MDD review is required for integration.”

Blocked output:

- “Final diagnosis established.”
- “Working diagnosis is permanent.”
- “No re-review needed.”

---

### 18.6 Prior Working Diagnosis Conflicts With New Evidence

Input reasoning context:

- prior working diagnosis of IPF,
- new exposure or autoimmune evidence appears,
- disease behaviour is discordant.

Allowed platform output:

- “MDD re-review prompt is triggered.”
- “Prior working diagnosis should not be treated as immutable.”
- “Alternative explanation remains visible.”
- “Diagnostic authority remains none.”

Blocked output:

- “Prior diagnosis stands automatically.”
- “New evidence ignored.”
- “MDD unnecessary.”

---

## 19. Required Metadata for Future Test Cases

Each UIP MDD / missing evidence test case should carry:

| Field | Required |
|---|---|
| test_case_id | yes |
| baseline_pattern_state | yes |
| current_pattern_state | yes |
| missing_evidence_states | yes |
| mdd_state | yes |
| clinical_context_status | yes |
| exposure_history_status | yes |
| autoimmune_context_status | yes |
| medication_history_status | yes |
| infection_data_status | yes |
| cardiac_volume_status | yes |
| hemorrhage_context_status | yes |
| vascular_context_status | yes |
| pathology_context_status | yes |
| temporal_comparison_status | yes |
| working_diagnosis_status | yes |
| re_review_trigger | yes |
| urgent_review_prompt_visible_where_relevant | yes |
| expected_allowed_output | yes |
| expected_blocked_output | yes |
| source_anchor_id | yes |
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

## 20. Failure Modes

The following are explicit v0.6.6 failures:

| Failure Mode | Why It Fails |
|---|---|
| Missing evidence hidden | Creates false confidence |
| Missing evidence treated as exclusion | Violates missing evidence principle |
| MDD prompt absent despite uncertainty trigger | Weakens integration governance |
| MDD mechanically forced without context | Creates noisy non-specific review language |
| Exposure gap hidden | Hides HP/occupational mimic |
| Autoimmune gap hidden | Hides CTD-ILD |
| Medication gap hidden | Hides drug toxicity |
| Infection gap hidden | Hides superimposed infection |
| Cardiac/volume gap hidden | Hides edema mimic |
| Pathology gap hidden in uncertain case | Hides diagnostic limitation |
| Biopsy pathway automated | Creates clinical authority |
| Working diagnosis treated as final | Erases reviewability |
| Prior working diagnosis immutable | Blocks longitudinal reasoning |
| Urgent review prompt absent in danger context | Weakens safety visibility |
| Treatment recommendation appears | Violates treatment_authority none |
| Public readiness implied | Violates public_ready false |

---

## 21. Acceptance Criteria

v0.6.6 is accepted only if:

- missing evidence is explicitly represented,
- missing evidence is not treated as exclusion,
- MDD prompt visibility is context-aware,
- MDD is preserved for uncertainty, discordance, alternative pattern, biopsy integration, working diagnosis, and re-review contexts,
- MDD is not mechanically forced when no trigger exists,
- clinical context dependency remains visible,
- exposure history gaps remain visible,
- autoimmune context gaps remain visible,
- medication history gaps remain visible,
- infection/edema/hemorrhage/vascular gaps remain visible where relevant,
- pathology uncertainty remains visible where relevant,
- biopsy decision is not automated,
- working diagnosis remains provisional and reviewable,
- prior working diagnosis can be re-reviewed,
- urgent review prompt remains visible where relevant,
- diagnostic_authority remains none,
- treatment_authority remains none,
- public_ready remains false.

---

## 22. Next Step

The next recommended step is:

- v0.6.7 — UIP Parity Test Case Upgrade Pack

v0.6.7 should convert v0.6.2 through v0.6.6 into upgraded test cases.

It should test:

- UIP pattern boundary reasoning,
- probable UIP non-upgrade,
- indeterminate uncertainty preservation,
- alternative pattern closure block,
- mimic and superimposed process visibility,
- temporal comparison discipline,
- missing evidence prompts,
- context-aware MDD prompts,
- working diagnosis reviewability.

It should not create diagnostic authority.

---

## 23. Governance Statement

UIP MDD and Missing Evidence Prompt Parity protects the platform from silent overconfidence.

It does not diagnose.  
It does not treat.  
It does not decide biopsy.  
It does not confirm IPF.  
It does not replace radiologist interpretation.  
It does not replace clinical correlation.  
It does not replace pathology, microbiology, pulmonology, rheumatology, occupational medicine, MDD, or urgent clinical assessment.  
It does not claim public readiness.

The platform remains an evidence-governed clinical reasoning platform.

It teaches clinicians to read missing evidence, clinical context, review need, uncertainty, and change before naming UIP.