# ILD Reasoning Platform — Reasoning Map / Guided Visual Reasoning Interaction Contract v1

Version: v0.15.3  
Status: reasoning_map_guided_visual_reasoning_interaction_contract  
Scope: Reasoning map node taxonomy, edge semantics, visual hierarchy, non-probabilistic state display, missing evidence node behavior, mimic visibility node behavior, overlap node behavior, source status node behavior, confidence limiter node behavior, review prompt node behavior, authority envelope node behavior, no-decision node behavior, blocked visual ranking behavior, blocked diagnostic closure behavior, and audit trace hooks for node expansion and navigation  
Public Ready: false  
Product Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  
Patient-Facing Use: not_allowed  

---

## 1. Purpose

This document defines v0.15.3 — Reasoning Map / Guided Visual Reasoning Interaction Contract.

v0.15.3 defines how the prototype workspace may display a reasoning map for sealed synthetic demo cases.

The reasoning map is a guided visual reasoning surface.

It is not a diagnostic graph.  
It is not a probability graph.  
It is not a disease ranking graph.  
It is not a treatment pathway.  
It is not a test-ordering pathway.  
It is not a procedure-decision pathway.  
It is not a follow-up pathway.  
It is not a triage pathway.  
It is not a patient-facing explanation.  
It is not clinical validation.  
It is not product readiness.  
It is not public readiness.

This document does not add new clinical content.

It does not diagnose.  
It does not treat.  
It does not decide tests.  
It does not decide procedures.  
It does not schedule follow-up.  
It does not triage.  
It does not exclude mimics.  
It does not replace MDD.  
It does not create public readiness.  
It does not create product readiness.  
It does not make the platform clinically reviewed.  
It does not create patient-facing use.  
It does not use real patient data.  
It does not ingest deidentified real patient data.  
It does not import DICOM.  
It does not import real clinical reports.  
It does not perform clinical validation.  
It does not prove diagnostic performance.  
It does not create a deployed clinical workflow.

Its purpose is to define how a synthetic reasoning state may be visually navigated without becoming diagnosis, recommendation, ranking, probability, proof, or action.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.15.3 map principle is:

> “A reasoning map may guide attention, but only text-governed safety language may define meaning.”

---

## 2. Relationship to Prior v0.15 Steps

v0.15.3 inherits:

- v0.15.0 — Prototype Workspace / Demo UI Behavior Contract Entry Gate,
- v0.15.1 — Demo Workspace Screen / Component Behavior Schema,
- v0.15.2 — Demo Case Selection / Synthetic Intake UI Flow.

v0.15.0 opened the prototype workspace UI behavior boundary.

v0.15.1 defined screens and components.

v0.15.2 defined safe synthetic selection and intake flow.

v0.15.3 defines the guided visual reasoning map that appears after safe synthetic fixture binding and synthetic intake review.

v0.15.3 does not broaden prior steps.

v0.15.3 must not open:

- real patient data,
- deidentified real patient data,
- real clinical intake,
- DICOM import,
- real report import,
- diagnosis generation,
- disease ranking,
- disease exclusion,
- treatment recommendation,
- test ordering,
- procedure recommendation,
- follow-up scheduling,
- triage,
- patient-facing output,
- public-ready output,
- product-ready output,
- clinical validation,
- diagnostic performance measurement,
- MDD replacement.

Map inheritance rule:

> A reasoning map may visualize sealed reasoning state, but it may not create new clinical authority.

---

## 3. Global Authority Envelope

Every map state, node, edge, label, tooltip, expansion, filter, highlight, disabled control, and audit event must inherit the following authority envelope.

```yaml
authority_envelope:
  diagnostic_authority: none
  treatment_authority: none
  test_order_authority: none
  procedure_decision_authority: none
  follow_up_authority: none
  triage_authority: none
  patient_facing_use: not_allowed
  public_ready: false
  product_ready: false
  clinically_reviewed_platform_wide: false
  real_patient_data: not_allowed
  deidentified_real_patient_data: not_allowed
  clinical_validation: not_opened
  diagnostic_performance_claim: not_allowed
  mdd_replacement: not_allowed
```

No visual element may override this envelope.

Authority map rule:

> The reasoning map is non-authoritative even when it is visually structured.

---

## 4. Global No-Decision Object

The no-decision object must remain active on the reasoning map.

```yaml
no_decision_object:
  diagnosis_made: false
  disease_excluded: false
  mimic_excluded: false
  treatment_selected: false
  test_ordered: false
  procedure_decided: false
  follow_up_scheduled: false
  triage_assigned: false
  mdd_consensus_generated: false
  patient_facing_output_generated: false
```

Required display behavior:

- no-decision object node visible on map,
- no-decision object card available in side panel,
- no-decision object included in audit trace,
- no-decision object carried into safe export preview.

No-decision map rule:

> A map that shows reasoning must also show that no clinical decision was made.

---

## 5. Reasoning Map Object Schema

Every reasoning map must conform to the following schema.

```yaml
reasoning_map:
  map_id: string
  version: v0.15.3
  parent_synthetic_case_id: string
  parent_workspace_state_id: string
  prototype_only: true
  synthetic_demo_only: true
  real_patient_data_allowed: false
  deidentified_real_patient_data_allowed: false
  clinical_use_allowed: false
  patient_facing_allowed: false
  diagnostic_authority: none
  treatment_authority: none
  decision_effect: none
  visual_semantics: text_governed
  probability_display_allowed: false
  ranking_display_allowed: false
  diagnostic_closure_allowed: false
  treatment_pathway_allowed: false
  triage_pathway_allowed: false
  required_nodes: list
  optional_nodes: list
  blocked_nodes: list
  allowed_edges: list
  blocked_edges: list
  required_safety_labels: list
  required_authority_envelope: true
  required_no_decision_object: true
  required_audit_hooks: true
```

Map schema rule:

> A reasoning map is valid only if it displays relationships without probability, ranking, closure, or action.

---

## 6. Reasoning Map Node Schema

Every node must conform to the following schema.

```yaml
reasoning_map_node:
  node_id: string
  node_type: enum
  node_label: string
  node_role: enum
  data_origin: synthetic_fixture_only
  clinical_authority_effect: none
  decision_effect: none
  diagnostic_claim_allowed: false
  exclusion_claim_allowed: false
  treatment_claim_allowed: false
  order_claim_allowed: false
  visual_weight: non_authoritative
  color_semantics: non_probability
  icon_semantics: non_authority
  expansion_allowed: true
  expansion_content_type: text_governed_explanation
  required_tooltip: string
  required_audit_event_on_view: true
  required_audit_event_on_expand: true
```

Node schema rule:

> A node may represent a reasoning-state object, not a clinical conclusion.

---

## 7. Reasoning Map Edge Schema

Every edge must conform to the following schema.

```yaml
reasoning_map_edge:
  edge_id: string
  source_node_id: string
  target_node_id: string
  edge_type: enum
  edge_label: string
  relationship_meaning: text_governed
  probability_weight_allowed: false
  ranking_weight_allowed: false
  causal_proof_allowed: false
  diagnostic_proof_allowed: false
  action_trigger_allowed: false
  visual_thickness_semantics: non_probability
  visual_color_semantics: non_probability
  required_tooltip: string
  required_audit_event_on_view: true
```

Allowed edge types:

| Edge Type | Allowed Meaning |
|---|---|
| informs_visibility | One state explains why another state is visible |
| limits_interpretation | One state limits interpretation of another |
| preserves_uncertainty | One state prevents closure |
| preserves_mimic_visibility | One state keeps mimic prompt visible |
| preserves_overlap | One state keeps overlap unresolved |
| source_limits_claim | Source status limits claim strength |
| audit_links_state | Audit event explains visible state |
| authority_blocks_action | Authority envelope blocks decision behavior |
| no_decision_blocks_closure | No-decision object prevents closure semantics |

Blocked edge types:

| Blocked Edge Type | Reason |
|---|---|
| proves_diagnosis | diagram-as-proof risk |
| confirms_disease | diagnostic authority risk |
| excludes_disease | exclusion authority risk |
| ranks_probability | probability/ranking risk |
| recommends_treatment | treatment authority risk |
| orders_test | test-order authority risk |
| recommends_procedure | procedure authority risk |
| schedules_follow_up | follow-up authority risk |
| assigns_triage | triage authority risk |
| generates_mdd_consensus | MDD replacement risk |

Edge schema rule:

> Edges explain governance relationships; they do not prove, rank, or command.

---

## 8. Node Taxonomy

The following node types are allowed.

| Node Type | Role | Required / Optional |
|---|---|---|
| synthetic_case_context_node | Shows selected fictional case context | required |
| supplied_field_node | Shows fictional supplied fields | optional |
| missing_evidence_node | Shows missing evidence state | required when missing fields exist |
| temporal_limiter_node | Shows temporal comparison limitation | required when prior CT is unavailable |
| source_status_node | Shows source role and limitation | required |
| mimic_visibility_node | Shows high-risk mimic visibility | required when relevant |
| overlap_node | Shows unresolved coexistence / boundary | required when relevant |
| confidence_limiter_node | Shows why certainty remains limited | required |
| review_prompt_node | Shows review visibility prompt without action | optional |
| safe_export_preview_node | Links map state to safe export preview | optional |
| authority_envelope_node | Shows non-authority boundary | required |
| no_decision_node | Shows explicit decisions not made | required |
| audit_trace_node | Shows traceability | required |
| visual_safety_label_node | Shows visual meaning constraints | required |

The following node types are blocked.

| Blocked Node Type | Reason |
|---|---|
| final_diagnosis_node | diagnostic closure risk |
| most_likely_diagnosis_node | ranking risk |
| disease_probability_node | probability claim risk |
| rule_out_node | exclusion authority risk |
| confirmed_mimic_node | diagnostic authority risk |
| excluded_mimic_node | exclusion authority risk |
| treatment_recommendation_node | treatment authority risk |
| test_order_node | order authority risk |
| procedure_recommendation_node | procedure authority risk |
| follow_up_schedule_node | follow-up authority risk |
| triage_disposition_node | triage authority risk |
| patient_summary_node | patient-facing leak risk |
| mdd_consensus_node | MDD replacement risk |
| clinical_validation_node | validation overclaim risk |
| product_ready_node | deployment overclaim risk |
| public_ready_node | public-readiness overclaim risk |

Node taxonomy rule:

> The map may contain visibility, limitation, uncertainty, source, audit, and authority nodes; it may not contain conclusion or action nodes.

---

## 9. Visual Hierarchy Rules

The map may use hierarchy to help navigation.

Allowed hierarchy:

- central synthetic case context,
- surrounding limitation nodes,
- grouped evidence-state nodes,
- grouped mimic/overlap nodes,
- persistent authority/no-decision nodes,
- audit trace node accessible from all nodes,
- safe export preview node downstream but non-authoritative,
- visual safety label always visible or fixed.

Blocked hierarchy:

- final diagnosis at top,
- disease ranked by size,
- probability represented by position,
- color severity ladder,
- “winner” node,
- “ruled out” cluster,
- treatment path downstream of diagnosis,
- test-order path downstream of missing evidence,
- triage branch,
- patient-facing branch.

Visual hierarchy rule:

> Hierarchy may organize attention; it may not organize clinical certainty.

---

## 10. Non-Probabilistic State Display

The map may display state categories, but not probability.

Allowed state display:

```yaml
allowed_state_display:
  visible: true
  missing: true
  unresolved: true
  source_limited: true
  confidence_limited: true
  review_visible: true
  blocked: true
  audit_recorded: true
  authority_none: true
```

Blocked state display:

```yaml
blocked_state_display:
  probability_percent: false
  likelihood_score: false
  confidence_meter: false
  disease_rank: false
  heatmap_probability: false
  green_yellow_red_diagnostic_certainty: false
  confirmed_badge: false
  ruled_out_badge: false
  recommended_action_badge: false
```

Non-probabilistic display rule:

> The map may show state, but it may not show likelihood.

---

## 11. Missing Evidence Node Behavior

Missing evidence nodes must preserve missingness.

Required missing evidence node behavior:

```yaml
missing_evidence_node:
  node_type: missing_evidence_node
  allowed_labels:
    - "Missing evidence"
    - "Not provided"
    - "Interpretation limited"
  required_disclaimer: "Missing evidence limits interpretation; it does not exclude disease."
  expansion_content:
    - missing_field_name
    - why_missing_matters
    - related_visibility_state
    - related_source_limitation
    - audit_event_reference
  blocked_labels:
    - "Negative"
    - "Absent"
    - "Ruled out"
    - "No evidence of"
    - "Excluded"
```

Missing evidence node may connect to:

- mimic visibility node,
- overlap node,
- confidence limiter node,
- source status node,
- review prompt node,
- audit trace node.

Missing evidence node may not connect to:

- diagnosis node,
- exclusion node,
- treatment node,
- test order node,
- follow-up node,
- triage node.

Missing evidence node rule:

> Missing evidence remains a limiter, not a negative finding.

---

## 12. Mimic Visibility Node Behavior

Mimic visibility nodes must preserve high-risk mimic visibility without diagnosis or exclusion.

Required mimic visibility node behavior:

```yaml
mimic_visibility_node:
  node_type: mimic_visibility_node
  allowed_labels:
    - "Mimic visibility preserved"
    - "High-risk mimic prompt visible"
    - "Source-limited mimic review prompt"
  required_disclaimer: "Mimic visibility is a safety prompt, not a diagnosis or exclusion list."
  expansion_content:
    - mimic_family_name
    - visibility_reason
    - source_status_dependency
    - missing_evidence_dependency
    - overlap_dependency
    - audit_event_reference
  blocked_labels:
    - "Confirmed mimic"
    - "Excluded mimic"
    - "Most likely mimic"
    - "Mimic probability"
    - "Mimic ruled out"
```

Mimic visibility node may connect to:

- missing evidence node,
- source status node,
- overlap node,
- confidence limiter node,
- review prompt node,
- audit trace node.

Mimic visibility node may not connect to:

- final diagnosis node,
- probability node,
- treatment node,
- procedure node,
- triage node.

Mimic visibility node rule:

> Mimic visibility keeps risk visible; it does not name or dismiss disease.

---

## 13. Overlap Node Behavior

Overlap nodes must preserve unresolved coexistence and boundary uncertainty.

Required overlap node behavior:

```yaml
overlap_node:
  node_type: overlap_node
  allowed_labels:
    - "Overlap unresolved"
    - "Boundary not collapsed"
    - "Coexisting processes remain visible"
  required_disclaimer: "Overlap remains unresolved until human clinical review outside the platform."
  expansion_content:
    - overlap_reason
    - unresolved_boundary
    - source_limitation
    - missing_evidence_dependency
    - audit_event_reference
  blocked_labels:
    - "Winner selected"
    - "Primary diagnosis selected"
    - "Secondary diagnosis excluded"
    - "Dominant disease confirmed"
    - "Final choice"
```

Overlap node may connect to:

- mimic visibility node,
- missing evidence node,
- source status node,
- confidence limiter node,
- review prompt node,
- audit trace node.

Overlap node may not connect to:

- disease winner node,
- diagnosis ranking node,
- treatment pathway node,
- order pathway node,
- triage pathway node.

Overlap node rule:

> Overlap is a protected uncertainty state, not a selection problem.

---

## 14. Source Status Node Behavior

Source status nodes must preserve source role and limitation.

Required source status node behavior:

```yaml
source_status_node:
  node_type: source_status_node
  allowed_labels:
    - "Source status"
    - "Source role"
    - "Source limitation"
    - "Source-limited prompt"
  required_disclaimer: "Source status supports visibility and limitation; it does not grant clinical authority."
  expansion_content:
    - source_role
    - source_status
    - claim_scope
    - limitation_text
    - source_to_claim_mapping_reference
    - audit_event_reference
  blocked_labels:
    - "Source confirms diagnosis"
    - "Source validates platform"
    - "Source proves correctness"
    - "Source authorizes action"
    - "Source establishes probability"
```

Source status node may connect to:

- missing evidence node,
- mimic visibility node,
- overlap node,
- confidence limiter node,
- review prompt node,
- audit trace node.

Source status node may not connect to:

- authority granting node,
- diagnosis confirmation node,
- clinical validation node,
- product readiness node.

Source status node rule:

> Source status anchors limitations; it does not create authority.

---

## 15. Confidence Limiter Node Behavior

Confidence limiter nodes must explain limitation without estimating probability.

Required confidence limiter behavior:

```yaml
confidence_limiter_node:
  node_type: confidence_limiter_node
  allowed_labels:
    - "Confidence limited"
    - "Interpretation limited"
    - "Reasoning remains bounded"
  required_disclaimer: "This limiter does not estimate diagnostic probability."
  expansion_content:
    - limitation_reason
    - missing_evidence_dependency
    - source_status_dependency
    - temporal_dependency
    - overlap_dependency
    - audit_event_reference
  blocked_labels:
    - "Confidence score"
    - "Probability"
    - "Likelihood"
    - "Accuracy"
    - "Diagnostic confidence"
    - "High certainty"
```

Confidence limiter node may connect to:

- missing evidence node,
- source status node,
- overlap node,
- temporal limiter node,
- review prompt node,
- audit trace node.

Confidence limiter node may not connect to:

- probability node,
- diagnostic performance node,
- validation node,
- disease ranking node.

Confidence limiter node rule:

> A limiter explains why certainty is constrained; it does not quantify certainty.

---

## 16. Review Prompt Node Behavior

Review prompt nodes must preserve review visibility without action authority.

Required review prompt behavior:

```yaml
review_prompt_node:
  node_type: review_prompt_node
  allowed_labels:
    - "Review prompt visible"
    - "MDD preparation prompt"
    - "Specialist review visibility"
    - "Urgent review visibility"
  required_disclaimer: "Review prompt visibility is not an order, recommendation, triage decision, or procedure decision."
  expansion_content:
    - prompt_reason
    - related_missing_evidence
    - related_source_status
    - related_mimic_or_overlap_state
    - authority_boundary
    - audit_event_reference
  blocked_labels:
    - "Order required"
    - "Procedure required"
    - "Follow-up due"
    - "Triage decision"
    - "Safe for outpatient care"
    - "MDD consensus"
```

Review prompt node may connect to:

- missing evidence node,
- source status node,
- mimic visibility node,
- overlap node,
- confidence limiter node,
- safe export preview node,
- audit trace node.

Review prompt node may not connect to:

- order workflow,
- procedure workflow,
- follow-up scheduler,
- triage workflow,
- treatment pathway.

Review prompt node rule:

> A prompt can preserve human review visibility; it cannot command action.

---

## 17. Authority Envelope Node Behavior

Authority envelope nodes must remain persistent.

Required authority envelope node behavior:

```yaml
authority_envelope_node:
  node_type: authority_envelope_node
  required_label: "Authority envelope"
  required_disclaimer: "The platform has no diagnostic, treatment, order, procedure, follow-up, triage, patient-facing, public-ready, product-ready, or clinical-validation authority."
  required_fields:
    - diagnostic_authority: none
    - treatment_authority: none
    - test_order_authority: none
    - procedure_decision_authority: none
    - follow_up_authority: none
    - triage_authority: none
    - patient_facing_use: not_allowed
    - public_ready: false
    - product_ready: false
    - clinical_validation: not_opened
```

Blocked authority behavior:

- authority node hidden,
- authority node collapsed without warning,
- authority node replaced by icon only,
- authority node contradicted by action nodes,
- authority node omitted from export preview.

Authority envelope node rule:

> The map must show lack of authority as a first-class state.

---

## 18. No-Decision Node Behavior

No-decision nodes must explicitly show decisions not made.

Required no-decision node behavior:

```yaml
no_decision_node:
  node_type: no_decision_node
  required_label: "No decision made"
  required_fields:
    diagnosis_made: false
    disease_excluded: false
    mimic_excluded: false
    treatment_selected: false
    test_ordered: false
    procedure_decided: false
    follow_up_scheduled: false
    triage_assigned: false
    mdd_consensus_generated: false
    patient_facing_output_generated: false
  required_disclaimer: "The reasoning map displays governed state only; it does not make clinical decisions."
```

Blocked no-decision behavior:

- no-decision node absent,
- no-decision node hidden behind diagnosis-like content,
- no-decision node contradicted by recommendation labels,
- any no-decision field set to true,
- no-decision node omitted from audit trace.

No-decision node rule:

> The map must display decisions not made with the same clarity as visible reasoning states.

---

## 19. Audit Trace Node Behavior

Audit trace nodes must explain state movement without claiming correctness.

Required audit trace node behavior:

```yaml
audit_trace_node:
  node_type: audit_trace_node
  allowed_labels:
    - "Audit trace"
    - "State trace"
    - "Visibility trace"
  required_disclaimer: "Audit trace explains UI state; it does not prove medical correctness."
  expansion_content:
    - event_id
    - event_type
    - source_node
    - target_node
    - reason_displayed
    - authority_effect: none
    - decision_effect: none
```

Allowed audit events:

- reasoning_map_viewed,
- node_viewed,
- node_expanded,
- node_collapsed,
- edge_viewed,
- missing_evidence_node_viewed,
- mimic_visibility_node_viewed,
- overlap_node_viewed,
- source_status_node_viewed,
- confidence_limiter_node_viewed,
- review_prompt_node_viewed,
- authority_envelope_node_viewed,
- no_decision_node_viewed,
- unsafe_map_state_blocked.

Blocked audit meanings:

- diagnosis validated,
- disease excluded,
- clinical correctness proven,
- diagnostic performance measured,
- treatment authorized,
- test ordered,
- procedure recommended,
- follow-up scheduled,
- triage completed,
- MDD consensus achieved.

Audit trace node rule:

> Audit trace shows why the map looks the way it does, not whether medicine is correct.

---

## 20. Visual Safety Label Node Behavior

The visual safety label must remain visible or persistently accessible.

Required visual safety label:

```yaml
visual_safety_label_node:
  node_type: visual_safety_label_node
  required_label: "Visual safety"
  required_fields:
    visual_is_not_diagnosis: true
    diagram_is_not_proof: true
    color_is_not_probability: true
    icon_is_not_authority: true
    flow_is_not_treatment_pathway: true
    text_governs_visual_meaning: true
    synthetic_demo_only: true
    not_patient_facing: true
```

Blocked visual safety behavior:

- safety label hidden,
- safety label only in documentation,
- safety label omitted from reasoning map,
- color used without meaning disclaimer,
- icon used without authority disclaimer,
- flow used without pathway disclaimer.

Visual safety node rule:

> The map must warn the user how not to read the map.

---

## 21. Interaction Behavior

Allowed interactions:

| Interaction | Allowed Meaning |
|---|---|
| view_map | Display synthetic reasoning map |
| pan_map | Navigate visual space |
| zoom_map | Improve readability |
| expand_node | Read text-governed explanation |
| collapse_node | Hide expanded explanation |
| view_edge_tooltip | Read relationship explanation |
| highlight_related_nodes | Temporarily show related governance states |
| filter_by_state_type | Show selected visibility/limitation class |
| inspect_audit_event | Read trace event |
| return_to_intake_review | Navigate backward safely |
| proceed_to_evidence_panel | Open related safe evidence panel |
| proceed_to_safe_export_preview | Open non-diagnostic export preview |

Blocked interactions:

| Blocked Interaction | Reason |
|---|---|
| drag_node_to_rank | visual ranking risk |
| resize_node_by_likelihood | probability risk |
| mark_node_confirmed | diagnostic authority risk |
| mark_node_ruled_out | exclusion authority risk |
| convert_node_to_action | treatment/order/procedure risk |
| generate_diagnosis_from_map | diagnostic authority risk |
| generate_treatment_from_map | treatment authority risk |
| export_map_as_patient_summary | patient-facing leak risk |
| publish_map_publicly | public-readiness risk |
| mark_map_clinically_validated | validation overclaim risk |

Interaction rule:

> Map interactions may reveal explanation; they may not change clinical meaning.

---

## 22. Highlighting and Focus Rules

The map may use highlight states for attention only.

Allowed highlight states:

```yaml
allowed_highlight_states:
  selected_node: neutral_focus
  related_limitation: neutral_focus
  related_missing_evidence: neutral_focus
  related_source_status: neutral_focus
  related_mimic_visibility: neutral_focus
  related_overlap: neutral_focus
  blocked_unsafe_state: fail_closed_focus
```

Blocked highlight states:

```yaml
blocked_highlight_states:
  highest_probability: false
  most_likely_diagnosis: false
  confirmed_disease: false
  ruled_out_disease: false
  recommended_action: false
  urgency_triage_level: false
  treatment_path_priority: false
```

Highlight rule:

> Highlighting may guide attention, not clinical priority.

---

## 23. Color Rules

Colors may be used only for neutral UI state, not clinical meaning.

Allowed color semantics:

| Color Use | Meaning |
|---|---|
| neutral selected state | User selected a node |
| neutral hover state | User hovered over a node |
| disabled grey state | Control unavailable |
| fail-closed warning state | Unsafe UI action blocked |
| source-limited state | Source limitation visible |
| missing-state marker | Missing evidence visible |

Blocked color semantics:

| Blocked Color Use | Reason |
|---|---|
| green = diagnosis likely | probability risk |
| red = diagnosis severe | severity/triage risk |
| yellow = intermediate probability | probability risk |
| color gradient = likelihood | ranking risk |
| color intensity = confidence | confidence score risk |
| color = treatment priority | treatment authority risk |
| color = triage level | triage authority risk |

Color rule:

> Color may show UI state; it may not show probability, severity, confidence, or action priority.

---

## 24. Icon Rules

Icons may be used only as navigational aids.

Allowed icon semantics:

- information,
- missing evidence,
- source status,
- audit trace,
- authority boundary,
- no-decision object,
- visual safety warning,
- fail-closed state.

Blocked icon semantics:

- confirmed diagnosis icon,
- ruled-out disease icon,
- recommended treatment icon,
- order test icon,
- procedure required icon,
- follow-up due icon,
- triage status icon,
- patient-safe icon,
- clinically validated icon,
- product-ready icon.

Icon rule:

> Icons may help find content; they may not confer authority.

---

## 25. Edge Visual Rules

Edges may show relationship type, not strength of clinical likelihood.

Allowed edge visual behavior:

- same thickness for all relationship edges,
- dashed edge for limitation relationship,
- neutral edge for visibility relationship,
- blocked edge marker for unsafe relationship,
- tooltip explains relationship in text,
- no edge weight values.

Blocked edge visual behavior:

- thicker edge means more likely,
- darker edge means stronger diagnosis,
- edge number means probability,
- edge arrow means clinical action,
- edge cluster means ranked diagnosis,
- edge color means severity,
- edge animation means urgency.

Edge visual rule:

> Edge visuals may show relationship category, not clinical strength.

---

## 26. Blocked Visual Ranking Behavior

The map must block visual ranking.

Blocked ranking behavior:

```yaml
blocked_visual_ranking:
  disease_rank_list: false
  largest_node_as_most_likely: false
  highest_node_as_best_match: false
  closest_node_as_primary_diagnosis: false
  edge_weight_as_probability: false
  color_intensity_as_confidence: false
  node_order_as_recommendation: false
  left_to_right_as_treatment_sequence: false
```

Required blocked-state message:

```text
Visual ranking is not allowed. The prototype reasoning map shows governed visibility and limitation states only. It does not rank diagnoses, estimate probability, or recommend clinical action.
```

Visual ranking rule:

> The map must not let layout become diagnosis.

---

## 27. Blocked Diagnostic Closure Behavior

The map must block diagnostic closure.

Blocked diagnostic closure behavior:

```yaml
blocked_diagnostic_closure:
  final_diagnosis_label: false
  diagnosis_confirmed_badge: false
  most_likely_diagnosis_badge: false
  disease_ruled_out_badge: false
  mimic_excluded_badge: false
  diagnostic_summary_card: false
  impression_heading: false
  conclusion_heading_as_diagnosis: false
  diagnostic_export_from_map: false
```

Required blocked-state message:

```text
Diagnostic closure is not allowed. This reasoning map is a synthetic, non-clinical prototype visibility surface and does not produce diagnosis, exclusion, treatment, orders, procedures, follow-up, triage, or MDD consensus.
```

Diagnostic closure rule:

> The map may open reasoning visibility; it may not close the case.

---

## 28. Map-to-Panel Navigation

The map may link to safe panels only.

Allowed map-to-panel navigation:

| Map Node | Allowed Destination |
|---|---|
| missing_evidence_node | Missing Evidence Panel |
| mimic_visibility_node | Mimic Visibility Panel |
| overlap_node | Overlap Panel |
| source_status_node | Source Status Panel |
| confidence_limiter_node | Confidence Limiter Panel |
| review_prompt_node | Review Prompt Panel |
| authority_envelope_node | Authority Envelope Display |
| no_decision_node | No-Decision Object Display |
| audit_trace_node | Audit Trace Screen |
| safe_export_preview_node | Safe Export Preview Screen |

Blocked map-to-panel navigation:

| Map Node | Blocked Destination |
|---|---|
| any node | Diagnosis Screen |
| any node | Disease Ranking Dashboard |
| any node | Probability Dashboard |
| any node | Treatment Recommendation Screen |
| any node | Test Ordering Screen |
| any node | Procedure Recommendation Screen |
| any node | Follow-Up Scheduler |
| any node | Triage Screen |
| any node | Patient-Facing Summary |
| any node | Clinical Validation Dashboard |
| any node | Product Readiness Dashboard |

Map-to-panel rule:

> Map navigation may deepen safe visibility; it may not escalate to clinical workflow.

---

## 29. Map Fail-Closed Conditions

The reasoning map must fail closed under the following conditions.

```yaml
map_fail_closed_conditions:
  authority_envelope_missing:
    map_display_allowed: false
    repair_required: true
    audit_required: true
  no_decision_object_missing:
    map_display_allowed: false
    repair_required: true
    audit_required: true
  visual_safety_label_missing:
    map_display_allowed: false
    repair_required: true
    audit_required: true
  real_patient_data_detected:
    map_display_allowed: false
    workspace_allowed: false
    audit_required: true
  deidentified_real_patient_data_detected:
    map_display_allowed: false
    workspace_allowed: false
    audit_required: true
  probability_node_detected:
    map_display_allowed: false
    repair_required: true
    audit_required: true
  diagnosis_node_detected:
    map_display_allowed: false
    repair_required: true
    audit_required: true
  treatment_or_action_node_detected:
    map_display_allowed: false
    repair_required: true
    audit_required: true
  patient_facing_node_detected:
    map_display_allowed: false
    repair_required: true
    audit_required: true
```

Map fail-closed rule:

> A map that cannot preserve non-authority must not render.

---

## 30. Audit Hooks for Map Interaction

Every meaningful map interaction must emit an audit event.

Required audit event schema:

```yaml
reasoning_map_audit_event:
  event_id: string
  event_type: enum
  timestamp_or_sequence_id: string
  map_id: string
  node_id: optional
  edge_id: optional
  user_action: string
  authority_effect: none
  decision_effect: none
  correctness_claim: false
  clinical_validation_effect: none
  product_readiness_effect: none
```

Required audit event types:

| Event Type | Trigger |
|---|---|
| reasoning_map_opened | Map rendered |
| map_safety_labels_checked | Required labels verified |
| node_viewed | Node entered viewport or selected |
| node_expanded | User expanded node |
| node_collapsed | User collapsed node |
| edge_tooltip_viewed | User viewed edge explanation |
| related_nodes_highlighted | User highlighted related safe states |
| safe_panel_navigation_clicked | User moved to allowed panel |
| unsafe_node_blocked | Blocked node detected |
| unsafe_edge_blocked | Blocked edge detected |
| visual_ranking_attempt_blocked | Ranking attempt blocked |
| diagnostic_closure_attempt_blocked | Closure attempt blocked |
| map_fail_closed_triggered | Map stopped rendering due to unsafe state |

Audit hook rule:

> The map records visibility and safety behavior, not clinical correctness.

---

## 31. Map Acceptance Criteria

v0.15.3 may be considered complete only if all of the following are true.

| Criterion | Required State |
|---|---|
| reasoning map object schema defined | true |
| node schema defined | true |
| edge schema defined | true |
| node taxonomy defined | true |
| blocked node taxonomy defined | true |
| visual hierarchy rules defined | true |
| non-probabilistic state display defined | true |
| missing evidence node behavior defined | true |
| mimic visibility node behavior defined | true |
| overlap node behavior defined | true |
| source status node behavior defined | true |
| confidence limiter node behavior defined | true |
| review prompt node behavior defined | true |
| authority envelope node behavior defined | true |
| no-decision node behavior defined | true |
| audit trace node behavior defined | true |
| visual safety label node behavior defined | true |
| interaction behavior defined | true |
| highlight/focus rules defined | true |
| color rules defined | true |
| icon rules defined | true |
| edge visual rules defined | true |
| visual ranking behavior blocked | true |
| diagnostic closure behavior blocked | true |
| map-to-panel navigation constrained | true |
| map fail-closed conditions defined | true |
| audit hooks for map interaction defined | true |
| real patient data remains blocked | true |
| deidentified real patient data remains blocked | true |
| clinical validation remains blocked | true |
| diagnostic performance claim remains blocked | true |
| product readiness remains false | true |
| public readiness remains false | true |
| patient-facing use remains not_allowed | true |
| diagnostic authority remains none | true |
| treatment authority remains none | true |
| order/procedure/follow-up/triage authority remains none | true |
| MDD replacement remains blocked | true |

v0.15.3 acceptance rule:

> The reasoning map is accepted only if it guides visual attention without becoming probability, proof, diagnosis, recommendation, or action.

---

## 32. Next Step

The next recommended step is:

- v0.15.4 — Demo Export Preview / Red-Team Fail-Closed UI Behavior

v0.15.4 should define:

- safe export preview screen behavior,
- export preview section ordering,
- blocked unsafe headings in UI preview,
- blocked diagnosis/exclusion/action language in preview,
- red-team unsafe phrase display rules,
- fail-closed modal behavior,
- repair-required UI behavior,
- revalidation-required UI behavior,
- unsafe copy/export block,
- authority envelope and no-decision object in export preview,
- audit trace hooks for blocked export preview states.

v0.15.4 must not open clinical deployment, real patient data, public readiness, product readiness, patient-facing use, clinical validation, diagnostic authority, treatment authority, test ordering, procedure decision, follow-up scheduling, triage, or MDD replacement.

---

## 33. Governance Statement

This document defines the reasoning map and guided visual reasoning interaction contract for the prototype workspace.

It does not diagnose.  
It does not treat.  
It does not validate clinical performance.  
It does not decide tests.  
It does not decide procedures.  
It does not schedule follow-up.  
It does not triage.  
It does not create public readiness.  
It does not create product readiness.  
It does not make the platform clinically reviewed.  
It does not create patient-facing use.  
It does not use real patient data.  
It does not ingest deidentified real patient data.  
It does not import DICOM.  
It does not import real clinical reports.  
It does not replace clinicians, radiologists, pathologists, pulmonologists, rheumatologists, microbiologists, occupational medicine review, oncology review, radiation oncology review, MDD, or urgent clinical assessment.

The platform remains an evidence-governed clinical reasoning platform.

The current project principle is:

> “It teaches clinicians to read change before naming disease.”

The v0.15.3 governance discipline is:

> “Do not let a reasoning map become diagnostic proof.”