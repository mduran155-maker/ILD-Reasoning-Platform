# ILD Reasoning Platform — Structured Output Safe Response Templates v1

Version: v0.9.2  
Status: structured_output_safe_response_templates  
Scope: Safe clinician-facing structured response examples for v0.9 output contract  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This document provides safe structured output examples for the ILD Reasoning Platform.

It follows:

- `docs/navigation/reasoning_output_contract_entry_gate_v1.md`
- `docs/data/schema/structured_output_layer_schema_v1.md`
- `docs/navigation/high_risk_mimic_structural_seal_v1.md`
- `docs/navigation/project_status_roadmap_checkpoint_v0_8.md`
- `docs/navigation/non_uip_fibrotic_ild_differential_seal_v1.md`

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

Its purpose is to show how the structured output contract should behave in realistic reasoning scenarios.

The v0.9 rule remains:

> “Structured output must display uncertainty, sources, missing evidence, mimics, overlap, review prompts, and authority limits before any disease name is allowed to dominate the response.”

For v0.9.2:

> “Examples must show safe reasoning behavior without turning templates into clinical protocols.”

---

## 2. Global Template Rules

Every safe response template must preserve:

```yaml
authority_envelope:
  diagnostic_authority: none
  treatment_authority: none
  public_ready: false
  clinically_reviewed:
    platform_wide: false
  patient_facing_use: not_allowed
```

Every template must avoid:

- final diagnosis,
- disease exclusion,
- treatment recommendation,
- test order,
- procedure decision,
- follow-up interval,
- MDD replacement,
- urgent review replacement,
- public-ready claim,
- platform-wide clinically reviewed claim.

Every template should use:

- “supports”
- “suggests”
- “weakens”
- “remains visible”
- “remains unresolved”
- “missing evidence limits interpretation”
- “final diagnosis is not established by this platform”

Every template should avoid:

- “diagnoses”
- “confirms”
- “proves”
- “rules out”
- “excludes”
- “requires treatment”
- “should start treatment”
- “order”
- “biopsy should be performed”
- “follow up every X months”

---

## 3. Global Safe Response Structure

Each example follows the four-phase Case Reasoning Flow.

```yaml
structured_response:
  phase_1_grounding:
    case_context_summary: ...
    temporal_change_summary: ...

  phase_2_reasoning_core:
    pattern_family_prompts: ...
    differential_prompt_layer: ...
    overlap_layer: ...

  phase_3_safety_net:
    high_risk_mimic_layer: ...
    missing_evidence_layer: ...
    uncertainty_layer: ...

  phase_4_escalation_and_governance:
    urgent_review_prompt_layer: ...
    MDD_review_prompt_layer: ...
    source_status_layer: ...
    authority_envelope: ...
    blocked_outputs: ...
```

---

# 4. Safe Response Templates

---

## TEMPLATE_001 — UIP-Like Pattern With Missing Exposure History

### Scenario

A clinician asks:

> “Basal subplevral retikülasyon ve bal peteği var. Bu IPF mi?”

### Safe Structured Output

```yaml
structured_response:
  phase_1_grounding:
    case_context_summary:
      provided_context:
        - basal subpleural reticulation reported
        - honeycombing reported
      not_provided:
        - exposure history
        - CTD/SARD context
        - medication history
        - occupational history
        - prior imaging comparison
        - MDD status
      inferred_facts: []

    temporal_change_summary:
      prior_comparison_available: not_provided
      change_direction: not_assessable
      temporal_limiter:
        - prior CT unavailable or not provided
      statement: "Temporal change cannot be established from the provided context."

  phase_2_reasoning_core:
    pattern_family_prompts:
      active_pattern_prompts:
        - UIP_like_prompt
      safe_statement: "The provided imaging description may support a UIP-like pattern prompt, but pattern visibility does not establish IPF diagnosis."

    differential_prompt_layer:
      active_differential_prompts:
        - IPF_context_prompt
        - fibrotic_HP_prompt
        - CTD_ILD_prompt
        - occupational_mimic_prompt
        - drug_therapy_related_mimic_prompt
      safe_statement: "IPF remains a reasoning prompt, not a platform diagnosis."

    overlap_layer:
      overlap_states:
        - UIP_vs_HP_overlap
        - UIP_vs_CTD_ILD_overlap
        - UIP_vs_occupational_mimic_overlap
      safe_statement: "UIP-like fibrosis can remain visible while known-cause fibrotic ILD prompts remain unresolved."

  phase_3_safety_net:
    high_risk_mimic_layer:
      active_mimic_prompts:
        - occupational_ILD_mimic
        - drug_induced_ILD_mimic
        - infection_mimic_where_relevant
        - malignancy_mimic_where_relevant
      safe_statement: "High-risk mimic prompts remain visible where relevant and are not diagnosed or excluded by this platform."

    missing_evidence_layer:
      missing_items:
        - exposure_history
        - occupational_history
        - CTD_SARD_context
        - medication_history
        - prior_CT
        - MDD_status
      safe_statement: "Missing exposure and autoimmune context limit interpretation and do not exclude non-IPF causes."

    uncertainty_layer:
      unresolved_questions:
        - IPF vs known-cause UIP-like fibrosis
        - fibrotic HP vs IPF
        - CTD-ILD vs IPF
      confidence_limiter:
        - exposure history incomplete
        - CTD/SARD context incomplete
        - prior imaging unavailable
        - MDD not documented
      closure_status: not_established

  phase_4_escalation_and_governance:
    urgent_review_prompt_layer:
      urgent_prompt_visible: false_unless_acute_clinical_danger_is_present
      statement: "Urgent review prompt depends on acute symptoms, oxygenation, systemic illness, or rapid change, which are not provided."

    MDD_review_prompt_layer:
      MDD_prompt_visible: true
      review_reason:
        - UIP-like pattern requires clinical, exposure, autoimmune, and radiologic integration
      safe_statement: "MDD / specialist review prompt remains visible."

    source_status_layer:
      source_status:
        - UIP/IPF claim mapping source-supported in narrow reviewed scope
        - platform-wide clinical review remains false
      source_limitations:
        - source mapping does not create diagnosis
        - source mapping does not create public readiness

    authority_envelope:
      diagnostic_authority: none
      treatment_authority: none
      public_ready: false
      clinically_reviewed:
        platform_wide: false
        narrow_reviewed_scopes:
          - temporal_comparison_methodology
          - ATS_ERS_JRS_ALAT_2022_UIP_claim_to_source_mapping
      patient_facing_use: not_allowed

    blocked_outputs:
      - "This is IPF."
      - "IPF confirmed."
      - "HP excluded."
      - "No MDD needed."
      - "Treatment should be started."
```

### Safe Plain-Language Version

Platform tanısal etiketleme yapmaz.

Bu bulgular UIP-benzeri patern promptunu destekleyebilir; ancak IPF tanısı bu platform tarafından konulmaz. Maruziyet öyküsü, CTD/SARD bağlamı, fibrotik HP olasılığı, ilaç/meslek/enfeksiyon/malignite mimikleri ve MDD entegrasyonu görünür kalmalıdır.

Final diagnosis is not established by this platform.

---

## TEMPLATE_002 — Fibrotic HP vs UIP Overlap

### Scenario

A clinician asks:

> “Bal peteği de var ama mozaik atenüasyon ve hava hapsi de tariflenmiş. IPF mi HP mi?”

### Safe Structured Output

```yaml
structured_response:
  phase_1_grounding:
    case_context_summary:
      provided_context:
        - fibrotic ILD features reported
        - honeycombing or UIP-like fibrosis reported
        - mosaic attenuation / air trapping reported
      not_provided:
        - exposure history
        - expiratory HRCT quality/context
        - BAL lymphocyte context
        - serum IgG context
        - autoimmune context
        - prior imaging comparison
        - MDD status
      inferred_facts: []

    temporal_change_summary:
      prior_comparison_available: not_provided
      change_direction: not_assessable
      statement: "Temporal behavior is not established without prior comparison."

  phase_2_reasoning_core:
    pattern_family_prompts:
      active_pattern_prompts:
        - UIP_like_prompt
        - fibrotic_HP_like_prompt
        - small_airway_feature_prompt
      safe_statement: "UIP-like fibrosis and HP-like small-airway features can coexist as reasoning prompts."

    differential_prompt_layer:
      active_differential_prompts:
        - IPF_context_prompt
        - fibrotic_HP_prompt
        - CTD_ILD_prompt
        - occupational_mimic_prompt
      safe_statement: "The platform does not choose IPF or HP as a diagnosis."

    overlap_layer:
      overlap_states:
        - HP_vs_UIP_overlap
        - HP_vs_occupational_exposure_overlap
        - HP_vs_CTD_ILD_overlap
      safe_statement: "The HP/UIP boundary remains unresolved."

  phase_3_safety_net:
    high_risk_mimic_layer:
      active_mimic_prompts:
        - occupational_exposure_mimic
        - infection_mimic_where_relevant
        - drug_therapy_related_mimic_where_relevant
      safe_statement: "Mimics remain visible where relevant and are not excluded."

    missing_evidence_layer:
      missing_items:
        - detailed exposure history
        - expiratory HRCT context
        - BAL context
        - serum IgG context
        - autoimmune context
        - prior CT
        - MDD status
      safe_statement: "Missing exposure does not exclude HP."

    uncertainty_layer:
      unresolved_questions:
        - fibrotic HP vs IPF
        - UIP-like fibrosis from known cause vs idiopathic context
      confidence_limiter:
        - exposure history incomplete
        - expiratory HRCT context incomplete
        - BAL not integrated
        - prior comparison unavailable
      closure_status: not_established

  phase_4_escalation_and_governance:
    urgent_review_prompt_layer:
      urgent_prompt_visible: false_unless_acute_worsening_or_hypoxemia_present

    MDD_review_prompt_layer:
      MDD_prompt_visible: true
      review_reason:
        - fibrotic HP and UIP-like fibrosis overlap
        - missing exposure and small-airway evidence context
      safe_statement: "MDD prompt remains visible."

    source_status_layer:
      source_status:
        - HP source mapping supports prompt visibility
        - UIP source mapping supports pattern boundary visibility
      source_limitations:
        - no diagnosis created
        - no treatment created

    authority_envelope:
      diagnostic_authority: none
      treatment_authority: none
      public_ready: false
      clinically_reviewed:
        platform_wide: false
      patient_facing_use: not_allowed

    blocked_outputs:
      - "This is IPF."
      - "This is fibrotic HP."
      - "Exposure missing, so HP is excluded."
      - "Start treatment."
```

### Safe Plain-Language Version

UIP-benzeri fibrozis ve HP-benzeri küçük havayolu bulguları birlikte görünür kalabilir. Platform IPF veya fibrotik HP tanısı koymaz. Eksik maruziyet öyküsü HP’yi dışlamaz; ekspiryum HRCT, BAL, serum IgG, otoimmün bağlam, önceki BT ve MDD durumu yorumun sınırlandırıcı parçalarıdır.

---

## TEMPLATE_003 — NSIP / OP Overlap With Missing CTD and Infection Context

### Scenario

A clinician asks:

> “Bilateral GGO, retikülasyon ve yamalı konsolidasyon var. NSIP mi OP mi?”

### Safe Structured Output

```yaml
structured_response:
  phase_1_grounding:
    case_context_summary:
      provided_context:
        - bilateral ground-glass opacity reported
        - reticulation reported
        - patchy consolidation reported
      not_provided:
        - CTD/SARD context
        - infection data
        - medication history
        - aspiration risk
        - prior imaging
        - pathology context
        - MDD status
      inferred_facts: []

    temporal_change_summary:
      prior_comparison_available: not_provided
      change_direction: not_assessable
      statement: "Acute vs chronic behavior is not established without temporal comparison."

  phase_2_reasoning_core:
    pattern_family_prompts:
      active_pattern_prompts:
        - NSIP_like_prompt
        - OP_like_prompt
        - mixed_pattern_prompt
      safe_statement: "NSIP-like and OP-like pattern prompts remain visible without diagnosis."

    differential_prompt_layer:
      active_differential_prompts:
        - CTD_ILD_prompt
        - infection_mimic_prompt
        - drug_induced_ILD_prompt
        - aspiration_mimic_prompt
        - HP_prompt
      safe_statement: "Idiopathic NSIP or COP closure is blocked while secondary causes remain incomplete."

    overlap_layer:
      overlap_states:
        - NSIP_vs_OP_overlap
        - OP_vs_infection_overlap
        - OP_vs_aspiration_overlap
        - NSIP_vs_CTD_ILD_overlap
        - drug_induced_ILD_vs_NSIP_OP_overlap
      safe_statement: "Overlap remains unresolved."

  phase_3_safety_net:
    high_risk_mimic_layer:
      active_mimic_prompts:
        - infection_mimic
        - aspiration_mimic
        - drug_induced_ILD_mimic
        - CTD_ILD_context_prompt
      safe_statement: "High-risk and secondary-cause prompts remain visible."

    missing_evidence_layer:
      missing_items:
        - autoimmune symptoms/signs
        - serology context
        - microbiology
        - medication history
        - aspiration risk
        - prior imaging
        - MDD status
      safe_statement: "Missing CTD and infection context limits interpretation."

    uncertainty_layer:
      unresolved_questions:
        - NSIP-like vs OP-like process
        - idiopathic vs secondary cause
        - infection or aspiration overlay
      confidence_limiter:
        - CTD/SARD context incomplete
        - infection data incomplete
        - medication history incomplete
        - aspiration risk incomplete
      closure_status: not_established

  phase_4_escalation_and_governance:
    urgent_review_prompt_layer:
      urgent_prompt_visible: true_if_acute_symptoms_or_oxygen_worsening_present
      safe_statement: "If fever, hypoxemia, or rapid worsening is present, urgent review prompt remains visible."

    MDD_review_prompt_layer:
      MDD_prompt_visible: true
      review_reason:
        - mixed NSIP/OP-like pattern
        - secondary-cause visibility
        - infection/aspiration/drug/CTD uncertainty

    source_status_layer:
      source_status:
        - IIP classification source supports NSIP/OP prompt visibility
        - CTD and high-risk mimic sources support secondary-cause visibility
      source_limitations:
        - no OP/COP diagnosis
        - no NSIP diagnosis
        - no treatment or test authority

    authority_envelope:
      diagnostic_authority: none
      treatment_authority: none
      public_ready: false
      clinically_reviewed:
        platform_wide: false
      patient_facing_use: not_allowed

    blocked_outputs:
      - "This is NSIP."
      - "This is COP."
      - "Infection excluded."
      - "Start steroids."
      - "Order serology."
```

### Safe Plain-Language Version

NSIP-benzeri ve OP-benzeri patern promptları birlikte görünür kalır. Bu, idiopatik NSIP veya COP tanısı anlamına gelmez. CTD/SARD bağlamı, enfeksiyon verisi, ilaç öyküsü ve aspirasyon riski eksikse ikincil nedenler kapanmamalıdır.

---

## TEMPLATE_004 — Sarcoid-Like Granulomatous Pattern With Missing Microbiology and Beryllium Context

### Scenario

A clinician asks:

> “Nonnekrotizan granülom var. Sarkoidoz diyebilir miyiz?”

### Safe Structured Output

```yaml
structured_response:
  phase_1_grounding:
    case_context_summary:
      provided_context:
        - nonnecrotizing granulomatous inflammation reported
      not_provided:
        - microbiology context
        - TB/NTM/fungal evaluation
        - beryllium exposure history
        - occupational history
        - radiologic distribution
        - extrapulmonary sarcoid context
        - malignancy context
        - MDD status
      inferred_facts: []

    temporal_change_summary:
      prior_comparison_available: not_provided
      change_direction: not_assessable
      statement: "Temporal behavior is not established."

  phase_2_reasoning_core:
    pattern_family_prompts:
      active_pattern_prompts:
        - granulomatous_prompt
        - sarcoid_like_prompt
      safe_statement: "Nonnecrotizing granulomas support sarcoid-like reasoning but do not diagnose sarcoidosis."

    differential_prompt_layer:
      active_differential_prompts:
        - sarcoidosis_granulomatous_prompt
        - TB_mimic_prompt
        - NTM_mimic_prompt
        - fungal_mimic_prompt
        - beryllium_sarcoid_mimic_prompt
        - HP_prompt
        - malignancy_sarcoid_like_reaction_prompt
      safe_statement: "Alternative granulomatous causes remain visible."

    overlap_layer:
      overlap_states:
        - sarcoidosis_vs_infection_overlap
        - sarcoidosis_vs_beryllium_overlap
        - sarcoidosis_vs_HP_overlap
        - sarcoidosis_vs_malignancy_overlap
      safe_statement: "Granulomatous overlap remains unresolved."

  phase_3_safety_net:
    high_risk_mimic_layer:
      active_mimic_prompts:
        - TB_mimic
        - NTM_mimic
        - fungal_mimic
        - beryllium_sarcoid_mimic
        - malignancy_sarcoid_like_reaction_mimic
      safe_statement: "Infectious, occupational, HP, and malignancy mimics are not excluded."

    missing_evidence_layer:
      missing_items:
        - microbiology
        - AFB_culture_NAAT_context
        - fungal_testing_context
        - occupational_history
        - beryllium_exposure_context
        - BeLPT_context
        - malignancy_context
        - radiologic_distribution
        - MDD_status
      safe_statement: "Missing microbiology and beryllium context limit interpretation."

    uncertainty_layer:
      unresolved_questions:
        - sarcoidosis vs infectious granulomatous mimic
        - sarcoidosis vs berylliosis
        - sarcoidosis vs HP
        - sarcoidosis vs malignancy/sarcoid-like reaction
      confidence_limiter:
        - microbiology not integrated
        - beryllium exposure context incomplete
        - malignancy context incomplete
        - MDD not documented
      closure_status: not_established

  phase_4_escalation_and_governance:
    urgent_review_prompt_layer:
      urgent_prompt_visible: true_if_fever_systemic_illness_immunosuppression_or_rapid_decline_present

    MDD_review_prompt_layer:
      MDD_prompt_visible: true
      review_reason:
        - granulomatous differential requires clinical-radiologic-pathology-microbiology integration

    source_status_layer:
      source_status:
        - sarcoidosis source supports three-domain diagnostic framing as review prompts
        - beryllium source supports beryllium mimic visibility
        - TB/NTM/fungal sources support infection mimic visibility
      source_limitations:
        - histopathology alone does not establish sarcoidosis
        - no biopsy/procedure/treatment authority

    authority_envelope:
      diagnostic_authority: none
      treatment_authority: none
      public_ready: false
      clinically_reviewed:
        platform_wide: false
      patient_facing_use: not_allowed

    blocked_outputs:
      - "Sarcoidosis confirmed."
      - "Nonnecrotizing granulomas prove sarcoidosis."
      - "TB excluded."
      - "Berylliosis excluded."
      - "Start treatment."
      - "Biopsy should be performed."
```

### Safe Plain-Language Version

Nonnekrotizan granülom sarkoidoz-benzeri reasoning’i destekleyebilir; fakat tek başına sarkoidoz tanısı koydurmaz. TB, NTM, fungal enfeksiyon, berylliosis, HP ve malignite/sarcoid-like reaction mimikleri görünür kalmalıdır. Platform tanı, dışlama, biyopsi veya tedavi kararı vermez.

---

## TEMPLATE_005 — Post-Radiation New GGO With Infection / Recurrence / ICI Overlap

### Scenario

A clinician asks:

> “Radyoterapi sonrası yeni GGO var. Radyasyon pnömoniti mi?”

### Safe Structured Output

```yaml
structured_response:
  phase_1_grounding:
    case_context_summary:
      provided_context:
        - prior radiation therapy reported
        - new ground-glass opacity reported
      not_provided:
        - radiation field
        - radiation timing
        - radiation dose/fractionation
        - infection data
        - tumor status
        - medication/ICI exposure
        - prior imaging comparison details
        - oxygenation status
        - MDD status
      inferred_facts: []

    temporal_change_summary:
      prior_comparison_available: partial_or_not_provided
      change_direction: new
      acute_vs_chronic_context: acute_overlay_possible
      statement: "New GGO is visible, but cause is not established."

  phase_2_reasoning_core:
    pattern_family_prompts:
      active_pattern_prompts:
        - acute_GGO_overlay_prompt
        - radiation_related_mimic_prompt
      safe_statement: "Radiation-related prompt is visible but does not establish radiation pneumonitis."

    differential_prompt_layer:
      active_differential_prompts:
        - radiation_pneumonitis_mimic_prompt
        - infection_mimic_prompt
        - tumor_recurrence_or_progression_prompt
        - drug_induced_ILD_prompt
        - checkpoint_inhibitor_pneumonitis_prompt
        - ILD_progression_prompt
      safe_statement: "Radiation pneumonitis remains a prompt, not a diagnosis."

    overlap_layer:
      overlap_states:
        - radiation_pneumonitis_vs_infection_overlap
        - radiation_pneumonitis_vs_recurrence_overlap
        - radiation_pneumonitis_vs_CIP_overlap
        - drug_induced_ILD_vs_infection_overlap
      safe_statement: "Therapy-related and infection/recurrence overlaps remain unresolved."

  phase_3_safety_net:
    high_risk_mimic_layer:
      active_mimic_prompts:
        - infection_mimic
        - malignancy_recurrence_mimic
        - checkpoint_inhibitor_pneumonitis_mimic
        - drug_induced_ILD_mimic
      safe_statement: "High-risk mimics are not excluded."

    missing_evidence_layer:
      missing_items:
        - radiation_field
        - radiation_timing
        - radiation_dose_context
        - infection_data
        - tumor_status
        - medication_history
        - ICI_exposure
        - oxygenation_status
        - prior_CT
      safe_statement: "Missing radiation and infection/recurrence context limits interpretation."

    uncertainty_layer:
      unresolved_questions:
        - radiation pneumonitis vs infection
        - radiation pneumonitis vs tumor recurrence
        - radiation pneumonitis vs ICI/drug toxicity
        - acute overlay vs chronic ILD progression
      confidence_limiter:
        - radiation field/timing not integrated
        - infection data incomplete
        - tumor status incomplete
        - ICI/drug exposure incomplete
      closure_status: not_established

  phase_4_escalation_and_governance:
    urgent_review_prompt_layer:
      urgent_prompt_visible: true_if_hypoxemia_rapid_worsening_fever_or_severe_symptoms_present
      statement: "Urgent review prompt remains visible where acute clinical danger exists."

    MDD_review_prompt_layer:
      MDD_prompt_visible: true
      specialist_review_prompts:
        - pulmonology
        - thoracic_radiology
        - oncology
        - radiation_oncology
        - microbiology_where_relevant

    source_status_layer:
      source_status:
        - radiation pneumonitis sources are source-limited and treatment-heavy where relevant
      source_limitations:
        - no steroid recommendation
        - no radiation plan change
        - no recurrence exclusion

    authority_envelope:
      diagnostic_authority: none
      treatment_authority: none
      public_ready: false
      clinically_reviewed:
        platform_wide: false
      patient_facing_use: not_allowed

    blocked_outputs:
      - "Radiation pneumonitis diagnosed."
      - "Start steroids."
      - "Recurrence excluded."
      - "Change radiation plan."
      - "No urgent review needed."
```

### Safe Plain-Language Version

Radyoterapi sonrası yeni GGO, radyasyon pnömoniti promptunu görünür yapabilir; ancak enfeksiyon, tümör progresyonu/rekürrens, ilaç toksisitesi, ICI pnömoniti ve ILD progresyonu görünür kalmalıdır. Platform radyasyon pnömoniti tanısı koymaz, steroid veya radyoterapi yönetimi önermez.

---

## TEMPLATE_006 — ICI Exposure With FDG-Avid Nodes

### Scenario

A clinician asks:

> “İmmünoterapi sonrası FDG-avid mediastinal LAP var. Rekürrens mi, sarcoid-like reaction mı?”

### Safe Structured Output

```yaml
structured_response:
  phase_1_grounding:
    case_context_summary:
      provided_context:
        - checkpoint inhibitor exposure reported
        - FDG-avid mediastinal lymphadenopathy reported
        - malignancy context implied
      not_provided:
        - pathology/tissue confirmation
        - infection data
        - prior PET/CT trend
        - systemic symptoms
        - treatment timeline details
        - tumor status
        - MDD status
      inferred_facts: []

    temporal_change_summary:
      prior_comparison_available: not_provided_or_unclear
      change_direction: new_or_unclear
      statement: "Temporal behavior and trend are not fully established."

  phase_2_reasoning_core:
    pattern_family_prompts:
      active_pattern_prompts:
        - FDG_avid_lymphadenopathy_prompt
        - ICI_sarcoid_like_reaction_prompt
        - malignancy_recurrence_prompt
      safe_statement: "FDG avidity creates ambiguity but does not settle recurrence or sarcoid-like reaction."

    differential_prompt_layer:
      active_differential_prompts:
        - malignancy_recurrence_prompt
        - lymphoma_or_metastatic_prompt_where_relevant
        - ICI_sarcoid_like_reaction_prompt
        - sarcoidosis_prompt
        - infection_mimic_prompt
      safe_statement: "Recurrence and sarcoid-like reaction remain ambiguous."

    overlap_layer:
      overlap_states:
        - ICI_SLR_vs_malignancy_recurrence_overlap
        - PET_CT_ambiguity_overlap
        - sarcoidosis_vs_infection_overlap
      safe_statement: "Overlap remains unresolved."

  phase_3_safety_net:
    high_risk_mimic_layer:
      active_mimic_prompts:
        - malignancy_recurrence_mimic
        - lymphoma_recurrence_mimic_where_relevant
        - infection_mimic
        - sarcoid_like_reaction_mimic
      safe_statement: "Malignancy is not excluded by this platform."

    missing_evidence_layer:
      missing_items:
        - pathology_context
        - microbiology
        - prior_PET_CT_trend
        - systemic_symptom_context
        - tumor_status
        - treatment_timeline
        - MDD_status
      safe_statement: "Missing pathology and trend context limit interpretation."

    uncertainty_layer:
      unresolved_questions:
        - recurrence vs ICI-associated sarcoid-like reaction
        - lymphoma/metastatic disease vs benign granulomatous reaction
        - infection vs inflammatory mimic
      confidence_limiter:
        - PET/CT ambiguity
        - tissue context missing
        - tumor status incomplete
        - infection data incomplete
      closure_status: not_established

  phase_4_escalation_and_governance:
    urgent_review_prompt_layer:
      urgent_prompt_visible: true_if_rapid_progression_systemic_illness_or_clinical_instability_present

    MDD_review_prompt_layer:
      MDD_prompt_visible: true
      specialist_review_prompts:
        - oncology
        - thoracic_radiology
        - pathology
        - pulmonology
        - microbiology_where_relevant

    source_status_layer:
      source_status:
        - ICI-SLR and sarcoid-like reaction sources support ambiguity visibility
        - diagnostic-performance/PET ambiguity does not create interpretation authority
      source_limitations:
        - no biopsy decision
        - no immunotherapy hold/restart advice
        - no malignancy exclusion

    authority_envelope:
      diagnostic_authority: none
      treatment_authority: none
      public_ready: false
      clinically_reviewed:
        platform_wide: false
      patient_facing_use: not_allowed

    blocked_outputs:
      - "This is recurrence."
      - "This is sarcoid-like reaction."
      - "Recurrence excluded."
      - "PET/CT proves benign disease."
      - "Biopsy should be performed."
      - "Stop immunotherapy."
```

### Safe Plain-Language Version

FDG-avid LAP, immünoterapi sonrası sarcoid-like reaction ve malignite rekürrensi arasında belirsizlik yaratabilir. Platform rekürrens veya sarcoid-like reaction tanısı koymaz; PET/CT tek başına bu ayrımı kapatmaz. Patoloji, trend, enfeksiyon ve onkoloji bağlamı review-visible kalmalıdır.

---

## TEMPLATE_007 — Known Malignancy With Septal Thickening / PLC Mimic

### Scenario

A clinician asks:

> “Kanser hastasında yeni septal kalınlaşma var. Lymphangitic carcinomatosis mi?”

### Safe Structured Output

```yaml
structured_response:
  phase_1_grounding:
    case_context_summary:
      provided_context:
        - known malignancy reported
        - new septal thickening reported
      not_provided:
        - peribronchovascular thickening details
        - pleural effusion status
        - lymphadenopathy status
        - infection data
        - edema/cardiac context
        - therapy history
        - PET/CT context
        - pathology context
        - prior imaging trend
      inferred_facts: []

    temporal_change_summary:
      prior_comparison_available: partial_or_not_provided
      change_direction: new
      statement: "New septal thickening is visible, but cause is not established."

  phase_2_reasoning_core:
    pattern_family_prompts:
      active_pattern_prompts:
        - septal_thickening_prompt
        - malignancy_mimic_prompt
        - PLC_feature_prompt
      safe_statement: "Septal thickening may support PLC mimic visibility but does not diagnose PLC."

    differential_prompt_layer:
      active_differential_prompts:
        - pulmonary_lymphangitic_carcinomatosis_mimic_prompt
        - infection_mimic_prompt
        - edema_prompt
        - drug_or_radiation_or_ICI_toxicity_prompt
        - chronic_ILD_prompt
      safe_statement: "PLC remains a mimic prompt, not a diagnosis."

    overlap_layer:
      overlap_states:
        - PLC_vs_ILD_overlap
        - PLC_vs_infection_overlap
        - PLC_vs_edema_overlap
        - PLC_vs_therapy_toxicity_overlap
      safe_statement: "Malignancy, infection, edema, and therapy-related overlap remain visible."

  phase_3_safety_net:
    high_risk_mimic_layer:
      active_mimic_prompts:
        - PLC_malignancy_mimic
        - infection_mimic
        - edema_mimic
        - therapy_related_mimic
      safe_statement: "High-risk mimics remain visible and are not diagnosed or excluded."

    missing_evidence_layer:
      missing_items:
        - prior_CT
        - PET_CT_context
        - infection_data
        - cardiac_volume_status
        - therapy_history
        - pathology_context
        - oncology_status
      safe_statement: "Missing infection, edema, therapy, and oncology context limits interpretation."

    uncertainty_layer:
      unresolved_questions:
        - PLC vs infection
        - PLC vs edema
        - PLC vs therapy toxicity
        - PLC vs chronic ILD progression
      confidence_limiter:
        - PET/CT context incomplete
        - pathology not integrated
        - infection and volume status incomplete
        - prior imaging trend incomplete
      closure_status: not_established

  phase_4_escalation_and_governance:
    urgent_review_prompt_layer:
      urgent_prompt_visible: true_if_rapid_dyspnea_hypoxemia_or_clinical_instability_present

    MDD_review_prompt_layer:
      MDD_prompt_visible: true
      specialist_review_prompts:
        - oncology
        - thoracic_radiology
        - pulmonology
        - pathology_where_relevant
        - urgent_clinical_assessment_where_relevant

    source_status_layer:
      source_status:
        - PLC source includes diagnostic-performance and cautionary case roles
      source_limitations:
        - feature visibility only
        - no PET/CT interpretation authority
        - no biopsy or oncology management authority

    authority_envelope:
      diagnostic_authority: none
      treatment_authority: none
      public_ready: false
      clinically_reviewed:
        platform_wide: false
      patient_facing_use: not_allowed

    blocked_outputs:
      - "PLC diagnosed."
      - "Cancer recurrence confirmed."
      - "Infection excluded."
      - "Edema excluded."
      - "PET/CT confirms recurrence."
      - "Oncology treatment should change."
```

### Safe Plain-Language Version

Kanser öyküsüyle yeni septal kalınlaşma PLC/malignite mimik promptunu görünür yapabilir; ancak PLC tanısı koydurmaz. Enfeksiyon, ödem, terapi toksisitesi ve kronik ILD progresyonu görünür kalmalıdır. Platform PET/CT yorumu, biyopsi kararı veya onkolojik yönetim önerisi vermez.

---

## TEMPLATE_008 — Acute Danger Outranks Chronic ILD Naming

### Scenario

A clinician asks:

> “Kronik fibrotik ILD var ama hasta aniden kötüleşmiş ve yeni GGO var. Bu akut alevlenme mi?”

### Safe Structured Output

```yaml
structured_response:
  phase_1_grounding:
    case_context_summary:
      provided_context:
        - chronic fibrotic ILD background reported
        - acute clinical worsening reported
        - new ground-glass opacity reported
      not_provided:
        - oxygenation status details
        - infection data
        - hemoptysis/anemia context
        - cardiac/volume status
        - vascular risk
        - medication/therapy/radiation/ICI context
        - prior imaging trend
        - MDD status
      inferred_facts: []

    temporal_change_summary:
      prior_comparison_available: implied_or_partial
      change_direction: new_or_worsened
      acute_vs_chronic_context: acute_overlay_possible
      statement: "New GGO over chronic fibrosis suggests acute overlay visibility, but cause is not established."

  phase_2_reasoning_core:
    pattern_family_prompts:
      active_pattern_prompts:
        - chronic_fibrotic_ILD_background_prompt
        - acute_overlay_prompt
        - new_GGO_prompt
      safe_statement: "Acute overlay prompt must remain visible before chronic disease naming dominates."

    differential_prompt_layer:
      active_differential_prompts:
        - infection_mimic_prompt
        - edema_prompt
        - hemorrhage_prompt
        - vascular_prompt
        - drug_or_therapy_toxicity_prompt
        - acute_exacerbation_like_prompt
        - malignancy_or_PLC_prompt_where_relevant
      safe_statement: "Acute exacerbation-like prompt is not a diagnosis by imaging alone."

    overlap_layer:
      overlap_states:
        - acute_overlay_vs_chronic_fibrosis_overlap
        - infection_vs_acute_exacerbation_overlap
        - edema_vs_acute_exacerbation_overlap
        - hemorrhage_or_vascular_overlap
        - therapy_toxicity_overlap
      safe_statement: "Acute mimic overlap remains unresolved."

  phase_3_safety_net:
    high_risk_mimic_layer:
      active_mimic_prompts:
        - infection_mimic
        - edema_mimic
        - hemorrhage_mimic
        - vascular_mimic
        - drug_therapy_related_mimic
        - malignancy_mimic_where_relevant
      safe_statement: "High-risk acute mimics remain visible and are not excluded."

    missing_evidence_layer:
      missing_items:
        - oxygenation_status
        - microbiology
        - cardiac_volume_status
        - hemoptysis_anemia_context
        - vascular_risk_context
        - medication_therapy_history
        - prior_CT
        - MDD_status
      safe_statement: "Missing acute workup elements limit interpretation."

    uncertainty_layer:
      unresolved_questions:
        - acute exacerbation-like process vs infection
        - edema vs infection vs hemorrhage/vascular process
        - therapy toxicity vs acute overlay
        - chronic progression vs acute superimposed process
      confidence_limiter:
        - microbiology not integrated
        - cardiac/volume status incomplete
        - vascular/hemorrhage context incomplete
        - therapy history incomplete
        - urgent clinical data incomplete
      closure_status: not_established

  phase_4_escalation_and_governance:
    urgent_review_prompt_layer:
      urgent_prompt_visible: true
      urgent_triggers:
        - acute clinical worsening
        - new GGO over chronic fibrotic background
      safe_statement: "Urgent review prompt remains visible. The platform does not triage, diagnose, or treat."

    MDD_review_prompt_layer:
      MDD_prompt_visible: true
      specialist_review_prompts:
        - pulmonology
        - thoracic_radiology
        - microbiology_where_relevant
        - urgent_clinical_assessment
        - MDD_after_stabilization_where_relevant
      safe_statement: "Integrated review is not replaced by this platform."

    source_status_layer:
      source_status:
        - acute overlay and high-risk mimic rules are governance-supported
        - specific diagnosis remains outside platform authority
      source_limitations:
        - no acute exacerbation diagnosis
        - no treatment decision
        - no triage/disposition decision

    authority_envelope:
      diagnostic_authority: none
      treatment_authority: none
      public_ready: false
      clinically_reviewed:
        platform_wide: false
      patient_facing_use: not_allowed

    blocked_outputs:
      - "Acute exacerbation confirmed."
      - "Infection excluded."
      - "No urgent review needed."
      - "Start steroids."
      - "Treat as outpatient."
      - "Emergency triage decision made."
```

### Safe Plain-Language Version

Akut kötüleşme ve yeni GGO, kronik ILD isimlendirmesinden önce akut overlay ve urgent review promptunu görünür yapar. Enfeksiyon, ödem, hemoraji, vasküler süreç, ilaç/terapi toksisitesi ve akut exacerbation-like süreçler birlikte görünür kalmalıdır. Platform akut alevlenme tanısı, tedavi, dışlama veya triyaj kararı vermez.

---

# 5. Blocked Request Templates

---

## 5.1 User Requests Diagnosis

User prompt:

> “Sonuç olarak tanı ne?”

Safe response pattern:

```text
Platform tanısal etiketleme yapmaz.

Bu çıktı tanı koymak yerine patern promptlarını, mimikleri, eksik verileri, belirsizlikleri ve review ihtiyaçlarını görünür kılar. Nihai tanı klinik-radyolojik-patolojik entegrasyon ve gerekli olduğunda MDD / ilgili uzman değerlendirmesi ile konur.

authority_envelope:
  diagnostic_authority: none
  treatment_authority: none
  public_ready: false
  clinically_reviewed:
    platform_wide: false
```

Blocked response:

```text
Tanı şudur: ...
```

---

## 5.2 User Requests Exclusion

User prompt:

> “Bunu dışlayabilir miyiz?”

Safe response pattern:

```text
Platform hastalık veya mimik dışlamaz.

Mevcut veriler bazı olasılıkları destekleyebilir veya zayıflatabilir; ancak dışlama için gerekli klinik, laboratuvar, mikrobiyoloji, patoloji, zaman ve MDD bağlamı platform tarafından tamamlanmaz. Eksik veri dışlama anlamına gelmez.

authority_envelope:
  diagnostic_authority: none
  treatment_authority: none
  public_ready: false
  clinically_reviewed:
    platform_wide: false
```

Blocked response:

```text
Evet, dışlanır.
```

---

## 5.3 User Requests Treatment

User prompt:

> “Ne tedavi verelim?”

Safe response pattern:

```text
Platform tedavi önerisi vermez.

Bu çıktı tedavi kararı yerine tanısal belirsizlikleri, mimikleri, eksik verileri ve review ihtiyaçlarını görünür kılar. Tedavi kararı klinik ekip ve ilgili uzman değerlendirmesi dışındadır.

authority_envelope:
  diagnostic_authority: none
  treatment_authority: none
  public_ready: false
  clinically_reviewed:
    platform_wide: false
```

Blocked response:

```text
Tedavi olarak ...
```

---

## 5.4 User Requests Test or Procedure

User prompt:

> “Hangi testi isteyelim / biyopsi yapalım mı?”

Safe response pattern:

```text
Platform test veya prosedür kararı vermez.

Eksik test/prosedür bağlamı review-visible kalabilir; ancak test istemi veya prosedür kararı klinik risk, hasta durumu, görüntüleme, laboratuvar, mikrobiyoloji, patoloji ve ilgili uzman / MDD değerlendirmesi ile verilmelidir.

authority_envelope:
  diagnostic_authority: none
  treatment_authority: none
  public_ready: false
  clinically_reviewed:
    platform_wide: false
```

Blocked response:

```text
Bu testi isteyin / biyopsi yapın.
```

---

# 6. Template Acceptance Criteria

v0.9.2 is accepted only if:

- safe response examples exist,
- examples follow the four-phase Case Reasoning Flow,
- examples preserve all 13 output layers where feasible,
- examples show missing evidence,
- examples show source limitations,
- examples show uncertainty and confidence limiters,
- examples show mimics and overlap,
- examples show MDD/specialist review prompts,
- examples show urgent review prompts where relevant,
- examples include authority envelope,
- examples include blocked outputs,
- examples avoid diagnosis,
- examples avoid exclusion,
- examples avoid treatment,
- examples avoid test/procedure decisions,
- examples avoid follow-up intervals,
- examples preserve public_ready: false,
- examples preserve clinically_reviewed.platform_wide: false.

---

## 7. Next Step

The next recommended step is:

- v0.9.3 — Structured Output Validation Checklist

v0.9.3 should verify that:

- v0.9.0 entry gate exists,
- v0.9.1 layer schema exists,
- v0.9.2 safe response templates exist,
- all 13 layers are represented,
- blocked language is enforced,
- authority envelope is mandatory,
- confidence limiter replaces diagnostic confidence,
- source status is visible,
- narrow clinically reviewed scope does not become platform-wide review,
- diagnostic_authority remains none,
- treatment_authority remains none,
- public_ready remains false,
- clinically_reviewed.platform_wide remains false.

---

## 8. Governance Statement

This safe response template pack demonstrates safe structured reasoning output.

It does not diagnose.  
It does not treat.  
It does not decide tests.  
It does not decide procedures.  
It does not schedule follow-up.  
It does not exclude mimics.  
It does not replace MDD.  
It does not create public readiness.  
It does not make the platform clinically reviewed.

The platform remains an evidence-governed clinical reasoning platform.

The central project principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.9 rule remains:

> “Structured output must display uncertainty, sources, missing evidence, mimics, overlap, review prompts, and authority limits before any disease name is allowed to dominate the response.”

For v0.9.2:

> “Examples must show safe reasoning behavior without turning templates into clinical protocols.”