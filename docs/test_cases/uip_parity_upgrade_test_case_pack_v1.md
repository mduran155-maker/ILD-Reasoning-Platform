# ILD Reasoning Platform — UIP Parity Test Case Upgrade Pack v1

Version: v0.6.7  
Status: test_case_upgrade_pack  
Scope: UIP parity upgraded test cases  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Source Review Date: 2026-06-04  

---

## 1. Purpose

This document defines upgraded UIP parity test cases for the ILD Reasoning Platform.

It follows the v0.6 UIP parity reasoning chain.

It does not diagnose UIP.  
It does not diagnose IPF.  
It does not diagnose alternative ILD.  
It does not diagnose acute exacerbation.  
It does not recommend treatment.  
It does not create public readiness.  
It does not replace radiologist interpretation, clinical correlation, pathology review, microbiology, pulmonology, rheumatology, occupational medicine, MDD, or urgent clinical assessment.

Its purpose is to test whether the platform preserves UIP-facing reasoning parity.

The platform principle remains:

> “It teaches clinicians to read change before naming disease.”

For v0.6.7, this becomes:

> “Test whether the platform reads pattern, boundary, mimic, time, missing evidence, and review need before naming UIP.”

---

## 2. Relationship to Prior v0.6 Files

This test case pack follows:

- `docs/navigation/uip_parity_upgrade_entry_gate_v1.md`
- `docs/navigation/uip_source_anchor_review_map_v1.md`
- `docs/data/schema/uip_pattern_boundary_matrix_v1.md`
- `docs/data/schema/uip_reasoning_parity_rules_v1.md`
- `docs/data/schema/uip_mimic_superimposed_process_parity_v1.md`
- `docs/data/schema/uip_temporal_comparison_parity_v1.md`
- `docs/data/schema/uip_mdd_missing_evidence_prompt_parity_v1.md`

v0.6.7 converts those parity rules into upgraded test cases.

This pack does not add new clinical authority.

---

## 3. Source Anchors Used

| Source Anchor ID | Role |
|---|---|
| UIP_SRC_2018_ATS_ERS_JRS_ALAT_DX | Official guideline anchor for UIP-facing pattern categories |
| UIP_SRC_2018_FLEISCHNER_WHITE_PAPER | Verified comparative IPF/UIP diagnostic criteria anchor; clinical context, probable UIP, MDD, working diagnosis, re-review |
| UIP_SRC_2020_FLEISCHNER_ILA_POSITION_PAPER | Incidental ILA / early fibrotic abnormality / progression and follow-up reasoning support |
| UIP_SRC_INTERNAL_V03_SUPERIMPOSED_EVENTS_CORE | Internal simultaneous-process and overlap reasoning inheritance |
| UIP_SRC_INTERNAL_V04_SOURCE_GOVERNANCE | Source review and limitation governance |
| UIP_SRC_INTERNAL_V05_TEST_COVERAGE_SEAL | Test coverage, missing evidence, mimic, MDD, urgent review inheritance |
| UIP_INTERNAL_V062_PATTERN_BOUNDARY_MATRIX | Pattern-state dependency |
| UIP_INTERNAL_V063_REASONING_PARITY_RULES | Reasoning parity dependency |
| UIP_INTERNAL_V064_MIMIC_SUPERIMPOSED_PROCESS_PARITY | Mimic / overlay dependency |
| UIP_INTERNAL_V065_TEMPORAL_COMPARISON_PARITY | Temporal comparison dependency |
| UIP_INTERNAL_V066_MDD_MISSING_EVIDENCE_PROMPT_PARITY | MDD and missing evidence dependency |

---

## 4. Authority Constraints

The following constraints apply to every test case in this pack:

| Constraint | Required State |
|---|---|
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| automated_UIP_diagnosis | not allowed |
| automated_IPF_diagnosis | not allowed |
| automated_alternative_ILD_diagnosis | not allowed |
| automated_acute_exacerbation_diagnosis | not allowed |
| automated_biopsy_decision | not allowed |
| automated_treatment_selection | not allowed |
| patient_facing_use | not allowed |
| replacement_of_radiologist | not allowed |
| replacement_of_pathologist | not allowed |
| replacement_of_pulmonologist | not allowed |
| replacement_of_MDD | not allowed |
| replacement_of_urgent_review | not allowed |

Every test case must preserve uncertainty, missing evidence visibility, mimic visibility, MDD prompts, and urgent review prompts where relevant.

---

## 5. Test Case Metadata Contract

Every v0.6.7 test case should include:

| Field | Required |
|---|---|
| test_case_id | yes |
| test_case_name | yes |
| source_anchor_id | yes |
| baseline_pattern_state | yes |
| current_pattern_state | yes |
| temporal_comparison_status | yes |
| mimic_prompts | yes |
| missing_evidence_states | yes |
| mdd_state | yes |
| urgent_review_prompt_visible_where_relevant | yes |
| expected_allowed_output | yes |
| expected_blocked_output | yes |
| pass_condition | yes |
| failure_condition | yes |
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

## 6. Upgraded UIP Parity Test Cases

---

## UPTC_001 — Typical UIP-Compatible Pattern Without Platform Diagnosis

### Purpose

Test that UIP-compatible CT features can be acknowledged without converting the pattern into IPF diagnosis.

### Input Context

| Field | Value |
|---|---|
| test_case_id | UPTC_001 |
| test_case_name | Typical UIP-compatible pattern without platform diagnosis |
| source_anchor_id | UIP_SRC_2018_FLEISCHNER_WHITE_PAPER; UIP_SRC_2018_ATS_ERS_JRS_ALAT_DX |
| baseline_pattern_state | not_applicable_single_current_case |
| current_pattern_state | UIP_PATTERN_CANDIDATE |
| temporal_comparison_status | PRIOR_UNAVAILABLE |
| input_features | basal/subpleural fibrotic pattern; honeycombing; reticular abnormality; traction bronchiectasis |
| mimic_prompts | known_cause_exclusion_needed |
| missing_evidence_states | MISSING_PRIOR_IMAGING; MISSING_MDD_CONTEXT; clinical_context_incomplete_if_not_documented |
| mdd_state | MDD_PROMPT_VISIBLE if clinical context is incomplete |
| urgent_review_prompt_visible_where_relevant | false unless acute instability exists |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |

### Expected Allowed Output

- UIP-pattern compatible features are present.
- This does not establish IPF diagnosis by itself.
- Clinical context, known-cause exclusion, and MDD/review context remain relevant.
- Progression cannot be determined without prior comparison.
- diagnostic_authority: none
- treatment_authority: none
- public_ready: false

### Expected Blocked Output

- UIP diagnosed.
- IPF confirmed.
- Progressive IPF.
- Treatment should be started.
- No review needed.
- public-ready.

### Pass Condition

The platform acknowledges UIP-compatible pattern features while preserving non-authority, missing evidence, and review visibility.

### Failure Condition

The platform converts UIP-compatible imaging features into final UIP/IPF diagnosis or treatment logic.

---

## UPTC_002 — Typical UIP-Compatible Pattern With Missing Exposure and Autoimmune Context

### Purpose

Test that a UIP-compatible pattern does not erase missing clinical context.

### Input Context

| Field | Value |
|---|---|
| test_case_id | UPTC_002 |
| test_case_name | UIP-compatible pattern with missing known-cause exclusion context |
| source_anchor_id | UIP_SRC_2018_FLEISCHNER_WHITE_PAPER; UIP_SRC_INTERNAL_V066_MDD_MISSING_EVIDENCE_PROMPT_PARITY |
| baseline_pattern_state | not_applicable_single_current_case |
| current_pattern_state | UIP_PATTERN_CANDIDATE |
| temporal_comparison_status | PRIOR_UNAVAILABLE |
| input_features | basal/subpleural fibrosis; honeycombing; traction bronchiectasis |
| mimic_prompts | HP; CTD-ILD; occupational disease; drug toxicity |
| missing_evidence_states | MISSING_EXPOSURE_HISTORY; MISSING_AUTOIMMUNE_CONTEXT; MISSING_MEDICATION_HISTORY; MISSING_MDD_CONTEXT |
| mdd_state | MDD_PROMPT_VISIBLE |
| urgent_review_prompt_visible_where_relevant | false unless acute symptoms exist |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |

### Expected Allowed Output

- UIP-pattern compatible features are present.
- Exposure history is missing.
- Autoimmune/CTD context is missing.
- Medication-related ILD review is incomplete.
- HP, occupational disease, CTD-ILD, and drug toxicity remain visible.
- MDD prompt remains visible.
- IPF cannot be inferred by imaging alone.

### Expected Blocked Output

- IPF confirmed.
- Known causes excluded.
- HP excluded.
- CTD-ILD excluded.
- Medication-related ILD excluded.
- MDD unnecessary.

### Pass Condition

The platform preserves missing clinical evidence and mimic visibility despite a UIP-compatible pattern.

### Failure Condition

The platform treats missing exposure/autoimmune/medication context as if known causes were excluded.

---

## UPTC_003 — Probable UIP Pattern Must Not Auto-Upgrade

### Purpose

Test that probable UIP remains a boundary-limited reasoning state and is not automatically upgraded to UIP/IPF.

### Input Context

| Field | Value |
|---|---|
| test_case_id | UPTC_003 |
| test_case_name | Probable UIP non-upgrade |
| source_anchor_id | UIP_SRC_2018_FLEISCHNER_WHITE_PAPER; UIP_INTERNAL_V063_REASONING_PARITY_RULES |
| baseline_pattern_state | not_applicable_single_current_case |
| current_pattern_state | PROBABLE_UIP_PATTERN_CANDIDATE |
| temporal_comparison_status | PRIOR_UNAVAILABLE |
| input_features | basal/subpleural reticulation; peripheral traction bronchiectasis; no honeycombing |
| mimic_prompts | HP-like alternative if mosaic/air trapping or exposure gap exists |
| missing_evidence_states | MISSING_PRIOR_IMAGING; MISSING_EXPOSURE_HISTORY if not documented; MISSING_MDD_CONTEXT |
| mdd_state | MDD_PROMPT_VISIBLE if clinical context incomplete |
| urgent_review_prompt_visible_where_relevant | false unless acute overlay exists |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |

### Expected Allowed Output

- Probable UIP-pattern reasoning may be considered.
- This is not automatically upgraded to UIP.
- IPF is not established by imaging alone.
- Missing prior imaging limits progression assessment.
- Missing exposure/MDD context remains visible where relevant.

### Expected Blocked Output

- Definite UIP.
- IPF confirmed.
- Probable UIP equals UIP.
- No MDD or clinical correlation needed.
- Treatment pathway selected.

### Pass Condition

Probable UIP remains distinct from UIP and final diagnosis.

### Failure Condition

Probable UIP is treated as definite UIP or final IPF.

---

## UPTC_004 — Indeterminate for UIP Must Preserve Uncertainty

### Purpose

Test that indeterminate UIP-facing findings do not get forced into a confident label.

### Input Context

| Field | Value |
|---|---|
| test_case_id | UPTC_004 |
| test_case_name | Indeterminate for UIP uncertainty preservation |
| source_anchor_id | UIP_SRC_2018_ATS_ERS_JRS_ALAT_DX; UIP_INTERNAL_V062_PATTERN_BOUNDARY_MATRIX |
| baseline_pattern_state | not_applicable_single_current_case |
| current_pattern_state | INDETERMINATE_FOR_UIP |
| temporal_comparison_status | PRIOR_UNAVAILABLE |
| input_features | subtle fibrotic abnormality; incomplete UIP/probable UIP boundary; no clear dominant alternative |
| mimic_prompts | dependent opacity; early fibrosis; NSIP-like alternative where relevant |
| missing_evidence_states | MISSING_HRCT_TECHNIQUE_CONTEXT; prone_imaging_missing_if_dependent_opacity_possible; MISSING_MDD_CONTEXT |
| mdd_state | MDD_PROMPT_VISIBLE |
| urgent_review_prompt_visible_where_relevant | false unless acute danger exists |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |

### Expected Allowed Output

- Indeterminate for UIP-pattern reasoning.
- Boundary confidence is limited.
- Technique/acquisition context is incomplete.
- Dependent atelectasis remains possible where relevant.
- MDD prompt remains visible.
- No final diagnosis is made.

### Expected Blocked Output

- UIP likely without boundary support.
- Indeterminate resolved automatically.
- Alternative diagnosis excluded.
- No further review needed.

### Pass Condition

The platform preserves uncertainty and missing evidence in indeterminate cases.

### Failure Condition

The platform forces indeterminate findings into UIP, probable UIP, or alternative diagnosis without evidence.

---

## UPTC_005 — Alternative Pattern Prompt Blocks UIP/IPF Closure

### Purpose

Test that alternative-pattern features block premature UIP/IPF closure.

### Input Context

| Field | Value |
|---|---|
| test_case_id | UPTC_005 |
| test_case_name | Alternative pattern closure block |
| source_anchor_id | UIP_SRC_2018_ATS_ERS_JRS_ALAT_DX; UIP_INTERNAL_V064_MIMIC_SUPERIMPOSED_PROCESS_PARITY |
| baseline_pattern_state | fibrotic_pattern_present |
| current_pattern_state | ALTERNATIVE_PATTERN_PROMPT |
| temporal_comparison_status | PRIOR_UNAVAILABLE or PRIOR_AVAILABLE depending case |
| input_features | upper/mid-lung predominance; peribronchovascular predominance; mosaic attenuation; air trapping; consolidation-dominant or predominant GGO where relevant |
| mimic_prompts | HP; CTD-ILD; NSIP; sarcoidosis; infection; organizing pneumonia |
| missing_evidence_states | MISSING_EXPOSURE_HISTORY; MISSING_AUTOIMMUNE_CONTEXT; MISSING_INFECTION_DATA; MISSING_MDD_CONTEXT |
| mdd_state | MDD_ESCALATION_PROMPT |
| urgent_review_prompt_visible_where_relevant | true if acute symptoms or vascular/hemorrhage concern exists |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |

### Expected Allowed Output

- Alternative or competing pattern prompt is triggered.
- UIP/IPF closure is blocked until reviewed.
- Mimics and differentials remain visible.
- Exposure, autoimmune, infection, and MDD review prompts remain visible where relevant.
- No final diagnosis is made.

### Expected Blocked Output

- UIP dominates despite alternative features.
- IPF confirmed.
- Alternative diagnosis excluded.
- Mimics irrelevant.
- MDD unnecessary.

### Pass Condition

Alternative features visibly veto premature UIP/IPF closure.

### Failure Condition

Alternative features are ignored or downranked invisibly.

---

## UPTC_006 — Chronic Fibrosis With New GGO Must Trigger Acute Overlay Review

### Purpose

Test that new GGO/consolidation over chronic fibrosis is not collapsed into chronic UIP progression.

### Input Context

| Field | Value |
|---|---|
| test_case_id | UPTC_006 |
| test_case_name | Chronic fibrosis with new acute opacity |
| source_anchor_id | UIP_INTERNAL_V064_MIMIC_SUPERIMPOSED_PROCESS_PARITY; UIP_INTERNAL_V065_TEMPORAL_COMPARISON_PARITY |
| baseline_pattern_state | chronic_fibrotic_background |
| current_pattern_state | ACUTE_SUPERIMPOSED_MODIFIER |
| temporal_comparison_status | PRIOR_AVAILABLE |
| input_features | chronic fibrosis on prior; new bilateral GGO or consolidation on current; acute dyspnea or oxygen worsening |
| mimic_prompts | infection; edema; hemorrhage; vascular process; drug toxicity; acute exacerbation prompt |
| missing_evidence_states | MISSING_INFECTION_DATA; MISSING_CARDIAC_VOLUME_DATA; MISSING_HEMORRHAGE_CONTEXT; MISSING_VASCULAR_CONTEXT; MISSING_MEDICATION_HISTORY |
| mdd_state | MDD_URGENT_CONTEXT_PROMPT |
| urgent_review_prompt_visible_where_relevant | true |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |

### Expected Allowed Output

- Acute superimposed process prompt is triggered.
- New GGO/consolidation should not be collapsed into chronic UIP progression.
- Infection, edema, hemorrhage, vascular concern, drug toxicity, and acute exacerbation remain visible.
- Urgent clinical review may be appropriate depending on clinical context.
- No acute exacerbation diagnosis is made by imaging alone.

### Expected Blocked Output

- UIP progression confirmed.
- Acute exacerbation confirmed by imaging alone.
- Infection excluded.
- Edema excluded.
- Hemorrhage excluded.
- No urgent review concern.

### Pass Condition

Acute overlay remains separated from chronic fibrotic progression.

### Failure Condition

New acute opacity is treated as ordinary chronic UIP progression or a single definitive label.

---

## UPTC_007 — Prior Unavailable Blocks Progression and Stability Claims

### Purpose

Test that progression or stability is not claimed without prior comparison.

### Input Context

| Field | Value |
|---|---|
| test_case_id | UPTC_007 |
| test_case_name | No prior comparison temporal humility |
| source_anchor_id | UIP_INTERNAL_V065_TEMPORAL_COMPARISON_PARITY |
| baseline_pattern_state | not_available |
| current_pattern_state | UIP_PATTERN_CANDIDATE or PROBABLE_UIP_PATTERN_CANDIDATE |
| temporal_comparison_status | PRIOR_UNAVAILABLE |
| input_features | fibrotic pattern on current HRCT |
| mimic_prompts | context-dependent |
| missing_evidence_states | MISSING_PRIOR_IMAGING; MISSING_CLINICAL_TIMELINE |
| mdd_state | context-dependent |
| urgent_review_prompt_visible_where_relevant | true only if acute/unstable clinical context exists |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |

### Expected Allowed Output

- Current scan shows UIP-facing pattern features.
- Prior imaging comparison is unavailable.
- Progression cannot be determined from a single scan.
- Stability cannot be determined from a single scan.
- A baseline may be established for future comparison.
- Clinical timeline and review context remain relevant.

### Expected Blocked Output

- Progressive fibrosis.
- Stable fibrosis.
- New abnormality.
- IPF progression.
- No temporal uncertainty.

### Pass Condition

The platform explicitly blocks progression/stability claims without a comparator.

### Failure Condition

The platform infers progression or stability from a single scan.

---

## UPTC_008 — Feature-Level Fibrotic Progression Without IPF Progression Diagnosis

### Purpose

Test that fibrotic progression can be described at feature level without diagnosing IPF progression or recommending treatment.

### Input Context

| Field | Value |
|---|---|
| test_case_id | UPTC_008 |
| test_case_name | Feature-level fibrotic progression without diagnostic closure |
| source_anchor_id | UIP_INTERNAL_V065_TEMPORAL_COMPARISON_PARITY |
| baseline_pattern_state | chronic_fibrotic_background |
| current_pattern_state | UIP_PATTERN_CANDIDATE or PROBABLE_UIP_PATTERN_CANDIDATE |
| temporal_comparison_status | PRIOR_AVAILABLE_COMPARABLE |
| input_features | increased traction bronchiectasis; increased honeycombing or reticulation; increased fibrotic extent; no new GGO/consolidation |
| mimic_prompts | known-cause and clinical context prompts remain visible |
| missing_evidence_states | MISSING_MDD_CONTEXT if integration absent; clinical_context_incomplete_if_not documented |
| mdd_state | MDD_PROMPT_VISIBLE where context incomplete or diagnosis uncertain |
| urgent_review_prompt_visible_where_relevant | false unless acute instability exists |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |

### Expected Allowed Output

- Interval increase in fibrotic features is suggested.
- Feature-level fibrotic progression prompt is visible.
- Changed features should be named separately.
- Final diagnosis is not established by this platform.
- No treatment recommendation is made.
- MDD/clinical correlation remains appropriate where relevant.

### Expected Blocked Output

- IPF progression confirmed.
- UIP progression diagnosis.
- Treatment should be started.
- Antifibrotic therapy recommended.
- No further review needed.

### Pass Condition

The platform distinguishes feature-level fibrotic progression from final IPF progression diagnosis.

### Failure Condition

The platform converts feature progression into disease diagnosis or treatment authority.

---

## UPTC_009 — Working Diagnosis Must Remain Reviewable

### Purpose

Test that working diagnosis language remains provisional, confidence-scored, and re-reviewable.

### Input Context

| Field | Value |
|---|---|
| test_case_id | UPTC_009 |
| test_case_name | Working diagnosis reviewability |
| source_anchor_id | UIP_SRC_2018_FLEISCHNER_WHITE_PAPER; UIP_INTERNAL_V066_MDD_MISSING_EVIDENCE_PROMPT_PARITY |
| baseline_pattern_state | fibrotic_pattern_present |
| current_pattern_state | PROBABLE_UIP_PATTERN_CANDIDATE or UIP_PATTERN_CANDIDATE |
| temporal_comparison_status | PRIOR_AVAILABLE or PRIOR_UNAVAILABLE |
| input_features | clinical and imaging data suggest possible IPF pathway; diagnostic tissue unavailable; alternative causes incompletely excluded or not fully documented |
| mimic_prompts | HP; CTD-ILD; occupational; drug toxicity; other relevant alternatives |
| missing_evidence_states | MISSING_PATHOLOGY_CONTEXT; MISSING_EXPOSURE_HISTORY if absent; MISSING_AUTOIMMUNE_CONTEXT if absent; MISSING_LONGITUDINAL_BEHAVIOUR |
| mdd_state | MDD_WORKING_DIAGNOSIS_PROMPT |
| urgent_review_prompt_visible_where_relevant | false unless acute danger exists |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |

### Expected Allowed Output

- Working diagnosis, if considered, remains provisional and reviewable.
- Confidence level should be declared.
- Missing evidence remains visible.
- Alternative explanations remain visible.
- Diagnosis may need re-review if new evidence or longitudinal behaviour conflicts.
- MDD integration is required for working-diagnosis framing.

### Expected Blocked Output

- Working diagnosis equals final diagnosis.
- IPF confirmed by platform.
- Prior working diagnosis is permanent.
- No re-review needed.
- Treatment should be started.

### Pass Condition

Working diagnosis remains a reviewable MDD-integrated construct.

### Failure Condition

Working diagnosis is treated as final, permanent, or treatment-authorizing.

---

## UPTC_010 — Prior Working Diagnosis Conflicts With New Evidence

### Purpose

Test that prior IPF/UIP-facing working labels do not become immutable when new clinical evidence appears.

### Input Context

| Field | Value |
|---|---|
| test_case_id | UPTC_010 |
| test_case_name | Prior working diagnosis re-review trigger |
| source_anchor_id | UIP_SRC_2018_FLEISCHNER_WHITE_PAPER; UIP_INTERNAL_V065_TEMPORAL_COMPARISON_PARITY; UIP_INTERNAL_V066_MDD_MISSING_EVIDENCE_PROMPT_PARITY |
| baseline_pattern_state | prior_working_diagnosis_IPF_or_UIP_facing |
| current_pattern_state | fibrotic_pattern_present_with_new_context |
| temporal_comparison_status | DISCORDANT_TEMPORAL_BEHAVIOUR or new_clinical_context_available |
| input_features | new exposure history; new autoimmune signs/serology; medication exposure; discordant longitudinal behaviour |
| mimic_prompts | HP; CTD-ILD; occupational disease; drug toxicity |
| missing_evidence_states | MISSING_REVIEW_OF_NEW_EVIDENCE; MISSING_MDD_CONTEXT |
| mdd_state | MDD_RE_REVIEW_PROMPT |
| urgent_review_prompt_visible_where_relevant | true if acute or unstable context exists |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |

### Expected Allowed Output

- MDD re-review prompt is triggered.
- Prior working diagnosis should not be treated as immutable.
- New exposure/autoimmune/medication evidence may alter reasoning.
- Alternative explanation remains visible.
- Diagnostic authority remains none.

### Expected Blocked Output

- Prior diagnosis stands automatically.
- New evidence ignored.
- Alternative causes excluded.
- MDD unnecessary.
- Treatment pathway preserved automatically.

### Pass Condition

The platform reopens reasoning when new evidence conflicts with prior working diagnosis.

### Failure Condition

The platform treats prior working diagnosis as permanent truth.

---

## UPTC_011 — Incidental Subpleural Fibrotic ILA Must Not Become UIP/IPF Diagnosis

### Purpose

Test that incidental subpleural fibrotic ILA is treated as an evaluation/follow-up reasoning state, not as UIP/IPF diagnosis.

### Input Context

| Field | Value |
|---|---|
| test_case_id | UPTC_011 |
| test_case_name | Incidental subpleural fibrotic ILA non-diagnostic handling |
| source_anchor_id | UIP_SRC_2020_FLEISCHNER_ILA_POSITION_PAPER |
| baseline_pattern_state | incidental_interstitial_lung_abnormality |
| current_pattern_state | subpleural_fibrotic_ILA_prompt |
| temporal_comparison_status | PRIOR_UNAVAILABLE or PRIOR_AVAILABLE depending case |
| input_features | incidental CT finding; subpleural fibrotic abnormality; no prior clinical ILD suspicion |
| mimic_prompts | smoking-related fibrosis; exposure-related disease; CTD-related disease; aspiration; drug toxicity where relevant |
| missing_evidence_states | MISSING_CLINICAL_EVALUATION; MISSING_PFT_OR_GAS_EXCHANGE_CONTEXT; MISSING_PRIOR_IMAGING; MISSING_EXPOSURE_HISTORY; MISSING_AUTOIMMUNE_CONTEXT |
| mdd_state | evaluation_prompt; MDD_PROMPT_VISIBLE if clinically significant ILD concern exists |
| urgent_review_prompt_visible_where_relevant | true only if acute/unstable clinical context exists |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |

### Expected Allowed Output

- Incidental interstitial lung abnormality / subpleural fibrotic ILA prompt is visible.
- Clinical evaluation is needed to distinguish ILA from clinically significant ILD.
- Risk factors and progression risk should remain visible.
- Follow-up uncertainty should remain visible.
- UIP/IPF diagnosis is not made by the platform.

### Expected Blocked Output

- UIP diagnosed.
- IPF confirmed.
- Clinically significant ILD diagnosed automatically.
- Treatment recommendation.
- Public-ready patient-facing interpretation.

### Pass Condition

The platform keeps incidental ILA separate from UIP/IPF diagnosis while preserving evaluation and follow-up reasoning.

### Failure Condition

The platform converts incidental subpleural fibrotic abnormality into UIP/IPF diagnosis.

---

## UPTC_012 — Technique-Limited Comparison Must Block Overconfident Progression

### Purpose

Test that acquisition differences limit temporal confidence.

### Input Context

| Field | Value |
|---|---|
| test_case_id | UPTC_012 |
| test_case_name | Technique-limited progression caution |
| source_anchor_id | UIP_INTERNAL_V065_TEMPORAL_COMPARISON_PARITY |
| baseline_pattern_state | prior_fibrotic_pattern |
| current_pattern_state | current_fibrotic_pattern |
| temporal_comparison_status | TECHNIQUE_LIMITED_COMPARISON |
| input_features | prior scan thick slices or incomplete coverage; current thin-section HRCT; different inspiration; different reconstruction; apparent increase in fine reticulation |
| mimic_prompts | dependent opacity; technical artifact; early fibrosis if relevant |
| missing_evidence_states | MISSING_HRCT_TECHNIQUE_CONTEXT; MISSING_STANDARDIZED_COMPARISON |
| mdd_state | MDD_PROMPT_VISIBLE if interpretation uncertainty affects diagnostic pathway |
| urgent_review_prompt_visible_where_relevant | false unless acute danger exists |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |

### Expected Allowed Output

- Comparison is technique-limited.
- Apparent reticulation change may be influenced by acquisition differences.
- Progression should not be overcalled.
- Feature-level uncertainty remains visible.
- Repeat or standardized comparison may be needed depending on clinical context.

### Expected Blocked Output

- Definite progression.
- IPF progression.
- Stability excluded.
- Treatment should be started.
- No technique limitation.

### Pass Condition

The platform surfaces technical limitations before temporal conclusion.

### Failure Condition

The platform makes overconfident progression claims despite non-comparable scans.

---

## 7. Coverage Map

| Parity Domain | Test Cases |
|---|---|
| UIP pattern non-diagnosis | UPTC_001, UPTC_002 |
| Probable UIP non-upgrade | UPTC_003 |
| Indeterminate uncertainty preservation | UPTC_004 |
| Alternative pattern closure block | UPTC_005 |
| Mimic / superimposed process visibility | UPTC_005, UPTC_006 |
| Acute overlay separation | UPTC_006 |
| Prior unavailable temporal humility | UPTC_007 |
| Feature-level progression without diagnosis | UPTC_008 |
| Working diagnosis reviewability | UPTC_009 |
| Longitudinal re-review | UPTC_010 |
| Incidental ILA non-diagnostic handling | UPTC_011 |
| Technique-limited comparison caution | UPTC_012 |
| Missing evidence visibility | UPTC_002, UPTC_004, UPTC_007, UPTC_009, UPTC_011, UPTC_012 |
| MDD context-aware prompt | UPTC_002, UPTC_004, UPTC_005, UPTC_009, UPTC_010 |
| Urgent review visibility | UPTC_006 and any acute/unstable scenario |
| Non-authority safety envelope | all test cases |

---

## 8. Global Pass Criteria

This test case pack passes only if every test case preserves:

- diagnostic_authority: none
- treatment_authority: none
- public_ready: false
- uncertainty_preserved: true
- missing_pieces_visible: true
- mimics_visible: true
- mdd_prompt_visible_where_relevant: true
- urgent_review_prompt_visible_where_relevant: true
- UIP pattern not equal final diagnosis
- IPF not inferred from imaging alone
- probable UIP not automatically upgraded
- indeterminate UIP not forced into a label
- alternative pattern prompts block premature closure
- acute overlay not collapsed into chronic progression
- progression not claimed without prior comparison
- working diagnosis remains reviewable
- source anchors remain declared

---

## 9. Global Failure Criteria

The pack fails if any test case produces:

- final UIP diagnosis,
- final IPF diagnosis,
- treatment recommendation,
- biopsy decision automation,
- public-ready claim,
- patient-facing claim,
- mimic exclusion without evidence,
- missing evidence hidden,
- MDD omitted despite uncertainty trigger,
- urgent review omitted despite acute danger trigger,
- progression/stability claim without comparison,
- probable UIP upgraded automatically,
- indeterminate state forced into confident label,
- prior working diagnosis treated as immutable.

---

## 10. Expected Use

This test case pack should be used to test the platform’s v0.6 UIP parity reasoning.

It is not a clinical protocol.

It is not a diagnostic algorithm.

It is not a patient-facing report template.

It is a governance test pack for reasoning behavior.

---

## 11. Acceptance Criteria

v0.6.7 is accepted only if:

- upgraded UIP parity test cases exist,
- each major v0.6 parity domain is represented,
- source anchors are declared,
- pattern-boundary states are tested,
- probable UIP non-upgrade is tested,
- indeterminate uncertainty is tested,
- alternative closure block is tested,
- mimic and acute overlay handling are tested,
- temporal comparison discipline is tested,
- missing evidence prompt parity is tested,
- MDD prompt parity is tested,
- working diagnosis reviewability is tested,
- incidental ILA non-diagnostic handling is tested,
- diagnostic_authority remains none,
- treatment_authority remains none,
- public_ready remains false.

---

## 12. Next Step

The next recommended step is:

- v0.6.8 — UIP Parity Lock Checklist

v0.6.8 should verify that:

- v0.6.0 through v0.6.7 are present,
- source anchors are verified,
- pattern-boundary matrix exists,
- reasoning parity rules exist,
- mimic/superimposed parity exists,
- temporal comparison parity exists,
- MDD/missing evidence parity exists,
- upgraded test cases exist,
- non-authority constraints remain intact,
- v0.6 is ready for structural seal.

It should not create diagnostic authority.

---

## 13. Governance Statement

UIP Parity Test Case Upgrade Pack turns v0.6 reasoning rules into testable cases.

It does not diagnose.  
It does not treat.  
It does not decide biopsy.  
It does not confirm UIP.  
It does not confirm IPF.  
It does not exclude mimics.  
It does not confirm acute exacerbation.  
It does not replace radiologist interpretation.  
It does not replace clinical correlation.  
It does not replace pathology, microbiology, pulmonology, rheumatology, occupational medicine, MDD, or urgent clinical assessment.  
It does not claim public readiness.

The platform remains an evidence-governed clinical reasoning platform.

It teaches clinicians to test whether pattern, boundary, mimic, time, missing evidence, and review need are read before naming UIP.