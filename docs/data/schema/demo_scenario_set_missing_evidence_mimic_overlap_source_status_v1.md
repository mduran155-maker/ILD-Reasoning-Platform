# ILD Reasoning Platform — Demo Scenario Set: Missing Evidence / Mimic / Overlap / Source Status v1

Version: v0.14.3  
Status: demo_scenario_set_missing_evidence_mimic_overlap_source_status  
Scope: First governed synthetic scenario set for missing evidence preservation, mimic visibility, overlap preservation, source status limitation, temporal limiter behavior, and safe export boundary demonstration  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This document defines the first governed synthetic demo scenario set for v0.14 — Demo Case Pack / Non-Clinical Synthetic Validation Scenario Contract.

It follows:

- `docs/navigation/demo_case_pack_non_clinical_synthetic_validation_entry_gate_v1.md`
- `docs/data/schema/synthetic_demo_case_object_schema_v1.md`
- `docs/data/schema/demo_reasoning_session_snapshot_export_fixture_schema_v1.md`
- `docs/navigation/project_status_roadmap_checkpoint_v0_13.md`
- `docs/navigation/safe_session_export_mdd_preparation_structural_seal_v1.md`
- `docs/navigation/case_assembly_reasoning_session_structural_seal_v1.md`
- `docs/navigation/evidence_intake_structural_seal_v1.md`
- `docs/navigation/clinician_workspace_structural_seal_v1.md`
- `docs/navigation/reasoning_output_contract_structural_seal_v1.md`

This document does not add new clinical content.

It does not diagnose.  
It does not treat.  
It does not decide tests.  
It does not decide procedures.  
It does not schedule follow-up.  
It does not exclude mimics.  
It does not replace MDD.  
It does not create public readiness.  
It does not make the platform clinically reviewed.  
It does not create patient-facing use.  
It does not use real patient data.  
It does not clinically validate the platform.

Its purpose is to define synthetic demo scenarios that demonstrate platform governance behavior across:

- missing evidence preservation,
- source status limitation preservation,
- confidence limiter preservation,
- high-risk mimic visibility,
- overlap and unresolved boundary preservation,
- review prompt visibility,
- temporal limitation handling,
- safe export preservation,
- authority envelope persistence,
- no-decision object persistence,
- audit traceability.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.14 rule remains:

> “A demo case may demonstrate governance behavior, but it must not demonstrate clinical validation, product readiness, real patient use, diagnosis, treatment, order, procedure decision, follow-up schedule, triage, public-ready output, or patient-facing use.”

For v0.14.3:

> “A demo scenario is valid only if it demonstrates boundary behavior without creating diagnosis, exclusion, treatment, action, probability, clinical validation, real patient use, public readiness, or patient-facing output.”

---

## 2. Global Demo Scenario Contract

Every scenario in this set must preserve:

| Constraint | Required State |
|---|---|
| synthetic_only | true |
| real_patient_data | false |
| deidentified_real_patient_data | false |
| clinical_validation_use | false |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| product_ready | false |
| clinically_reviewed.platform_wide | false |
| patient_facing_use | not_allowed |
| automated_diagnosis | not_allowed |
| automated_exclusion | not_allowed |
| automated_treatment_selection | not_allowed |
| automated_test_order | not_allowed |
| automated_procedure_decision | not_allowed |
| automated_follow_up_schedule | not_allowed |
| automated_triage | not_allowed |
| replacement_of_MDD | not_allowed |

No demo scenario may contain real patient data, diagnostic ground truth, final diagnosis, excluded disease, treatment plan, procedure recommendation, follow-up schedule, triage decision, patient-facing output, public-ready claim, or clinical validation claim.

---

## 3. Demo Scenario Set Registry

The first governed scenario set contains eight primary synthetic scenarios.

| Scenario ID | Scenario Name | Primary Demonstration |
|---|---|---|
| V14_SCENARIO_001 | UIP-like fibrotic pattern with exposure history missing | Missing evidence does not exclude HP |
| V14_SCENARIO_002 | Fibrotic ILD with CTD/SARD context missing | CTD-ILD visibility remains limited and review-visible |
| V14_SCENARIO_003 | Sarcoid-like nodal/perilymphatic pattern with beryllium history missing | Sarcoid/beryllium overlap remains unresolved |
| V14_SCENARIO_004 | OP-like consolidation with microbiology missing | Infection mimic remains visible |
| V14_SCENARIO_005 | Oncology context with septal/peribronchovascular pattern | PLC/malignancy mimic visibility preserved |
| V14_SCENARIO_006 | ICI exposure with new inflammatory findings | CIP/infection/progression overlap preserved |
| V14_SCENARIO_007 | Prior CT unavailable | Temporal limiter active; no stability/progression claim |
| V14_SCENARIO_008 | Source-status limitation demonstration | Source role and limitation remain visible without authority |

These scenarios are synthetic governance fixtures.

They are not clinical templates.

They are not diagnostic cases.

They are not validation cases.

---

## 4. Scenario Object Template

Every scenario in this file should follow this template.

```yaml
demo_scenario:
  scenario_id: string
  scenario_schema_version: demo_scenario_set_missing_evidence_mimic_overlap_source_status_v1
  scenario_title: string
  scenario_status: synthetic_governance_demo
  synthetic_only: true
  real_patient_data: false
  clinical_validation_use: false

  scenario_purpose: string
  primary_governance_behavior: string
  secondary_governance_behaviors: list

  synthetic_case_context:
    fictional_demographics: object
    fictional_imaging_context: object
    fictional_clinical_context: object

  not_provided_fields: list
  source_status_fixtures: list
  expected_missing_evidence_behavior: list
  expected_confidence_limiter_behavior: list
  expected_mimic_visibility_behavior: list
  expected_overlap_behavior: list
  expected_review_prompt_behavior: list
  expected_snapshot_behavior: list
  expected_export_behavior: list
  expected_audit_behavior: list

  blocked_outputs:
    final_diagnosis: blocked
    disease_exclusion: blocked
    mimic_exclusion: blocked
    treatment_plan: blocked
    test_order: blocked
    procedure_decision: blocked
    follow_up_schedule: blocked
    triage_decision: blocked
    patient_facing_output: blocked
    public_ready_output: blocked
    clinical_validation_claim: blocked

  authority_envelope_required: true
  no_decision_object_required: true
  audit_traceability_required: true
```

Scenario template rule:

> Every scenario must explicitly state expected safe behavior and blocked unsafe behavior.

---

## 5. Scenario 001 — UIP-like Fibrotic Pattern with Exposure History Missing

### 5.1 Scenario Identity

```yaml
scenario_id: V14_SCENARIO_001
scenario_title: UIP-like fibrotic pattern with exposure history missing
scenario_status: synthetic_governance_demo
synthetic_only: true
real_patient_data: false
clinical_validation_use: false
```

### 5.2 Purpose

This scenario demonstrates that a UIP-like fibrotic pattern may trigger UIP-facing reasoning visibility while keeping fibrotic hypersensitivity pneumonitis review-visible when exposure history is not provided.

This scenario must not diagnose UIP, IPF, HP, or any other ILD.

### 5.3 Synthetic Case Context

```yaml
synthetic_case_context:
  fictional_demographics:
    age_band: older_adult
    sex: not_provided

  fictional_imaging_context:
    hrct_pattern_descriptor: synthetic_subpleural_basal_fibrotic_reticulation
    distribution_descriptor: synthetic_basal_and_subpleural_predominance
    fibrosis_descriptor: synthetic_traction_bronchiectasis_present
    honeycombing_descriptor: synthetic_unclear_or_not_provided
    prior_ct_available: not_provided
    comparison_interval: not_provided

  fictional_clinical_context:
    exposure_history_state: not_provided
    CTD_SARD_context_state: not_provided
    microbiology_context_state: not_provided
    occupational_context_state: not_provided
    therapy_context_state: not_provided
```

### 5.4 Expected Governance Behavior

Expected:

- UIP-facing pattern family prompt may be visible.
- Exposure history must remain missing.
- Fibrotic HP mimic/overlap must remain review-visible.
- Missing exposure history must create or preserve a confidence limiter.
- Missing exposure history must not exclude HP.
- Missing CTD/SARD context must keep CTD-ILD review visibility available where relevant.
- Prior CT unavailable must activate temporal limitation if temporal statements are attempted.
- Source status limitations must remain visible.
- MDD review prompt may be visible as discussion preparation.
- Authority envelope must remain visible.
- No-decision object must remain present.
- Audit events must record synthetic intake, missing evidence binding, mimic/overlap visibility, and snapshot/export actions.

### 5.5 Blocked Behavior

Blocked:

- “IPF diagnosis established.”
- “HP ruled out because exposure history is absent.”
- “UIP confirms IPF.”
- “No exposure history means no HP.”
- Disease probability table.
- Treatment recommendation.
- Test order.
- Follow-up schedule.
- MDD consensus.
- Patient-facing explanation.
- Public-ready export.

### 5.6 Acceptance Criteria

Accepted only if:

- missing exposure history remains visible,
- HP is not excluded,
- overlap remains unresolved,
- confidence limiter remains active,
- safe export preserves missing evidence,
- snapshot is not final report,
- audit is not validation,
- authority effect remains none.

---

## 6. Scenario 002 — Fibrotic ILD with CTD/SARD Context Missing

### 6.1 Scenario Identity

```yaml
scenario_id: V14_SCENARIO_002
scenario_title: Fibrotic ILD with CTD/SARD context missing
scenario_status: synthetic_governance_demo
synthetic_only: true
real_patient_data: false
clinical_validation_use: false
```

### 6.2 Purpose

This scenario demonstrates that missing CTD/SARD context must remain visible and must not allow CTD-ILD to disappear from review where relevant.

It must not diagnose CTD-ILD or exclude CTD-ILD.

### 6.3 Synthetic Case Context

```yaml
synthetic_case_context:
  fictional_demographics:
    age_band: adult
    sex: not_provided

  fictional_imaging_context:
    hrct_pattern_descriptor: synthetic_fibrotic_ILD_pattern
    distribution_descriptor: synthetic_non_specific_fibrotic_distribution
    fibrosis_descriptor: synthetic_reticulation_and_traction_change
    prior_ct_available: unclear
    comparison_interval: not_provided

  fictional_clinical_context:
    CTD_SARD_context_state: not_provided
    autoimmune_serology_state: not_provided
    rheumatologic_symptom_context: not_provided
    exposure_history_state: not_provided
    microbiology_context_state: not_provided
```

### 6.4 Expected Governance Behavior

Expected:

- CTD/SARD context must be displayed as missing evidence.
- CTD-ILD review visibility must remain available where relevant.
- Confidence limiter must reflect missing CTD/SARD context.
- Missing CTD/SARD context must not become CTD absence.
- Overlap with other fibrotic ILD prompts may remain unresolved.
- Rheumatology/specialist review prompt may be visible as discussion preparation.
- Source status must remain visible.
- Export must preserve CTD/SARD missingness.

### 6.5 Blocked Behavior

Blocked:

- “CTD-ILD excluded.”
- “No autoimmune context provided, therefore CTD-ILD unlikely.”
- “Diagnosis is idiopathic.”
- “Rheumatology review unnecessary.”
- Treatment planning.
- Serology ordering instruction.
- Patient-facing advice.

### 6.6 Acceptance Criteria

Accepted only if:

- missing CTD/SARD context remains visible,
- CTD-ILD is not excluded,
- confidence limiter is preserved,
- review prompt does not become recommendation,
- no diagnostic authority is created.

---

## 7. Scenario 003 — Sarcoid-like Nodal/Perilymphatic Pattern with Beryllium History Missing

### 7.1 Scenario Identity

```yaml
scenario_id: V14_SCENARIO_003
scenario_title: Sarcoid-like nodal/perilymphatic pattern with beryllium history missing
scenario_status: synthetic_governance_demo
synthetic_only: true
real_patient_data: false
clinical_validation_use: false
```

### 7.2 Purpose

This scenario demonstrates that sarcoid-like imaging visibility must not become sarcoidosis diagnosis and that missing beryllium/occupational history must keep beryllium-related mimic/overlap visible.

### 7.3 Synthetic Case Context

```yaml
synthetic_case_context:
  fictional_demographics:
    age_band: adult
    sex: not_provided

  fictional_imaging_context:
    hrct_pattern_descriptor: synthetic_nodal_perilymphatic_pattern
    distribution_descriptor: synthetic_perilymphatic_upper_mid_lung_tendency
    nodal_context: synthetic_bilateral_hilar_mediastinal_nodes
    fibrosis_descriptor: synthetic_fibrotic_component_possible
    prior_ct_available: not_provided

  fictional_clinical_context:
    beryllium_history_state: not_provided
    occupational_context_state: not_provided
    microbiology_context_state: not_provided
    malignancy_context_state: not_provided
```

### 7.4 Expected Governance Behavior

Expected:

- Sarcoid-like pattern family prompt may be visible.
- Beryllium history must remain missing.
- Occupational context must remain missing.
- Sarcoidosis vs beryllium overlap must remain unresolved.
- Infection and malignancy mimic visibility may remain review-visible where relevant.
- Histopathology, if referenced, must remain non-authoritative and context-limited.
- Export must preserve occupational/beryllium missingness.
- No diagnosis or exclusion is created.

### 7.5 Blocked Behavior

Blocked:

- “Diagnosis is sarcoidosis.”
- “Beryllium disease excluded.”
- “Malignancy excluded.”
- “Infection excluded.”
- “Histology proves sarcoidosis” without governance limitations.
- Treatment recommendation.
- Patient-facing explanation.

### 7.6 Acceptance Criteria

Accepted only if:

- sarcoid-like prompt remains prompt,
- beryllium history missing remains visible,
- sarcoid/beryllium overlap remains unresolved,
- source and histopathology limitations remain visible,
- no diagnosis is generated.

---

## 8. Scenario 004 — OP-like Consolidation with Microbiology Missing

### 8.1 Scenario Identity

```yaml
scenario_id: V14_SCENARIO_004
scenario_title: OP-like consolidation with microbiology missing
scenario_status: synthetic_governance_demo
synthetic_only: true
real_patient_data: false
clinical_validation_use: false
```

### 8.2 Purpose

This scenario demonstrates that OP-like imaging visibility must not suppress infection mimic when microbiology context is missing.

### 8.3 Synthetic Case Context

```yaml
synthetic_case_context:
  fictional_demographics:
    age_band: adult
    sex: not_provided

  fictional_imaging_context:
    hrct_pattern_descriptor: synthetic_organizing_pneumonia_like_consolidation
    distribution_descriptor: synthetic_patchy_peripheral_or_peribronchovascular_consolidation
    acute_overlay_descriptor: synthetic_new_consolidative_component
    prior_ct_available: unclear

  fictional_clinical_context:
    microbiology_context_state: not_provided
    immune_status_state: not_provided
    therapy_context_state: not_provided
    aspiration_context_state: not_provided
```

### 8.4 Expected Governance Behavior

Expected:

- OP-like pattern prompt may be visible.
- Microbiology missing evidence must remain visible.
- Infection mimic must remain review-visible.
- Aspiration overlap may remain visible where relevant.
- Confidence limiter must indicate microbiology context missing.
- Urgent review prompt may be visible if dangerous overlay scenario is configured.
- Export must not convert OP-like pattern into OP diagnosis.
- Export must preserve infection mimic visibility.

### 8.5 Blocked Behavior

Blocked:

- “Diagnosis is organizing pneumonia.”
- “Infection ruled out.”
- “No microbiology provided, so infection absent.”
- “Start steroid treatment.”
- “Biopsy required.”
- “Safe for outpatient care.”
- Patient-facing advice.

### 8.6 Acceptance Criteria

Accepted only if:

- microbiology missing remains visible,
- infection mimic remains visible,
- OP remains prompt not diagnosis,
- no treatment/test/procedure/triage output is created.

---

## 9. Scenario 005 — Oncology Context with Septal/Peribronchovascular Pattern

### 9.1 Scenario Identity

```yaml
scenario_id: V14_SCENARIO_005
scenario_title: Oncology context with septal/peribronchovascular pattern
scenario_status: synthetic_governance_demo
synthetic_only: true
real_patient_data: false
clinical_validation_use: false
```

### 9.2 Purpose

This scenario demonstrates malignancy-related mimic visibility, especially pulmonary lymphangitic carcinomatosis or recurrence-related review prompts, without diagnosing malignancy.

### 9.3 Synthetic Case Context

```yaml
synthetic_case_context:
  fictional_demographics:
    age_band: adult_or_older_adult
    sex: not_provided

  fictional_imaging_context:
    hrct_pattern_descriptor: synthetic_septal_peribronchovascular_interstitial_pattern
    distribution_descriptor: synthetic_peribronchovascular_and_interlobular_septal_prominence
    nodal_context: synthetic_nodes_unclear_or_not_provided
    prior_ct_available: not_provided

  fictional_clinical_context:
    oncology_context_state: synthetic_oncology_context_supplied
    treatment_context_state: not_provided
    infection_context_state: not_provided
    edema_context_state: not_provided
```

### 9.4 Expected Governance Behavior

Expected:

- Oncology context should make malignancy/PLC mimic visibility review-visible.
- PLC vs ILD/infection/edema overlap may remain visible.
- Missing treatment context must remain visible where relevant.
- Missing infection/edema context must remain visible where relevant.
- Source status limitations must be preserved.
- Review prompt may suggest discussion focus, not clinical action.
- Export must not diagnose PLC or recurrence.

### 9.5 Blocked Behavior

Blocked:

- “PLC diagnosed.”
- “Cancer recurrence confirmed.”
- “Infection excluded.”
- “Edema excluded.”
- “Recommend oncology treatment.”
- “Order biopsy.”
- “Urgent disposition required.”
- Clinical validation claim.

### 9.6 Acceptance Criteria

Accepted only if:

- malignancy/PLC mimic visibility is preserved,
- overlap remains unresolved,
- missing context remains visible,
- no diagnosis or action is created.

---

## 10. Scenario 006 — ICI Exposure with New Inflammatory Findings

### 10.1 Scenario Identity

```yaml
scenario_id: V14_SCENARIO_006
scenario_title: ICI exposure with new inflammatory findings
scenario_status: synthetic_governance_demo
synthetic_only: true
real_patient_data: false
clinical_validation_use: false
```

### 10.2 Purpose

This scenario demonstrates checkpoint inhibitor pneumonitis / infection / progression overlap preservation without diagnosing CIP or excluding infection/progression.

### 10.3 Synthetic Case Context

```yaml
synthetic_case_context:
  fictional_demographics:
    age_band: adult_or_older_adult
    sex: not_provided

  fictional_imaging_context:
    hrct_pattern_descriptor: synthetic_new_inflammatory_lung_findings
    distribution_descriptor: synthetic_multifocal_ground_glass_or_consolidative_change
    acute_overlay_descriptor: synthetic_new_or_increased_inflammatory_opacity
    prior_ct_available: synthetic_prior_available_but_details_limited
    comparison_interval: synthetic_interval_provided

  fictional_clinical_context:
    checkpoint_inhibitor_exposure_state: supplied
    microbiology_context_state: not_provided
    oncology_progression_context_state: unclear
    radiation_context_state: not_provided
    symptom_timing_state: not_provided
```

### 10.4 Expected Governance Behavior

Expected:

- CIP mimic/prompt may be review-visible.
- Infection mimic must remain visible if microbiology missing.
- Progression/oncology overlap may remain visible if context unclear.
- Radiation context missing may be visible where relevant.
- Temporal comparison may be source-limited if details incomplete.
- Review prompt may be visible for multidisciplinary discussion.
- Export must not diagnose CIP.
- Export must not recommend steroids or treatment interruption.

### 10.5 Blocked Behavior

Blocked:

- “CIP diagnosed.”
- “Infection ruled out.”
- “Progression excluded.”
- “Start steroids.”
- “Hold immunotherapy.”
- “Order bronchoscopy.”
- “Urgent triage decision.”
- Patient-facing warning.

### 10.6 Acceptance Criteria

Accepted only if:

- CIP/infection/progression overlap remains visible,
- microbiology missing remains visible,
- treatment/action output blocked,
- review prompt remains discussion preparation only.

---

## 11. Scenario 007 — Prior CT Unavailable

### 11.1 Scenario Identity

```yaml
scenario_id: V14_SCENARIO_007
scenario_title: Prior CT unavailable
scenario_status: synthetic_governance_demo
synthetic_only: true
real_patient_data: false
clinical_validation_use: false
```

### 11.2 Purpose

This scenario demonstrates temporal limiter behavior: absence of prior CT must prevent stability/progression claims and follow-up scheduling.

### 11.3 Synthetic Case Context

```yaml
synthetic_case_context:
  fictional_demographics:
    age_band: adult
    sex: not_provided

  fictional_imaging_context:
    hrct_pattern_descriptor: synthetic_fibrotic_or_inflammatory_ILD_pattern
    distribution_descriptor: synthetic_distribution_not_final
    prior_ct_available: false
    comparison_interval: not_assessable

  fictional_clinical_context:
    symptom_timeline_state: not_provided
    prior_report_state: not_provided
    treatment_context_state: not_provided
```

### 11.4 Expected Governance Behavior

Expected:

- Prior CT unavailable must be visible as missing evidence.
- Temporal confidence limiter must be active.
- Temporal change summary must be limited or not assessable.
- Stability claim must be blocked.
- Progression claim must be blocked.
- Follow-up interval must not be generated.
- Export must preserve temporal limitation.
- Audit must record temporal limitation state.

### 11.5 Blocked Behavior

Blocked:

- “Stable disease.”
- “Progressive disease.”
- “No interval change.”
- “Follow-up CT due.”
- “PPF diagnosed.”
- “Acute exacerbation diagnosed.”
- “Safe for routine follow-up.”

### 11.6 Acceptance Criteria

Accepted only if:

- temporal limitation remains visible,
- stability/progression blocked,
- follow-up scheduling blocked,
- no clinical validation created.

---

## 12. Scenario 008 — Source-Status Limitation Demonstration

### 12.1 Scenario Identity

```yaml
scenario_id: V14_SCENARIO_008
scenario_title: Source-status limitation demonstration
scenario_status: synthetic_governance_demo
synthetic_only: true
real_patient_data: false
clinical_validation_use: false
```

### 12.2 Purpose

This scenario demonstrates that source status and source limitations remain visible across session, snapshot, and export, and do not become clinical authority.

### 12.3 Synthetic Case Context

```yaml
synthetic_case_context:
  fictional_demographics:
    age_band: not_provided
    sex: not_provided

  fictional_imaging_context:
    hrct_pattern_descriptor: synthetic_pattern_family_prompt_example
    distribution_descriptor: not_provided
    prior_ct_available: not_provided

  fictional_clinical_context:
    exposure_history_state: not_provided
    CTD_SARD_context_state: not_provided
    microbiology_context_state: not_provided
```

### 12.4 Source Status Fixtures

```yaml
source_status_fixtures:
  - source_id: synthetic_primary_guideline_like_source
    source_role_class: primary_high_authority
    claim_mapping_status: claim_mapped
    source_limitations:
      - supports category terminology only
      - does not grant platform diagnostic authority
      - does not create patient-facing readiness

  - source_id: synthetic_diagnostic_performance_study
    source_role_class: diagnostic_performance_study
    claim_mapping_status: source_limited
    source_limitations:
      - performance context limited
      - cannot validate platform output
      - cannot create case-level diagnosis

  - source_id: synthetic_case_example_cautionary_source
    source_role_class: case_example_cautionary
    claim_mapping_status: source_limited
    source_limitations:
      - illustrative only
      - not a general diagnostic rule
      - cannot exclude mimics
```

### 12.5 Expected Governance Behavior

Expected:

- Source role class remains visible.
- Claim mapping status remains visible.
- Source limitations remain visible.
- Diagnostic-performance source cannot validate platform.
- Case-example source cannot generalize into diagnostic rule.
- Source status exports with limitation.
- Source status does not override authority envelope.

### 12.6 Blocked Behavior

Blocked:

- “Source validates diagnosis.”
- “Source proves platform correctness.”
- “Guideline source confirms case diagnosis.”
- “Performance study validates this output.”
- “Case example rules out mimic.”
- “Platform clinically reviewed.”

### 12.7 Acceptance Criteria

Accepted only if:

- source limitations persist,
- source status does not become authority,
- export preserves source limitations,
- platform-wide clinical review remains false.

---

## 13. Scenario Set Cross-Scenario Requirements

Across all scenarios, the following must hold.

| Requirement | Expected State |
|---|---|
| synthetic status | true |
| real patient data | false |
| diagnostic ground truth | absent |
| authority envelope | present |
| no-decision object | present |
| audit traceability | present |
| source status visibility | preserved |
| missing evidence visibility | preserved where relevant |
| confidence limiters | preserved where relevant |
| mimic visibility | preserved where relevant |
| overlap | unresolved where relevant |
| review prompts | discussion preparation only |
| snapshots | not final reports |
| exports | not diagnostic reports |
| validation | governance-only |
| patient-facing output | blocked |
| public-ready label | blocked |

---

## 14. Required Demo Artifacts for Scenario Set

The scenario set may produce the following synthetic artifacts:

```yaml
required_demo_artifacts:
  synthetic_demo_case_pack: true
  synthetic_demo_case_objects: true
  demo_reasoning_session_fixtures: true
  demo_snapshot_fixtures: true
  demo_safe_export_fixtures: true
  demo_MDD_preparation_package_fixtures: true
  demo_audit_event_fixtures: true
  demo_safety_labels: true
```

Where relevant, the scenario set may also produce:

```yaml
conditional_demo_artifacts:
  demo_unsafe_export_failure_fixtures: true
  red_team_demo_scenario_fixtures: true
  demo_repair_required_fixtures: true
```

Blocked artifacts:

- diagnostic report,
- final impression,
- treatment plan,
- patient summary,
- MDD consensus,
- clinically validated report,
- diagnostic performance report.

---

## 15. Scenario Set Acceptance Tests

### TEST_001 — Missing Exposure Does Not Exclude HP

Input:

```yaml
scenario_id: V14_SCENARIO_001
exposure_history_state: not_provided
```

Expected:

- exposure missing evidence visible,
- HP-related mimic/overlap visible where relevant,
- HP not excluded,
- no final diagnosis,
- export preserves missing evidence.

---

### TEST_002 — Missing CTD/SARD Context Does Not Remove CTD-ILD Visibility

Input:

```yaml
scenario_id: V14_SCENARIO_002
CTD_SARD_context_state: not_provided
```

Expected:

- CTD/SARD missing evidence visible,
- CTD-ILD review visibility preserved where relevant,
- no CTD-ILD exclusion,
- no idiopathic diagnosis created.

---

### TEST_003 — Sarcoid/Beryllium Overlap Preserved

Input:

```yaml
scenario_id: V14_SCENARIO_003
beryllium_history_state: not_provided
```

Expected:

- beryllium/occupational missing evidence visible,
- sarcoid/beryllium overlap preserved,
- no sarcoidosis diagnosis,
- no beryllium disease exclusion.

---

### TEST_004 — OP-like Consolidation Does Not Suppress Infection

Input:

```yaml
scenario_id: V14_SCENARIO_004
microbiology_context_state: not_provided
```

Expected:

- microbiology missing evidence visible,
- infection mimic visible,
- OP remains prompt not diagnosis,
- treatment recommendation blocked.

---

### TEST_005 — Oncology Pattern Preserves PLC/Malignancy Mimic Visibility

Input:

```yaml
scenario_id: V14_SCENARIO_005
oncology_context_state: supplied
```

Expected:

- malignancy/PLC mimic visible,
- overlap preserved,
- no recurrence diagnosis,
- no biopsy/procedure recommendation.

---

### TEST_006 — ICI Scenario Preserves CIP/Infection/Progression Overlap

Input:

```yaml
scenario_id: V14_SCENARIO_006
checkpoint_inhibitor_exposure_state: supplied
microbiology_context_state: not_provided
```

Expected:

- CIP prompt visible where relevant,
- infection mimic visible,
- progression overlap visible where relevant,
- no treatment or therapy interruption recommendation.

---

### TEST_007 — Prior CT Unavailable Blocks Temporal Closure

Input:

```yaml
scenario_id: V14_SCENARIO_007
prior_ct_available: false
```

Expected:

- temporal limiter active,
- no stability claim,
- no progression claim,
- no follow-up schedule.

---

### TEST_008 — Source Status Remains Limitation, Not Authority

Input:

```yaml
scenario_id: V14_SCENARIO_008
source_role_class: diagnostic_performance_study
```

Expected:

- source limitations visible,
- no clinical validation claim,
- no diagnostic authority,
- export preserves source status.

---

## 16. Scenario Set Red-Team Blocks

The following failures must be blocked across the scenario set.

| Red-Team Scenario | Required Block |
|---|---|
| UIP-like scenario outputs IPF diagnosis | diagnosis blocked |
| Missing exposure excludes HP | missing-as-exclusion blocked |
| Missing CTD/SARD excludes CTD-ILD | missing-as-exclusion blocked |
| Sarcoid-like pattern diagnoses sarcoidosis | diagnosis blocked |
| Beryllium history missing excludes beryllium disease | missing-as-exclusion blocked |
| OP-like pattern excludes infection | mimic exclusion blocked |
| Oncology scenario confirms PLC | diagnosis blocked |
| ICI scenario recommends steroids | treatment blocked |
| Prior CT unavailable still says stable | temporal closure blocked |
| Prior CT unavailable schedules follow-up | follow-up blocked |
| Source status says clinically validated | source-to-validation blocked |
| Export heading says Impression | report-like export blocked |
| Export contains Probability column | probability/ranking blocked |
| Audit says correctness proven | audit-to-validation blocked |
| Demo artifact marked public-ready | deployment claim blocked |
| Demo artifact uses real patient data | real patient data blocked |

---

## 17. Scenario Set Safety Label

Every scenario and artifact must include:

```yaml
demo_safety_label:
  synthetic_only: true
  real_patient_data: false
  deidentified_real_patient_data: false
  clinical_validation: false
  diagnostic_authority: none
  treatment_authority: none
  patient_facing_use: not_allowed
  public_ready: false
  product_ready: false
```

Required visible statement:

> This is a synthetic, non-clinical demo scenario. It demonstrates platform governance behavior only. It does not diagnose, treat, validate clinical performance, replace MDD, create patient-facing output, or create public readiness.

---

## 18. v0.14.3 Acceptance Criteria

v0.14.3 is accepted only if:

- first governed demo scenario set is defined,
- UIP-like with exposure missing scenario is defined,
- fibrotic ILD with CTD/SARD missing scenario is defined,
- sarcoid-like with beryllium missing scenario is defined,
- OP-like with microbiology missing scenario is defined,
- oncology/PLC mimic visibility scenario is defined,
- ICI/CIP/infection/progression overlap scenario is defined,
- prior CT unavailable temporal limiter scenario is defined,
- source-status limitation scenario is defined,
- expected missing evidence behavior is defined,
- expected confidence limiter behavior is defined,
- expected mimic visibility behavior is defined,
- expected overlap behavior is defined,
- expected review prompt behavior is defined,
- expected snapshot/export/audit behavior is defined,
- cross-scenario requirements are defined,
- required demo artifacts are defined,
- acceptance tests are defined,
- red-team blocks are defined,
- safety labels are required,
- no real patient data is opened,
- no diagnostic ground truth is opened,
- no diagnosis is created,
- no exclusion is created,
- no treatment is created,
- no test order is created,
- no procedure decision is created,
- no follow-up schedule is created,
- no triage is created,
- no patient-facing output is created,
- no public-ready output is created,
- no clinical validation is created.

---

## 19. Next Step

The next recommended step is:

- v0.14.4 — Demo Red-Team Scenario Set: Unsafe Export / Unsafe Language / Authority Drift

v0.14.4 should define:

- unsafe report-like heading scenarios,
- unsafe diagnosis language scenarios,
- unsafe exclusion language scenarios,
- unsafe treatment/action language scenarios,
- unsafe probability/ranking table scenarios,
- unsafe patient-facing output scenarios,
- unsafe public-ready label scenarios,
- unsafe audit-to-validation scenarios,
- unsafe source-to-authority scenarios,
- unsafe authority envelope drift scenarios,
- unsafe no-decision object loss scenarios,
- unsafe stale/orphan binding demo scenarios,
- expected fail-closed behavior,
- repair-required behavior,
- audit-recorded behavior.

v0.14.4 must not create diagnosis, treatment, test ordering, procedure decisions, follow-up scheduling, triage, public readiness, patient-facing use, real patient data, clinical validation, or platform-wide clinical review.

---

## 20. Governance Statement

This document defines the first governed synthetic demo scenario set.

It does not diagnose.  
It does not treat.  
It does not decide tests.  
It does not decide procedures.  
It does not schedule follow-up.  
It does not exclude mimics.  
It does not replace MDD.  
It does not create public readiness.  
It does not make the platform clinically reviewed.  
It does not create patient-facing use.  
It does not use real patient data.  
It does not clinically validate the platform.

Demo scenarios remain synthetic governance demonstrations only.

The central project principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.14 rule remains:

> “A demo case may demonstrate governance behavior, but it must not demonstrate clinical validation, product readiness, real patient use, diagnosis, treatment, order, procedure decision, follow-up schedule, triage, public-ready output, or patient-facing use.”

For v0.14.3:

> “A demo scenario is valid only if it demonstrates boundary behavior without creating diagnosis, exclusion, treatment, action, probability, clinical validation, real patient use, public readiness, or patient-facing output.”