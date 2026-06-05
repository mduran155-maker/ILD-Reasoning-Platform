# ILD Reasoning Platform — Prototype Workspace / Demo UI Behavior Contract Entry Gate v1

Version: v0.15.0  
Status: prototype_workspace_demo_ui_behavior_entry_gate  
Scope: Prototype workspace demo UI behavior, synthetic demo-only case selection, non-clinical UI boundaries, visually guided but text-governed interaction, safe prototype screens, blocked prototype screens, safe export preview, authority envelope display, no-decision object display, audit trace display, and prototype readiness boundaries  
Public Ready: false  
Product Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  
Patient-Facing Use: not_allowed  

---

## 1. Purpose

This document opens v0.15 — Prototype Workspace / Demo UI Behavior Contract.

v0.15 defines how the sealed synthetic demo architecture may be connected to a prototype workspace interface for demonstration of UI behavior only.

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
It does not perform clinical validation.  
It does not prove diagnostic performance.  
It does not create a deployed clinical workflow.

Its purpose is to define the entry gate for a prototype workspace that can demonstrate previously sealed governance behavior through safe UI interaction.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.14 sealed principle remains:

> “A demo case may demonstrate governance behavior, but it must not demonstrate clinical validation, product readiness, real patient use, diagnosis, treatment, order, procedure decision, follow-up schedule, triage, public-ready output, or patient-facing use.”

The v0.15 entry principle is:

> “A prototype workspace may demonstrate UI behavior, but it must not become clinical deployment, product readiness, real patient use, diagnosis, treatment, order, procedure decision, follow-up schedule, triage, public-ready output, patient-facing use, or platform-wide clinical review.”

---

## 2. Relationship to Prior Seals

v0.15 inherits:

- v0.3 Superimposed Events Core,
- v0.4 Evidence Layer / Source Review Governance,
- v0.5 Test Case Coverage Expansion,
- v0.6 UIP Parity Upgrade,
- v0.6.R1/R2/R3 source debt and source-status correction,
- v0.7 Non-UIP Fibrotic ILD Differential Reasoning Structural Seal,
- v0.8 High-Risk Mimic Source-Limited Prompt Visibility Structural Seal,
- v0.9 Reasoning Output Contract / Structured Response Schema Structural Seal,
- v0.10 Clinician Review Workspace / Interactive Reasoning UI Contract Structural Seal,
- v0.11 Evidence Intake / Clinician-Supplied Case Context Contract Structural Seal,
- v0.12 Case Assembly / Reasoning Session Object Contract Structural Seal,
- v0.13 Safe Session Export / MDD Preparation Package Contract Structural Seal,
- v0.14 Demo Case Pack / Non-Clinical Synthetic Validation Scenario Contract Structural Seal,
- v0.14.6 Demo Illustration / Visual Artifact Safety Contract,
- checkpoint-v0.14 roadmap discipline.

v0.15 must not weaken any prior seal.

v0.15 is a prototype demo UI behavior governance phase.

It is not:

- a clinical deployment phase,
- a diagnostic phase,
- a treatment phase,
- a test-ordering phase,
- a procedure-decision phase,
- a follow-up scheduling phase,
- a triage phase,
- a real patient testing phase,
- a clinical validation phase,
- a diagnostic performance phase,
- a product-readiness phase,
- a public-readiness phase,
- a patient-facing phase,
- a regulatory certification phase,
- an MDD replacement phase.

---

## 3. v0.15 Entry Gate Scope

v0.15 may define:

- prototype workspace scope,
- synthetic demo-only case selection,
- non-clinical UI boundary,
- visually guided but text-governed interaction principle,
- allowed prototype screens,
- blocked prototype screens,
- demo intake UI boundary,
- reasoning map UI boundary,
- missing evidence panel UI boundary,
- mimic visibility panel UI boundary,
- overlap panel UI boundary,
- source status panel UI boundary,
- red-team fail-closed UI boundary,
- safe export preview UI boundary,
- visual safety label integration,
- authority envelope display requirement,
- no-decision object display requirement,
- audit trace display requirement,
- prototype UI state behavior,
- prototype UI copy constraints,
- prototype UI navigation constraints,
- prototype UI disable-state behavior,
- prototype UI repair-state behavior,
- prototype UI non-readiness labels,
- prototype UI acceptance criteria.

v0.15 may not define:

- real patient data ingestion,
- real patient case selection,
- deidentified real patient case upload,
- diagnostic ground truth workflow,
- final diagnosis screen,
- most-likely diagnosis screen,
- disease ranking screen,
- probability heatmap,
- treatment pathway screen,
- test ordering workflow,
- procedure recommendation workflow,
- follow-up scheduling workflow,
- triage workflow,
- patient-facing report,
- public-ready interface,
- product-ready release,
- clinical validation dataset,
- diagnostic performance metrics,
- platform-wide clinical review status,
- autonomous clinical decision support deployment,
- MDD replacement workflow.

---

## 4. Global Authority Constraints

The following constraints remain mandatory across v0.15.

| Constraint | Required State |
|---|---|
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| product_ready | false |
| clinically_reviewed.platform_wide | false |
| patient_facing_use | not_allowed |
| real_patient_data | not_allowed |
| deidentified_real_patient_data | not_allowed |
| clinical_validation | not_opened |
| diagnostic_performance_claim | not_allowed |
| automated_diagnosis | not_allowed |
| automated_exclusion | not_allowed |
| automated_treatment_selection | not_allowed |
| automated_test_order | not_allowed |
| automated_procedure_decision | not_allowed |
| automated_follow_up_schedule | not_allowed |
| automated_triage | not_allowed |
| replacement_of_MDD | not_allowed |
| replacement_of_clinician | not_allowed |
| replacement_of_radiologist | not_allowed |
| replacement_of_pathologist | not_allowed |
| replacement_of_pulmonologist | not_allowed |
| replacement_of_rheumatologist | not_allowed |
| replacement_of_microbiology | not_allowed |
| replacement_of_occupational_medicine_review | not_allowed |
| replacement_of_oncology_review | not_allowed |
| replacement_of_radiation_oncology_review | not_allowed |
| replacement_of_urgent_review | not_allowed |

No prototype screen, button, badge, banner, modal, card, chart, diagram, color, icon, tooltip, export preview, audit trace, case selector, scenario label, validation label, or visual artifact may override these constraints.

---

## 5. Prototype Workspace Philosophy

The prototype workspace must help a reviewer inspect how sealed governance behavior appears in an interface.

It must not push the reviewer toward a final disease label.

The workspace should make the following easier to see:

- the selected synthetic demo case,
- the synthetic-only boundary,
- what fictional case context was supplied,
- what evidence is missing,
- what source status limits apply,
- which mimic families remain visible,
- which overlaps remain unresolved,
- why confidence remains limited,
- which review prompts are visible,
- which unsafe outputs are blocked,
- which authority limits are active,
- which no-decision object is present,
- which audit events explain the visible UI state,
- why export preview remains safe and non-diagnostic.

The workspace must not make the following easier to do:

- diagnose,
- exclude mimics,
- select treatment,
- order tests,
- decide procedures,
- schedule follow-up,
- triage,
- bypass MDD,
- bypass urgent clinical review,
- generate a patient-facing report,
- imply public readiness,
- imply product readiness,
- imply clinical validation.

Prototype workspace rule:

> The prototype workspace is a governed demo behavior surface, not a clinical decision surface.

---

## 6. Prototype Workspace Scope

The prototype workspace may show UI behavior for sealed synthetic demo artifacts only.

Allowed prototype scope:

- synthetic case selection,
- synthetic intake display,
- fictional case context review,
- reasoning map display,
- missing evidence panel display,
- mimic visibility panel display,
- overlap panel display,
- source status panel display,
- confidence limiter display,
- review prompt display,
- authority envelope display,
- no-decision object display,
- audit trace display,
- red-team fail-closed display,
- safe export preview display,
- visual safety label display.

Blocked prototype scope:

- real patient workspace,
- clinical intake workspace,
- diagnostic reporting workspace,
- treatment planning workspace,
- test ordering workspace,
- procedure planning workspace,
- follow-up scheduling workspace,
- triage workspace,
- patient communication workspace,
- public demo deployment,
- product release workspace,
- clinical validation dashboard,
- diagnostic performance dashboard.

Prototype scope rule:

> Prototype scope begins and ends with synthetic demo UI behavior.

---

## 7. Prototype UI Surface Registry

The following prototype UI surfaces are opened for contract design.

| UI Surface ID | Prototype Surface | Purpose | Authority Risk |
|---|---|---|---|
| V15_UI_001 | prototype_home_screen | Show prototype-only boundary and entry choices | public/product readiness risk |
| V15_UI_002 | synthetic_demo_case_selector | Select sealed synthetic cases only | real-case selection risk |
| V15_UI_003 | demo_intake_review_screen | Display fictional supplied and missing fields | real intake / inferred-data risk |
| V15_UI_004 | reasoning_map_screen | Show reasoning-state relations visually and text-governed | diagram-as-proof risk |
| V15_UI_005 | missing_evidence_panel | Preserve missing evidence visibility | missing-as-exclusion risk |
| V15_UI_006 | mimic_visibility_panel | Preserve high-risk mimic visibility | mimic-as-diagnosis risk |
| V15_UI_007 | overlap_panel | Preserve unresolved boundaries | winner-selection risk |
| V15_UI_008 | source_status_panel | Show source role and limitation | source-as-authority risk |
| V15_UI_009 | confidence_limiter_panel | Show interpretation limits | probability/ranking risk |
| V15_UI_010 | review_prompt_panel | Show review prompts without action authority | recommendation risk |
| V15_UI_011 | red_team_fail_closed_screen | Show unsafe attempts blocked | unsafe text leakage risk |
| V15_UI_012 | safe_export_preview_screen | Preview safe MDD preparation export | report/impression risk |
| V15_UI_013 | authority_envelope_display | Keep non-authority boundary visible | hidden authority drift risk |
| V15_UI_014 | no_decision_object_display | Show blocked decision fields explicitly | hidden decision risk |
| V15_UI_015 | audit_trace_screen | Show traceability without correctness claim | audit-as-validation risk |
| V15_UI_016 | visual_safety_label_display | Keep visual artifacts explanatory only | visual-as-diagnosis risk |

---

## 8. Synthetic Demo-Only Case Selection

The case selector may list only sealed synthetic demo cases.

Allowed selector behavior:

- show synthetic demo case ID,
- show demo case title,
- show demo purpose,
- show governance behavior being demonstrated,
- show scenario category,
- show synthetic-only safety label,
- show real_patient_data=false,
- show clinical_validation_use=false,
- show patient_facing_use=not_allowed,
- show authority envelope summary,
- show available demo artifacts.

Blocked selector behavior:

- upload real case,
- paste real report,
- import DICOM,
- import HRCT image,
- import accession number,
- enter patient identifier,
- select deidentified real case,
- mark case as clinically validated,
- mark case as product-ready,
- mark case as public-ready,
- show diagnostic ground truth,
- show final diagnosis,
- show most likely diagnosis,
- show disease probability.

Selector rule:

> The prototype selector selects fictional governance scenarios, not clinical cases.

---

## 9. Non-Clinical UI Boundary

Every prototype screen must preserve a visible non-clinical boundary.

Required non-clinical UI indicators:

- “Synthetic demo only,”
- “Not for clinical use,”
- “Not patient-facing,”
- “Not clinically validated,”
- “No diagnosis / no treatment / no orders,”
- “Prototype behavior demonstration,”
- authority envelope visible or one click away only when layout space is constrained,
- no-decision object visible on decision-adjacent screens.

Blocked UI indicators:

- “Clinical mode,”
- “Ready for use,”
- “Patient-ready,”
- “Public-ready,”
- “Product-ready,”
- “Validated,”
- “Diagnostic support active,”
- “Decision support active,”
- “Recommended diagnosis,”
- “Recommended treatment,”
- “Recommended next test,”
- “Recommended follow-up.”

Non-clinical UI rule:

> A prototype screen must identify itself as prototype demo behavior before any reasoning content is shown.

---

## 10. Visually Guided but Text-Governed Interaction Principle

v0.15 inherits the v0.14.6 visual artifact safety rule:

> visually guided but text-governed.

Visuals may help orientation.

Visuals may not create meaning without text.

Allowed visual guidance:

- section cards,
- non-probabilistic state markers,
- neutral icons,
- reasoning relationship lines,
- safe-vs-unsafe comparison panels,
- fail-closed state cards,
- audit trace flow,
- export boundary diagrams,
- source-status explanation markers,
- missing-evidence visibility markers.

Blocked visual guidance:

- probability heatmap,
- confidence meter,
- disease ranking scale,
- green/yellow/red diagnosis severity scale,
- treatment pathway flow,
- triage decision tree,
- diagnostic image simulation,
- final diagnosis badge,
- confirmed disease icon,
- ruled-out disease icon,
- patient-facing infographic.

Visual interaction rule:

> Visuals may guide the reviewer toward the relevant text, but only text-governed safety language may define the meaning of the UI state.

---

## 11. Allowed Prototype Screens

The following prototype screens are allowed for v0.15 design.

| Screen | Allowed Purpose |
|---|---|
| Prototype boundary landing screen | State synthetic/non-clinical/prototype limits |
| Synthetic demo case selection screen | Select sealed fictional scenarios only |
| Demo intake review screen | Show supplied vs missing fictional case context |
| Reasoning map screen | Show governed reasoning-state relations |
| Missing evidence panel | Preserve missing evidence visibility |
| Mimic visibility panel | Preserve high-risk mimic visibility |
| Overlap panel | Preserve unresolved coexistence |
| Source status panel | Show source role and limitation |
| Confidence limiter panel | Show interpretation limits without probability |
| Review prompt panel | Show MDD/specialist/urgent review prompts without action authority |
| Red-team fail-closed screen | Show unsafe UI/export attempts blocked |
| Safe export preview screen | Preview non-diagnostic MDD preparation package |
| Authority envelope screen/footer | Show non-authority boundary |
| No-decision object screen/card | Show decisions not made by platform |
| Audit trace screen | Show traceability without correctness claim |

Allowed screen rule:

> Allowed screens display governance behavior, not clinical decisions.

---

## 12. Blocked Prototype Screens

The following screens are blocked in v0.15.

| Blocked Screen | Reason |
|---|---|
| Final diagnosis screen | diagnostic authority risk |
| Most likely diagnosis screen | ranking / diagnostic closure risk |
| Diagnosis probability dashboard | probability / performance claim risk |
| Disease rule-out screen | exclusion authority risk |
| Treatment recommendation screen | treatment authority risk |
| Test ordering screen | order authority risk |
| Procedure recommendation screen | procedure authority risk |
| Follow-up scheduler | follow-up authority risk |
| Triage / disposition screen | triage authority risk |
| Patient-facing report screen | patient-facing leak risk |
| Clinical validation dashboard | validation overclaim risk |
| Product readiness dashboard | deployment overclaim risk |
| Public demo publication screen | public-readiness risk |
| MDD consensus screen | MDD replacement risk |
| Expert-equivalence screen | clinician replacement risk |

Blocked screen rule:

> If a screen requires clinical authority to be meaningful, it is not allowed in v0.15.

---

## 13. Demo Intake UI Boundary

The demo intake UI may display fictional supplied fields and missing fields.

Allowed demo intake UI behavior:

- display supplied fictional case context,
- display not-provided fields,
- display provided-vs-inferred boundary,
- display synthetic data label,
- display source status for supplied examples,
- display missing evidence as missing,
- display no real patient data warning,
- block upload/import controls for real patient materials.

Blocked demo intake UI behavior:

- real patient upload,
- free-text real report paste,
- DICOM import,
- HRCT image upload,
- patient identifier field,
- accession number field,
- institution identifier field,
- auto-infer missing exposure,
- auto-infer CTD/SARD context,
- auto-infer microbiology status,
- auto-infer pathology status,
- convert missing field into exclusion,
- convert supplied fictional field into diagnosis.

Demo intake rule:

> Intake UI may show fictional input state, not collect clinical data.

---

## 14. Reasoning Map UI Boundary

The reasoning map UI may show relationships among sealed reasoning objects.

Allowed reasoning map behavior:

- show case context node,
- show temporal comparison node,
- show pattern-family prompt nodes,
- show differential prompt nodes,
- show missing evidence nodes,
- show mimic visibility nodes,
- show overlap nodes,
- show source status nodes,
- show confidence limiter nodes,
- show review prompt nodes,
- show authority envelope node,
- show no-decision node,
- show audit trace links.

Blocked reasoning map behavior:

- final diagnosis node,
- disease winner node,
- probability edge,
- likelihood ranking,
- ruled-out node,
- treatment action node,
- test order node,
- procedure recommendation node,
- follow-up interval node,
- triage node,
- patient-facing explanation node,
- MDD consensus node.

Reasoning map rule:

> A reasoning map shows governed relationships, not proof of diagnosis.

---

## 15. Missing Evidence Panel UI Boundary

The missing evidence panel must preserve missingness as a limiter.

Allowed missing evidence panel behavior:

- show missing exposure history,
- show missing prior CT,
- show missing CTD/SARD context,
- show missing microbiology context,
- show missing oncology/therapy context,
- show missing pathology/MDD context,
- show why interpretation remains limited,
- show relevant review prompt where sealed logic permits,
- show audit reference for missing field state.

Blocked missing evidence panel behavior:

- “not provided” becomes “negative,”
- missing exposure becomes HP excluded,
- missing CTD context becomes CTD-ILD excluded,
- missing microbiology becomes infection excluded,
- missing oncology context becomes malignancy excluded,
- missing prior CT becomes stability/progression claim,
- missing pathology becomes diagnostic closure,
- missing evidence becomes follow-up recommendation.

Missing evidence rule:

> Missing evidence limits interpretation; it never excludes disease.

---

## 16. Mimic Visibility Panel UI Boundary

The mimic visibility panel must preserve high-risk mimic visibility.

Allowed mimic visibility behavior:

- show high-risk mimic family visibility,
- show source-limited prompt status,
- show missing evidence tied to mimic review,
- show overlap with pattern-family prompts,
- show review visibility without diagnosis,
- show audit trace for visible mimic prompts.

Blocked mimic visibility behavior:

- mimic confirmed,
- mimic excluded,
- mimic ranked by probability,
- mimic hidden because another pattern is prominent,
- mimic downgraded by color alone,
- mimic converted into treatment recommendation,
- mimic converted into procedure recommendation,
- mimic converted into triage.

Mimic panel rule:

> Mimic visibility is a safety prompt, not a diagnosis or exclusion list.

---

## 17. Overlap Panel UI Boundary

The overlap panel must preserve unresolved coexistence.

Allowed overlap behavior:

- show possible coexisting processes,
- show unresolved boundaries,
- show source limitations,
- show missing evidence dependencies,
- show temporal comparison dependencies,
- show review prompts where relevant,
- show no winner selected.

Blocked overlap behavior:

- choose one final disease,
- rank competing processes,
- collapse overlap into a single label,
- convert overlap into diagnostic certainty,
- convert overlap into treatment pathway,
- convert overlap into test ordering,
- convert overlap into procedure decision,
- convert overlap into triage.

Overlap rule:

> Overlap remains visible until human clinical review resolves it outside the platform.

---

## 18. Source Status Panel UI Boundary

The source status panel must preserve source role and limitation.

Allowed source status behavior:

- show source role,
- show source status,
- show source limitation,
- show source-to-claim mapping where available,
- show source debt where applicable,
- show source-limited prompt visibility,
- show that source status does not validate diagnosis,
- show audit reference for source-state display.

Blocked source status behavior:

- source confirms diagnosis,
- source validates clinical correctness,
- source proves platform accuracy,
- source overrides missing evidence,
- source authorizes treatment,
- source authorizes ordering,
- source authorizes procedure,
- source creates public readiness,
- source creates product readiness.

Source status rule:

> Sources anchor prompt visibility and limitations; they do not grant clinical authority.

---

## 19. Red-Team Fail-Closed UI Boundary

The red-team fail-closed UI may show unsafe attempts being blocked.

Allowed red-team UI behavior:

- show unsafe attempt label,
- show blocked state,
- show failure reason,
- show repair requirement,
- show revalidation requirement where relevant,
- show authority effect none,
- show audit event,
- show safe alternative wording only when it remains non-diagnostic and non-actionable.

Blocked red-team UI behavior:

- render unsafe output as usable clinical content,
- make blocked diagnosis visually prominent as if true,
- make blocked treatment/action text look actionable,
- hide failure reason,
- allow bypass,
- allow export despite unsafe state,
- allow unsafe text in export preview,
- imply red-team success proves clinical safety.

Red-team UI rule:

> Red-team UI demonstrates fail-closed behavior, not clinical advice.

---

## 20. Safe Export Preview UI Boundary

The safe export preview UI may show the non-diagnostic MDD preparation package format.

Allowed safe export preview behavior:

- preview governance-safe export sections,
- show synthetic demo label,
- show non-clinical label,
- show authority envelope,
- show no-decision statement,
- show source status,
- show missing evidence,
- show mimic visibility,
- show overlap,
- show confidence limiters,
- show review prompts,
- show audit references,
- show export blocked state when unsafe.

Blocked safe export preview behavior:

- heading “Impression,”
- heading “Diagnosis,”
- heading “Conclusion” when used as diagnostic closure,
- final diagnosis,
- disease exclusion,
- probability table,
- confidence score,
- treatment recommendation,
- test order,
- procedure recommendation,
- follow-up recommendation,
- triage/disposition,
- patient-facing summary,
- MDD consensus,
- clinical validation claim,
- product-ready claim,
- public-ready claim.

Safe export preview rule:

> Export preview shows safe formatting behavior, not a clinical report.

---

## 21. Visual Safety Label Integration

Every prototype screen containing visual artifacts must integrate visual safety labels.

Required label elements:

```yaml
visual_safety_label:
  synthetic_demo_only: true
  non_clinical: true
  not_patient_facing: true
  not_public_ready: true
  not_product_ready: true
  visual_is_not_diagnosis: true
  diagram_is_not_proof: true
  color_is_not_probability: true
  icon_is_not_authority: true
  flow_is_not_treatment_pathway: true
  text_governs_visual_meaning: true
```

Blocked label omissions:

- visual artifact without synthetic label,
- diagram without proof disclaimer,
- color-coded state without probability disclaimer,
- icon without authority disclaimer,
- flow without treatment-pathway disclaimer,
- workspace mock without prototype-only disclaimer.

Visual label rule:

> No strong visual may appear without a text safety boundary.

---

## 22. Authority Envelope Display Requirement

The authority envelope must remain visible across the prototype workspace.

Minimum authority envelope display:

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
  clinical_validation: not_opened
  mdd_replacement: not_allowed
```

Allowed display modes:

- persistent footer,
- persistent side panel,
- fixed header badge plus expandable full envelope,
- decision-adjacent card,
- export-preview required block.

Blocked display modes:

- hidden authority envelope,
- authority envelope only in documentation,
- authority envelope only after export,
- authority envelope replaced by small icon,
- authority envelope collapsible without warning on decision-adjacent screens,
- authority envelope absent from export preview.

Authority display rule:

> The UI must show lack of authority before the user can mistake the prototype for a clinical tool.

---

## 23. No-Decision Object Display Requirement

The prototype workspace must display a no-decision object wherever decision-adjacent content appears.

Required no-decision object:

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

Allowed no-decision display:

- card on reasoning map,
- card on export preview,
- footer item on panel screens,
- modal before viewing red-team examples,
- audit-linked state object.

Blocked no-decision display:

- no-decision object omitted,
- no-decision object only stored invisibly,
- no-decision object contradicted by screen labels,
- no-decision object hidden behind final diagnosis language,
- no-decision object removed from export preview.

No-decision rule:

> The prototype must show what it did not decide as clearly as what it displayed.

---

## 24. Audit Trace Display Requirement

The audit trace UI may show why a prototype state is visible or blocked.

Allowed audit trace display:

- case selected,
- synthetic status confirmed,
- intake field displayed,
- missing field preserved,
- source status displayed,
- mimic visibility preserved,
- overlap preserved,
- confidence limiter displayed,
- review prompt displayed,
- authority envelope displayed,
- no-decision object displayed,
- unsafe output blocked,
- export preview generated,
- export preview blocked,
- repair required,
- revalidation required where relevant.

Blocked audit trace display:

- diagnosis validated,
- clinical correctness proven,
- treatment authorized,
- test ordered,
- procedure recommended,
- follow-up scheduled,
- triage completed,
- MDD consensus achieved,
- platform clinically validated,
- product readiness achieved,
- public readiness achieved.

Audit trace rule:

> Audit trace explains UI state, not medical truth.

---

## 25. Prototype Readiness Boundary

v0.15.0 opens prototype UI behavior governance only.

Allowed readiness language:

- prototype workspace entry gate opened,
- demo UI behavior contract opened,
- synthetic demo UI boundary defined,
- prototype screen registry opened,
- UI authority boundary defined,
- safe export preview boundary defined,
- red-team fail-closed UI boundary defined.

Blocked readiness language:

- product ready,
- public ready,
- clinically reviewed,
- clinically validated,
- ready for patient use,
- ready for clinical deployment,
- diagnostic performance established,
- safe for clinical use,
- regulatory ready,
- MDD replacement ready,
- clinician replacement ready.

Readiness boundary rule:

> A prototype can be ready for internal demonstration without being ready for clinical use.

---

## 26. v0.15.0 Acceptance Criteria

v0.15.0 may be considered complete only if all of the following are true.

| Criterion | Required State |
|---|---|
| prototype workspace scope defined | true |
| synthetic demo-only case selection defined | true |
| non-clinical UI boundary defined | true |
| visually guided but text-governed principle preserved | true |
| allowed prototype screens defined | true |
| blocked prototype screens defined | true |
| demo intake UI boundary defined | true |
| reasoning map UI boundary defined | true |
| missing evidence panel UI boundary defined | true |
| mimic visibility panel UI boundary defined | true |
| overlap panel UI boundary defined | true |
| source status panel UI boundary defined | true |
| red-team fail-closed UI boundary defined | true |
| safe export preview UI boundary defined | true |
| visual safety label integration required | true |
| authority envelope display required | true |
| no-decision object display required | true |
| audit trace display required | true |
| real patient data blocked | true |
| clinical validation blocked | true |
| product readiness blocked | true |
| public readiness blocked | true |
| patient-facing use blocked | true |
| diagnostic authority remains none | true |
| treatment authority remains none | true |
| test/order/procedure/follow-up/triage authority remains none | true |
| MDD replacement blocked | true |

v0.15.0 acceptance rule:

> The entry gate passes only if prototype UI behavior is opened while clinical authority remains closed.

---

## 27. Next Step

The next recommended step is:

- v0.15.1 — Demo Workspace Screen / Component Behavior Schema

v0.15.1 should define the concrete schema for the allowed prototype screens and components opened in v0.15.0, including:

- screen identifiers,
- component identifiers,
- required safety labels,
- required authority envelope placement,
- required no-decision object placement,
- allowed actions,
- blocked actions,
- disabled-state semantics,
- fail-closed display states,
- audit trace hooks,
- visual/text governance rules,
- synthetic-only case binding.

v0.15.1 must not open clinical deployment, real patient data, public readiness, product readiness, patient-facing use, clinical validation, diagnostic authority, treatment authority, test ordering, procedure decision, follow-up scheduling, triage, or MDD replacement.

---

## 28. Governance Statement

This entry gate opens prototype workspace demo UI behavior governance.

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
It does not replace clinicians, radiologists, pathologists, pulmonologists, rheumatologists, microbiologists, occupational medicine review, oncology review, radiation oncology review, MDD, or urgent clinical assessment.

The platform remains an evidence-governed clinical reasoning platform.

The current project principle is:

> “It teaches clinicians to read change before naming disease.”

The v0.15.0 governance discipline is:

> “Do not let a prototype workspace become clinical deployment.”