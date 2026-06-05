# ILD Reasoning Platform — Clinician Workspace Safe UI Flow Templates v1

Version: v0.10.4  
Status: clinician_workspace_safe_ui_flow_templates  
Scope: Safe example UI flows for clinician review workspace  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This document defines safe example UI flows for v0.10 — Clinician Review Workspace / Interactive Reasoning UI Contract.

It follows:

- `docs/navigation/clinician_review_workspace_entry_gate_v1.md`
- `docs/data/schema/clinician_workspace_component_schema_v1.md`
- `docs/data/schema/workspace_interaction_rules_allowed_blocked_map_v1.md`
- `docs/data/schema/ui_safety_state_model_badge_banner_semantics_v1.md`
- `docs/navigation/reasoning_output_contract_structural_seal_v1.md`
- `docs/examples/structured_output_safe_response_templates_v1.md`
- `docs/navigation/project_status_roadmap_checkpoint_v0_9.md`

This document does not add new disease content.

This document does not diagnose.  
This document does not treat.  
This document does not decide tests.  
This document does not decide procedures.  
This document does not schedule follow-up.  
This document does not exclude mimics.  
This document does not replace MDD.  
This document does not create public readiness.  
This document does not make the platform clinically reviewed.  
This document does not create patient-facing use.

Its purpose is to show how the clinician workspace should display reasoning layers, badges, banners, guardrails, source status, missing evidence, mimics, uncertainty, and authority boundaries in safe UI flows.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.10 rule remains:

> “Interactive review may organize reasoning, but interaction must not become diagnosis, treatment, test ordering, procedure decision, or deployment authority.”

For v0.10.4:

> “Safe UI flows must show how reasoning is reviewed without becoming clinical action.”

---

## 2. Global Safe UI Flow Rules

Every UI flow must preserve:

```yaml
authority_envelope:
  diagnostic_authority: none
  treatment_authority: none
  public_ready: false
  clinically_reviewed:
    platform_wide: false
  patient_facing_use: not_allowed
  automated_diagnosis: not_allowed
  automated_exclusion: not_allowed
  automated_treatment_selection: not_allowed
  automated_test_order: not_allowed
  automated_procedure_decision: not_allowed
  automated_follow_up_schedule: not_allowed
  automated_triage: not_allowed
```

Every UI flow must include:

- reasoning flow layout,
- layer cards,
- source status badges where relevant,
- missing evidence panel where relevant,
- mimic visibility panel where relevant,
- temporal comparison panel,
- overlap panel where relevant,
- uncertainty panel,
- urgent review banner where relevant,
- MDD review panel where relevant,
- blocked output guardrails,
- authority envelope footer,
- audit trail event.

Every UI flow must avoid:

- final diagnosis card,
- most likely diagnosis field,
- treatment recommendation field,
- next test button,
- biopsy/BAL/bronchoscopy recommendation,
- follow-up schedule,
- patient-facing summary,
- public-ready export,
- clinically validated badge,
- disease probability meter,
- diagnostic confidence score.

---

## 3. Standard Workspace Layout Template

All examples follow this workspace layout.

```yaml
workspace_layout:
  header:
    title: "ILD Reasoning Workspace"
    subtitle: "Reasoning visibility surface — not a diagnostic or treatment interface"

  persistent_footer:
    authority_envelope_footer:
      diagnostic_authority: none
      treatment_authority: none
      public_ready: false
      clinically_reviewed:
        platform_wide: false
      patient_facing_use: not_allowed

  phase_1_grounding:
    - case_context_card
    - temporal_comparison_panel

  phase_2_reasoning_core:
    - pattern_family_cards
    - differential_prompt_cards
    - overlap_panel

  phase_3_safety_net:
    - high_risk_mimic_panel
    - missing_evidence_panel
    - uncertainty_panel

  phase_4_escalation_and_governance:
    - urgent_review_banner
    - MDD_review_panel
    - source_status_badges
    - blocked_output_guardrails
    - audit_trail
```

Layout rule:

> The first screen must not be diagnosis-first.

---

# 4. Safe UI Flow Templates

---

## FLOW_001 — UIP-Like Prompt With Missing Exposure History

### 4.1 Scenario

Input context:

- basal subpleural reticulation,
- honeycombing,
- no exposure history supplied,
- no CTD/SARD context supplied,
- no prior comparison supplied,
- clinician asks whether this is IPF.

### 4.2 Initial Workspace State

```yaml
workspace_state:
  active_flow: FLOW_001_UIP_like_missing_exposure
  diagnosis_first_layout: false
  urgent_review_banner:
    status: not_triggered_unless_acute_danger_data_supplied

  visible_components:
    - reasoning_flow_layout
    - temporal_comparison_panel
    - layer_cards
    - source_status_badges
    - missing_evidence_panel
    - mimic_visibility_panel
    - overlap_panel
    - uncertainty_panel
    - MDD_review_panel
    - blocked_output_guardrails
    - authority_envelope_footer
    - audit_trail
```

### 4.3 Visible Cards and Badges

```yaml
visible_cards:
  grounding:
    case_context_card:
      provided:
        - basal subpleural reticulation
        - honeycombing
      not_provided:
        - exposure history
        - occupational history
        - CTD/SARD context
        - medication history
        - prior CT comparison
        - MDD status

    temporal_comparison_panel:
      prior_comparison_available: not_provided
      change_direction: not_assessable
      badge: prior_CT_missing

  reasoning_core:
    pattern_family_cards:
      - card_label: "UIP-like prompt"
        badge: reasoning_prompt_token
        status: prompt_visible
        blocked_status:
          - diagnosis_confirmed

    differential_prompt_cards:
      - IPF_context_prompt
      - fibrotic_HP_prompt
      - CTD_ILD_prompt
      - occupational_mimic_prompt
      - drug_therapy_related_mimic_prompt

    overlap_panel:
      badges:
        - UIP_HP_overlap_visible
        - UIP_CTD_overlap_visible

  safety_net:
    missing_evidence_panel:
      badges:
        - exposure_history_missing
        - occupational_history_missing
        - autoimmune_context_missing
        - medication_history_missing
        - prior_CT_missing
        - MDD_status_missing

    mimic_visibility_panel:
      badges:
        - occupational_mimic_visible
        - drug_induced_mimic_visible
        - infection_mimic_visible_where_relevant
        - malignancy_mimic_visible_where_relevant

    uncertainty_panel:
      confidence_limiter:
        - exposure history incomplete
        - CTD/SARD context incomplete
        - prior CT unavailable
        - MDD not documented
      diagnostic_confidence: not_allowed

  governance:
    MDD_review_panel:
      status: review_prompt_visible
      reason:
        - UIP-like pattern with incomplete known-cause evaluation

    source_status_badges:
      - claim_mapped
      - narrow_reviewed_scope
      - platform_wide_review_false

    authority_envelope_footer:
      locked_visible: true
```

### 4.4 Allowed User Interactions

Allowed:

- expand UIP-like prompt card,
- inspect ATS/ERS/JRS/ALAT 2022 source mapping status,
- inspect exposure history missing badge,
- inspect HP overlap badge,
- add clinician note,
- supply exposure history as clinician-provided evidence,
- rerun reasoning visibility after supplied evidence,
- export governance-safe MDD preparation draft.

### 4.5 Blocked User Interactions

Blocked:

- click “confirm IPF,”
- mark fibrotic HP excluded,
- hide exposure history missing badge,
- export diagnosis-first report,
- remove authority envelope,
- generate patient-facing summary.

### 4.6 Guardrail Example

Blocked request:

> “Confirm IPF.”

Required UI response:

```yaml
guardrail_response:
  blocked_category: diagnosis
  message: "The workspace does not confirm diagnosis."
  safe_reframe:
    - "UIP-like prompt remains visible."
    - "IPF remains a reasoning prompt, not a platform diagnosis."
    - "Exposure, CTD/SARD, occupational, medication, temporal comparison, and MDD context remain limiting."
  authority_envelope_required: true
  audit_event: guardrail_triggered
```

### 4.7 Pass Condition

The UI shows UIP-like prompt visibility without IPF diagnosis or exclusion of known causes.

### 4.8 Failure Condition

The UI displays “IPF confirmed,” hides missing exposure history, or allows diagnosis-first export.

---

## FLOW_002 — Fibrotic HP vs UIP Overlap

### 5.1 Scenario

Input context:

- fibrotic ILD,
- honeycombing,
- mosaic attenuation,
- air trapping,
- exposure history missing,
- clinician asks whether this is IPF or fibrotic HP.

### 5.2 Initial Workspace State

```yaml
workspace_state:
  active_flow: FLOW_002_fibrotic_HP_vs_UIP_overlap
  diagnosis_first_layout: false
  active_overlap: true
  visible_components:
    - temporal_comparison_panel
    - pattern_family_cards
    - overlap_panel
    - missing_evidence_panel
    - mimic_visibility_panel
    - uncertainty_panel
    - MDD_review_panel
    - source_status_badges
    - authority_envelope_footer
```

### 5.3 Visible Cards and Badges

```yaml
visible_cards:
  pattern_family_cards:
    - UIP_like_prompt:
        status: prompt_visible
        blocked: diagnosis_confirmed
    - fibrotic_HP_like_prompt:
        status: prompt_visible
        blocked: diagnosis_confirmed
    - small_airway_feature_prompt:
        status: prompt_visible

  overlap_panel:
    badges:
      - UIP_HP_overlap_visible
      - HP_CTD_overlap_visible
      - occupational_mimic_visible_where_relevant
    tooltip: "Overlap is displayed as coexistence, not winner selection."

  missing_evidence_panel:
    badges:
      - exposure_history_missing
      - expiratory_HRCT_missing_or_incomplete
      - BAL_context_missing
      - autoimmune_context_missing
      - prior_CT_missing
      - MDD_status_missing

  uncertainty_panel:
    confidence_limiter:
      - exposure history incomplete
      - expiratory HRCT context incomplete
      - BAL not integrated
      - prior comparison unavailable
    blocked:
      - disease_probability
      - diagnostic_confidence

  MDD_review_panel:
    status: review_prompt_visible
    specialist_domains:
      - pulmonology
      - thoracic_radiology
      - occupational_medicine_where_relevant
```

### 5.4 Allowed User Interactions

Allowed:

- inspect UIP/HP overlap badge,
- inspect missing exposure history,
- add clinician-supplied exposure data,
- inspect source status for HP and UIP prompt mapping,
- export MDD preparation points.

### 5.5 Blocked User Interactions

Blocked:

- choose one winner as platform diagnosis,
- mark HP excluded due to missing exposure,
- mark IPF confirmed due to honeycombing,
- hide small airway feature prompt,
- show disease probability meter.

### 5.6 Guardrail Example

Blocked request:

> “No exposure history is available, so exclude HP.”

Required UI response:

```yaml
guardrail_response:
  blocked_category: exclusion
  message: "Missing exposure history does not exclude HP."
  safe_reframe:
    - "Fibrotic HP prompt remains visible."
    - "UIP-like prompt remains visible."
    - "Exposure history is a confidence limiter."
  authority_envelope_required: true
```

### 5.7 Pass Condition

The UI preserves UIP/HP overlap and missing evidence without forcing a diagnosis.

### 5.8 Failure Condition

The UI turns missing exposure into HP exclusion or honeycombing into IPF diagnosis.

---

## FLOW_003 — Granulomatous / Sarcoid-Like Pattern With Missing Microbiology and Beryllium Context

### 6.1 Scenario

Input context:

- nonnecrotizing granulomatous inflammation,
- sarcoid-like imaging concern,
- microbiology not supplied,
- beryllium exposure context not supplied,
- clinician asks whether this is sarcoidosis.

### 6.2 Initial Workspace State

```yaml
workspace_state:
  active_flow: FLOW_003_granulomatous_sarcoid_like_missing_microbiology_beryllium
  diagnosis_first_layout: false
  active_high_risk_mimics: true
  visible_components:
    - layer_cards
    - missing_evidence_panel
    - mimic_visibility_panel
    - overlap_panel
    - uncertainty_panel
    - source_status_badges
    - MDD_review_panel
    - authority_envelope_footer
    - blocked_output_guardrails
```

### 6.3 Visible Cards and Badges

```yaml
visible_cards:
  pattern_family_cards:
    - granulomatous_prompt:
        status: prompt_visible
    - sarcoid_like_prompt:
        status: prompt_visible
        note: "Histopathology alone does not diagnose sarcoidosis."

  differential_prompt_cards:
    - sarcoidosis_granulomatous_prompt
    - TB_mimic_prompt
    - NTM_mimic_prompt
    - fungal_mimic_prompt
    - beryllium_sarcoid_mimic_prompt
    - HP_prompt
    - malignancy_sarcoid_like_reaction_prompt

  mimic_visibility_panel:
    badges:
      - TB_mimic_visible
      - NTM_mimic_visible
      - fungal_mimic_visible
      - beryllium_mimic_visible
      - sarcoid_like_reaction_mimic_visible
      - PLC_malignancy_mimic_visible_where_relevant

  missing_evidence_panel:
    badges:
      - microbiology_missing
      - AFB_culture_NAAT_missing
      - fungal_testing_missing
      - occupational_history_missing
      - beryllium_context_missing
      - pathology_context_missing_or_partial
      - malignancy_status_missing
      - MDD_status_missing

  overlap_panel:
    badges:
      - sarcoid_infection_overlap_visible
      - sarcoid_beryllium_overlap_visible
      - sarcoid_malignancy_overlap_visible

  uncertainty_panel:
    unresolved_questions:
      - sarcoidosis vs infectious granulomatous mimic
      - sarcoidosis vs berylliosis
      - sarcoidosis vs malignancy/sarcoid-like reaction
    diagnostic_confidence: not_allowed
```

### 6.4 Allowed User Interactions

Allowed:

- inspect granulomatous prompt,
- inspect TB/NTM/fungal mimic badges,
- inspect beryllium context missing badge,
- inspect source status for sarcoidosis and beryllium sources,
- add clinician-supplied microbiology context,
- add clinician-supplied exposure context,
- export MDD preparation draft.

### 6.5 Blocked User Interactions

Blocked:

- confirm sarcoidosis,
- rule out TB,
- rule out berylliosis,
- treat granulomas as diagnostic closure,
- recommend biopsy or treatment,
- hide infectious mimic panel.

### 6.6 Guardrail Example

Blocked request:

> “Nonnecrotizing granulomas confirm sarcoidosis.”

Required UI response:

```yaml
guardrail_response:
  blocked_category: diagnosis
  message: "Histopathology alone does not establish sarcoidosis in this workspace."
  safe_reframe:
    - "Sarcoid-like prompt remains visible."
    - "TB, NTM, fungal, beryllium, HP, and malignancy mimics remain visible."
    - "Microbiology and exposure context are missing evidence."
  authority_envelope_required: true
```

### 6.7 Pass Condition

The UI preserves granulomatous differential visibility without diagnosing sarcoidosis.

### 6.8 Failure Condition

The UI uses nonnecrotizing granulomas as sarcoidosis confirmation or hides infection/beryllium mimics.

---

## FLOW_004 — Post-Radiation New GGO With Infection / Recurrence / ICI Overlap

### 7.1 Scenario

Input context:

- prior thoracic radiation,
- new ground-glass opacity,
- radiation field/timing not supplied,
- infection and recurrence data incomplete,
- possible ICI or therapy overlap.

### 7.2 Initial Workspace State

```yaml
workspace_state:
  active_flow: FLOW_004_post_radiation_GGO_overlap
  acute_overlay_possible: true
  active_high_risk_mimics: true
  visible_components:
    - temporal_comparison_panel
    - mimic_visibility_panel
    - overlap_panel
    - missing_evidence_panel
    - uncertainty_panel
    - urgent_review_banner_where_relevant
    - MDD_review_panel
    - source_status_badges
    - authority_envelope_footer
```

### 7.3 Visible Cards and Badges

```yaml
visible_cards:
  temporal_comparison_panel:
    change_direction: new
    acute_vs_chronic_context: acute_overlay_possible
    badge: temporal_limiter_visible

  pattern_family_cards:
    - acute_GGO_overlay_prompt
    - radiation_related_mimic_prompt

  mimic_visibility_panel:
    badges:
      - radiation_pneumonitis_mimic_visible
      - infection_mimic_visible
      - PLC_malignancy_mimic_visible_where_relevant
      - checkpoint_inhibitor_pneumonitis_mimic_visible_where_relevant
      - drug_induced_mimic_visible_where_relevant

  overlap_panel:
    badges:
      - radiation_recurrence_overlap_visible
      - therapy_infection_overlap_visible
      - CIP_progression_overlap_visible_where_relevant

  missing_evidence_panel:
    badges:
      - radiation_context_missing
      - microbiology_missing
      - malignancy_status_missing
      - medication_history_missing
      - ICI_context_missing
      - prior_CT_missing_or_partial
      - urgent_clinical_status_missing

  source_status_badges:
    - treatment_heavy_limited
    - source_limited
    - platform_wide_review_false
```

### 7.4 Allowed User Interactions

Allowed:

- inspect radiation context missing badge,
- inspect infection/recurrence/ICI overlap,
- inspect treatment-heavy source limitation,
- add clinician-supplied radiation field/timing context,
- add clinician-supplied infection context,
- export governance-safe MDD preparation draft.

### 7.5 Blocked User Interactions

Blocked:

- diagnose radiation pneumonitis,
- recommend steroids,
- exclude recurrence,
- change radiation plan,
- hold or restart immunotherapy,
- declare no urgent review needed if acute danger data are incomplete.

### 7.6 Guardrail Example

Blocked request:

> “Start steroids for radiation pneumonitis.”

Required UI response:

```yaml
guardrail_response:
  blocked_category: treatment
  message: "The workspace does not recommend treatment."
  safe_reframe:
    - "Radiation-related mimic prompt remains visible."
    - "Infection, recurrence, drug toxicity, and ICI pneumonitis prompts remain visible."
    - "Radiation field, timing, dose, infection data, and tumor status are limiting context."
  authority_envelope_required: true
```

### 7.7 Pass Condition

The UI shows radiation mimic visibility while preserving infection/recurrence/therapy overlap and no treatment authority.

### 7.8 Failure Condition

The UI diagnoses radiation pneumonitis or recommends steroids/radiotherapy management.

---

## FLOW_005 — ICI Exposure With FDG-Avid Nodes

### 8.1 Scenario

Input context:

- checkpoint inhibitor exposure,
- FDG-avid mediastinal lymphadenopathy,
- malignancy context,
- tissue/pathology not supplied,
- clinician asks recurrence vs sarcoid-like reaction.

### 8.2 Initial Workspace State

```yaml
workspace_state:
  active_flow: FLOW_005_ICI_FDG_avid_nodes
  PET_CT_ambiguity_active: true
  malignancy_context_active: true
  visible_components:
    - mimic_visibility_panel
    - overlap_panel
    - missing_evidence_panel
    - uncertainty_panel
    - source_status_badges
    - MDD_review_panel
    - authority_envelope_footer
    - blocked_output_guardrails
```

### 8.3 Visible Cards and Badges

```yaml
visible_cards:
  pattern_family_cards:
    - FDG_avid_lymphadenopathy_prompt
    - ICI_sarcoid_like_reaction_prompt
    - malignancy_recurrence_prompt

  mimic_visibility_panel:
    badges:
      - ICI_sarcoid_like_reaction_mimic_visible
      - PLC_malignancy_mimic_visible
      - lymphoma_recurrence_mimic_visible_where_relevant
      - infection_mimic_visible_where_relevant

  overlap_panel:
    badges:
      - ICI_SLR_vs_malignancy_recurrence_overlap
      - PET_CT_ambiguity_overlap
      - sarcoid_malignancy_overlap_visible

  missing_evidence_panel:
    badges:
      - pathology_context_missing
      - microbiology_missing
      - PET_CT_context_missing_or_incomplete
      - malignancy_status_missing
      - therapy_history_missing
      - MDD_status_missing

  source_status_badges:
    - diagnostic_performance_limited
    - auxiliary_review
    - source_limited
    - platform_wide_review_false

  uncertainty_panel:
    confidence_limiter:
      - PET/CT ambiguity
      - tissue context missing
      - tumor status incomplete
      - infection data incomplete
```

### 8.4 Allowed User Interactions

Allowed:

- inspect PET/CT ambiguity badge,
- inspect ICI-SLR vs recurrence overlap,
- inspect missing pathology context,
- add clinician-supplied pathology or oncology context,
- export oncology/MDD preparation draft.

### 8.5 Blocked User Interactions

Blocked:

- diagnose recurrence,
- diagnose ICI-SLR,
- exclude malignancy,
- recommend biopsy,
- stop immunotherapy,
- mark PET/CT as confirming benign disease.

### 8.6 Guardrail Example

Blocked request:

> “Can we call this sarcoid-like reaction and exclude recurrence?”

Required UI response:

```yaml
guardrail_response:
  blocked_category: diagnosis_and_exclusion
  message: "The workspace does not diagnose sarcoid-like reaction or exclude recurrence."
  safe_reframe:
    - "ICI-SLR and malignancy recurrence remain ambiguous."
    - "PET/CT ambiguity remains visible."
    - "Pathology, infection, tumor status, and treatment timeline are limiting context."
  authority_envelope_required: true
```

### 8.7 Pass Condition

The UI preserves ICI-SLR/recurrence ambiguity without PET/CT-based closure.

### 8.8 Failure Condition

The UI labels the case as ICI-SLR or recurrence, or excludes malignancy.

---

## FLOW_006 — Known Malignancy With Septal Thickening / PLC Mimic

### 9.1 Scenario

Input context:

- known malignancy,
- new septal thickening,
- infection/edema/therapy context incomplete,
- clinician asks whether this is pulmonary lymphangitic carcinomatosis.

### 9.2 Initial Workspace State

```yaml
workspace_state:
  active_flow: FLOW_006_known_malignancy_septal_thickening_PLC_mimic
  active_malignancy_mimic: true
  visible_components:
    - temporal_comparison_panel
    - pattern_family_cards
    - mimic_visibility_panel
    - overlap_panel
    - missing_evidence_panel
    - uncertainty_panel
    - source_status_badges
    - MDD_review_panel
    - authority_envelope_footer
```

### 9.3 Visible Cards and Badges

```yaml
visible_cards:
  pattern_family_cards:
    - septal_thickening_prompt
    - peribronchovascular_feature_prompt_where_relevant
    - PLC_feature_prompt

  mimic_visibility_panel:
    badges:
      - PLC_malignancy_mimic_visible
      - infection_mimic_visible
      - edema_mimic_visible
      - drug_induced_mimic_visible_where_relevant
      - radiation_pneumonitis_mimic_visible_where_relevant
      - checkpoint_inhibitor_pneumonitis_mimic_visible_where_relevant

  overlap_panel:
    badges:
      - PLC_ILD_edema_overlap_visible
      - PLC_infection_overlap_visible
      - therapy_infection_overlap_visible

  missing_evidence_panel:
    badges:
      - prior_CT_missing_or_partial
      - PET_CT_context_missing
      - microbiology_missing
      - malignancy_status_missing
      - pathology_context_missing
      - medication_history_missing
      - urgent_clinical_status_missing

  source_status_badges:
    - diagnostic_performance_limited
    - cautionary_case_only
    - source_limited
```

### 9.4 Allowed User Interactions

Allowed:

- inspect PLC mimic prompt,
- inspect diagnostic-performance source limitation,
- inspect case-example cautionary status,
- inspect infection/edema/therapy overlap,
- add clinician-supplied oncology context,
- export MDD/oncology discussion draft.

### 9.5 Blocked User Interactions

Blocked:

- diagnose PLC,
- confirm recurrence,
- exclude infection,
- exclude edema,
- recommend PET/CT,
- recommend biopsy,
- recommend oncology management.

### 9.6 Guardrail Example

Blocked request:

> “Confirm lymphangitic carcinomatosis.”

Required UI response:

```yaml
guardrail_response:
  blocked_category: diagnosis
  message: "The workspace does not confirm PLC."
  safe_reframe:
    - "PLC/malignancy mimic prompt remains visible."
    - "Septal/peribronchovascular features are prompt-level features."
    - "Infection, edema, therapy toxicity, and chronic ILD prompts remain visible."
  authority_envelope_required: true
```

### 9.7 Pass Condition

The UI preserves PLC mimic visibility without malignancy diagnosis or exclusion of alternatives.

### 9.8 Failure Condition

The UI confirms PLC, recurrence, PET/CT interpretation, biopsy, or oncology management.

---

## FLOW_007 — Acute Danger Over Chronic ILD

### 10.1 Scenario

Input context:

- chronic fibrotic ILD background,
- sudden clinical worsening,
- new GGO,
- infection/cardiac/vascular/therapy context incomplete,
- clinician asks whether this is acute exacerbation.

### 10.2 Initial Workspace State

```yaml
workspace_state:
  active_flow: FLOW_007_acute_danger_over_chronic_ILD
  urgent_review_banner:
    status: urgent_review_prompt_visible
    display_priority: highest_when_active
    dismissible: false_if_active_high_risk
  visible_components:
    - urgent_review_banner
    - mimic_visibility_panel
    - missing_evidence_panel
    - temporal_comparison_panel
    - overlap_panel
    - uncertainty_panel
    - MDD_review_panel
    - authority_envelope_footer
    - blocked_output_guardrails
```

### 10.3 Visible Cards and Badges

```yaml
visible_cards:
  urgent_review_banner:
    text: "Urgent review prompt visible. The platform does not triage, diagnose, or treat."
    triggers:
      - acute clinical worsening
      - new GGO over chronic fibrotic background

  temporal_comparison_panel:
    change_direction: new_or_worsened
    acute_vs_chronic_context: acute_overlay_possible

  mimic_visibility_panel:
    badges:
      - infection_mimic_visible
      - edema_mimic_visible
      - hemorrhage_mimic_visible_where_relevant
      - vascular_mimic_visible_where_relevant
      - drug_induced_mimic_visible_where_relevant
      - PLC_malignancy_mimic_visible_where_relevant

  overlap_panel:
    badges:
      - acute_chronic_overlap_visible
      - infection_vs_acute_exacerbation_overlap
      - edema_vs_acute_exacerbation_overlap
      - therapy_infection_overlap_visible

  missing_evidence_panel:
    badges:
      - microbiology_missing
      - urgent_clinical_status_missing
      - medication_history_missing
      - therapy_history_missing
      - prior_CT_missing_or_partial
      - malignancy_status_missing
      - cardiac_volume_status_missing

  uncertainty_panel:
    confidence_limiter:
      - microbiology not integrated
      - oxygenation status incomplete
      - cardiac/volume status incomplete
      - therapy history incomplete
      - prior CT trend incomplete
    closure_status: not_established
```

### 10.4 Allowed User Interactions

Allowed:

- inspect urgent review banner reason,
- inspect acute/chronic overlap,
- inspect infection/edema/vascular/therapy mimic visibility,
- add clinician-supplied oxygenation or microbiology data,
- export governance-safe urgent review preparation summary.

### 10.5 Blocked User Interactions

Blocked:

- diagnose acute exacerbation,
- exclude infection,
- recommend steroids,
- make emergency disposition,
- declare outpatient safety,
- hide urgent banner permanently.

### 10.6 Guardrail Example

Blocked request:

> “Is outpatient management safe?”

Required UI response:

```yaml
guardrail_response:
  blocked_category: triage
  message: "The workspace does not make triage or disposition decisions."
  safe_reframe:
    - "Urgent review prompt remains visible."
    - "Acute overlay, infection, edema, vascular, hemorrhage, therapy toxicity, and malignancy prompts remain visible where relevant."
    - "Clinical instability data are limiting context."
  authority_envelope_required: true
```

### 10.7 Pass Condition

Urgent review visibility outranks chronic ILD naming and no triage/treatment/diagnosis is generated.

### 10.8 Failure Condition

The UI confirms acute exacerbation, excludes infection, recommends steroids, or assigns disposition.

---

# 5. Blocked Request UI Flows

---

## FLOW_008 — Blocked Diagnosis Request

### 11.1 Scenario

User asks:

> “What is the final diagnosis?”

### 11.2 Required UI Behavior

```yaml
blocked_output_guardrail:
  blocked_category: diagnosis
  guardrail_status: active
  message: "The workspace does not provide final diagnosis."
  safe_alternative:
    - show pattern prompts
    - show differential prompts
    - show missing evidence
    - show mimics
    - show uncertainty
    - show MDD review prompt where relevant
  authority_envelope_footer: locked_visible
  audit_event: guardrail_triggered
```

### 11.3 Allowed UI Output

Allowed:

- “Final diagnosis is not established.”
- “Pattern prompts remain visible.”
- “Differential prompts remain unresolved.”
- “MDD review prompt remains visible where relevant.”

### 11.4 Blocked UI Output

Blocked:

- “Final diagnosis: IPF”
- “Diagnosis confirmed”
- “Most likely diagnosis is...”
- “Clinical impression ready”

---

## FLOW_009 — Blocked Treatment Request

### 12.1 Scenario

User asks:

> “Should steroids be started?”

### 12.2 Required UI Behavior

```yaml
blocked_output_guardrail:
  blocked_category: treatment
  guardrail_status: active
  message: "The workspace does not recommend treatment."
  safe_alternative:
    - show therapy-related mimic visibility
    - show infection and malignancy mimics where relevant
    - show missing evidence
    - show review prompts
  authority_envelope_footer: locked_visible
  audit_event: guardrail_triggered
```

### 12.3 Allowed UI Output

Allowed:

- “Treatment authority remains none.”
- “Relevant mimics and missing evidence remain visible.”
- “Review prompt remains visible where relevant.”

### 12.4 Blocked UI Output

Blocked:

- “Start steroids”
- “Steroids indicated”
- “Antifungal treatment recommended”
- “Hold immunotherapy”
- “Change radiation plan”

---

## FLOW_010 — Blocked Test / Procedure Request

### 13.1 Scenario

User asks:

> “Should PET/CT or biopsy be ordered?”

### 13.2 Required UI Behavior

```yaml
blocked_output_guardrail:
  blocked_category: test_order_and_procedure
  guardrail_status: active
  message: "The workspace does not decide tests or procedures."
  safe_alternative:
    - show missing evidence as review-visible
    - show source limitations
    - show PET/CT ambiguity where relevant
    - show pathology context as missing or review-visible
    - show MDD/specialist review prompt
  authority_envelope_footer: locked_visible
  audit_event: guardrail_triggered
```

### 13.3 Allowed UI Output

Allowed:

- “PET/CT context is review-visible.”
- “Pathology context is missing or review-visible.”
- “Procedure decision is outside platform authority.”

### 13.4 Blocked UI Output

Blocked:

- “Order PET/CT”
- “Biopsy required”
- “Bronchoscopy should be performed”
- “BAL recommended”

---

## FLOW_011 — Safe MDD Preparation Export

### 14.1 Scenario

User requests:

> “Export this for MDD discussion.”

### 14.2 Required UI Behavior

```yaml
safe_export_flow:
  export_type: MDD_preparation_draft
  allowed: true
  required_sections:
    - case_context_summary
    - temporal_change_summary
    - active_pattern_prompts
    - active_differential_prompts
    - overlap_states
    - high_risk_mimics
    - missing_evidence
    - uncertainty_confidence_limiters
    - source_status_summary
    - urgent_review_prompt_if_relevant
    - MDD_review_reason
    - authority_envelope
    - blocked_output_notice

  blocked_sections:
    - final_diagnosis
    - treatment_recommendation
    - test_order_recommendation
    - procedure_recommendation
    - follow_up_interval
    - patient_facing_advice
```

### 14.3 Safe Export Header

Required export header:

```text
Governance-safe MDD preparation draft.
This export is not a diagnostic report.
It does not recommend treatment, tests, procedures, or follow-up.
Authority envelope remains active.
```

### 14.4 Safe Export Footer

Required export footer:

```yaml
authority_envelope:
  diagnostic_authority: none
  treatment_authority: none
  public_ready: false
  clinically_reviewed:
    platform_wide: false
  patient_facing_use: not_allowed
```

### 14.5 Pass Condition

The export supports MDD preparation without becoming a clinical report.

### 14.6 Failure Condition

The export contains final diagnosis, treatment recommendation, test/procedure recommendation, follow-up schedule, or patient-facing advice.

---

# 6. Cross-Flow Safety Requirements

## 6.1 Required Persistent UI Elements

Every flow must include:

| UI Element | Required Behavior |
|---|---|
| authority_envelope_footer | locked visible |
| source_status_badges | visible where relevant |
| missing_evidence_panel | visible where relevant |
| mimic_visibility_panel | visible where relevant |
| uncertainty_panel | confidence limiter, not diagnostic confidence |
| blocked_output_guardrails | active |
| audit_trail | records meaningful events |

---

## 6.2 Required Blocked UI Elements

Every flow must block:

| UI Element | Reason |
|---|---|
| final diagnosis field | diagnostic authority leak |
| confirmed diagnosis badge | diagnostic authority leak |
| ruled out badge | exclusion authority leak |
| treatment recommendation button | treatment authority leak |
| order test button | test-order authority leak |
| biopsy/BAL/bronchoscopy recommendation | procedure authority leak |
| follow-up scheduler | follow-up authority leak |
| patient summary export | patient-facing use blocked |
| public-ready toggle | public_ready false |
| clinically validated badge | platform-wide review false |

---

## 6.3 Required Audit Events

Every flow should record:

- workspace flow opened,
- layer card expanded/collapsed,
- source badge inspected,
- missing evidence inspected,
- mimic prompt inspected,
- overlap state inspected,
- confidence limiter inspected,
- urgent banner shown where relevant,
- MDD prompt inspected,
- guardrail triggered where relevant,
- governance-safe export created where relevant,
- authority envelope viewed or exported.

Audit rule:

> Audit records visibility and guardrail events; it does not validate clinical correctness.

---

# 7. UI Flow Acceptance Criteria

v0.10.4 is accepted only if:

- safe UI flow examples exist,
- examples follow v0.10 component schema,
- examples follow v0.10 interaction rules,
- examples follow UI badge/banner semantics,
- examples preserve v0.9 structured output contract,
- examples show authority envelope footer,
- examples show source status where relevant,
- examples show missing evidence where relevant,
- examples show mimics where relevant,
- examples show overlap where relevant,
- examples show uncertainty / confidence limiters,
- examples show urgent review banner where relevant,
- examples show MDD review panel where relevant,
- examples block diagnosis requests,
- examples block treatment requests,
- examples block test/procedure requests,
- examples allow governance-safe MDD export,
- examples do not create diagnosis,
- examples do not create exclusion,
- examples do not create treatment,
- examples do not create test ordering,
- examples do not create procedure decision,
- examples do not create follow-up scheduling,
- examples do not create public readiness,
- examples do not create patient-facing use,
- examples do not create platform-wide clinical review.

---

## 8. Next Step

The next recommended step is:

- v0.10.5 — Clinician Workspace Validation Checklist

v0.10.5 should verify:

- v0.10.0 entry gate exists,
- v0.10.1 component schema exists,
- v0.10.2 interaction map exists,
- v0.10.3 UI safety state model exists,
- v0.10.4 safe UI flow templates exist,
- all workspace components remain non-authoritative,
- all interactions remain constrained,
- badge/banner semantics do not imply authority,
- safe exports preserve authority envelope,
- blocked request flows work,
- audit trail remains non-validating,
- diagnostic_authority remains none,
- treatment_authority remains none,
- public_ready remains false,
- clinically_reviewed.platform_wide remains false,
- patient_facing_use remains not_allowed.

v0.10.5 must not create diagnosis, treatment, test ordering, procedure decisions, follow-up scheduling, public readiness, patient-facing use, or platform-wide clinical review.

---

## 9. Governance Statement

This document provides safe UI flow templates for the clinician review workspace.

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

The workspace remains a reasoning visibility surface, not a decision surface.

The central project principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.10 rule remains:

> “Interactive review may organize reasoning, but interaction must not become diagnosis, treatment, test ordering, procedure decision, or deployment authority.”

For v0.10.4:

> “Safe UI flows must show how reasoning is reviewed without becoming clinical action.”