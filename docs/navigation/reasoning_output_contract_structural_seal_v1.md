# ILD Reasoning Platform — Reasoning Output Contract / Structured Response Schema Structural Seal v1

Version: v0.9.4  
Status: structurally_sealed  
Scope: Structured clinician-facing reasoning output contract structural seal  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Seal Purpose

This document structurally seals v0.9 — Reasoning Output Contract / Structured Response Schema.

This seal confirms that the ILD Reasoning Platform now has a governed clinician-facing structured output contract.

This seal does not add new disease content.

It does not diagnose.  
It does not treat.  
It does not decide tests.  
It does not decide procedures.  
It does not schedule follow-up.  
It does not exclude mimics.  
It does not replace MDD.  
It does not create public readiness.  
It does not make the platform clinically reviewed.

The platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The sealed v0.9 principle is:

> “Structured output must display uncertainty, sources, missing evidence, mimics, overlap, review prompts, and authority limits before any disease name is allowed to dominate the response.”

---

## 2. Sealed v0.9 Chain

The following v0.9 chain is now structurally sealed:

| Version | File | Role | Seal Status |
|---|---|---|---|
| v0.9.0 | `docs/navigation/reasoning_output_contract_entry_gate_v1.md` | Output contract entry gate | sealed |
| v0.9.1 | `docs/data/schema/structured_output_layer_schema_v1.md` | Detailed structured output layer schema | sealed |
| v0.9.2 | `docs/examples/structured_output_safe_response_templates_v1.md` | Safe response templates and examples | sealed |
| v0.9.3 | `docs/navigation/structured_output_validation_checklist_v1.md` | Pre-seal validation checklist | sealed |
| v0.9.4 | `docs/navigation/reasoning_output_contract_structural_seal_v1.md` | Structured output contract structural seal | sealed |

---

## 3. Structural Seal Statement

The v0.9 structured output layer is structurally complete.

This means:

- four-phase Case Reasoning Flow is defined,
- all 13 structured output layers are defined,
- detailed layer schema exists,
- safe response examples exist,
- validation checklist exists,
- source status display is mandatory,
- authority envelope is mandatory,
- blocked output protocol is mandatory,
- confidence limiter replaces diagnostic confidence,
- diagnostic confidence scoring is blocked,
- narrow clinically reviewed scopes remain separated from platform-wide clinical review,
- blocked verbs and preferred verbs are defined,
- urgent review outranks MDD and disease naming,
- high-risk mimics remain visible,
- missing evidence remains visible,
- overlap remains visible,
- uncertainty remains visible,
- diagnostic authority remains none,
- treatment authority remains none,
- public readiness remains false,
- platform-wide clinically reviewed status remains false.

This seal confirms structured output readiness.

It does not confirm clinical performance.

---

## 4. Prior Layer Inheritance

v0.9 inherits and preserves the following prior layers:

| Prior Layer | Inherited Constraint |
|---|---|
| v0.3 Superimposed Events Core | Multiple processes may coexist; single-label closure remains blocked |
| v0.4 Evidence Layer / Source Review Governance | Source-sensitive claims require anchor, role, review status, and limitation visibility |
| v0.5 Test Case Coverage Expansion | Missing evidence, mimics, MDD, urgent review, and non-authority remain visible |
| v0.6 UIP Parity Seal | UIP-facing reasoning remains non-diagnostic and source-governed |
| v0.6.R1/R2/R3 | Source-review debt and claim mapping discipline remain visible |
| v0.7 Non-UIP Differential Seal | Differential prompts remain visible without diagnoses |
| v0.8 High-Risk Mimic Seal | High-risk mimics remain visible without becoming diagnoses |
| checkpoint-v0.8 | v0.9 remains output governance, not clinical deployment |

Sealed rule:

> v0.9 displays prior reasoning layers safely; it does not convert them into diagnostic authority.

---

## 5. Four-Phase Case Reasoning Flow Seal

The following four-phase structure is sealed.

| Phase | Phase Name | Sealed Layers |
|---|---|---|
| Phase 1 | Grounding | case_context_summary; temporal_change_summary |
| Phase 2 | Reasoning Core | pattern_family_prompts; differential_prompt_layer; overlap_layer |
| Phase 3 | Safety Net | high_risk_mimic_layer; missing_evidence_layer; uncertainty_layer |
| Phase 4 | Escalation and Governance | urgent_review_prompt_layer; MDD_review_prompt_layer; source_status_layer; authority_envelope; blocked_outputs |

Sealed rule:

> Output must follow clinical reasoning flow, not a disease-first report style.

---

## 6. Thirteen-Layer Output Seal

The following 13 structured output layers are sealed.

| Layer ID | Layer Name | Seal Requirement |
|---|---|---|
| V09_LAYER_001 | case_context_summary | Restates provided facts only; no inferred missing data |
| V09_LAYER_002 | temporal_change_summary | Shows change or comparison limitation before disease naming |
| V09_LAYER_003 | pattern_family_prompts | Pattern prompt only; not diagnosis |
| V09_LAYER_004 | differential_prompt_layer | Differential prompts only; not final diagnosis |
| V09_LAYER_005 | overlap_layer | Preserves coexistence and unresolved boundaries |
| V09_LAYER_006 | high_risk_mimic_layer | Keeps mimics visible without diagnosis or exclusion |
| V09_LAYER_007 | missing_evidence_layer | Lists missing evidence; missing evidence is not exclusion |
| V09_LAYER_008 | uncertainty_layer | Uses confidence_limiter; diagnostic confidence is blocked |
| V09_LAYER_009 | urgent_review_prompt_layer | Visible where relevant; no triage or treatment |
| V09_LAYER_010 | MDD_review_prompt_layer | Visible where relevant; does not replace MDD |
| V09_LAYER_011 | source_status_layer | Source role, claim mapping, and limitations visible |
| V09_LAYER_012 | authority_envelope | Mandatory in every structured output |
| V09_LAYER_013 | blocked_outputs | Diagnosis, exclusion, treatment, test, procedure, and follow-up outputs blocked |

Sealed rule:

> Every reasoning layer must remain a reasoning layer, not a clinical authority layer.

---

## 7. Authority Envelope Seal

The following authority envelope is mandatory in every structured output.

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
```

Optional narrow reviewed scopes may be displayed only as limited scopes:

```yaml
clinically_reviewed:
  platform_wide: false
  narrow_reviewed_scopes:
    - temporal_comparison_methodology
    - ATS_ERS_JRS_ALAT_2022_UIP_claim_to_source_mapping
```

Sealed rule:

> Narrow reviewed scope must never inflate into platform-wide clinical review.

---

## 8. Narrow Clinically Reviewed Scope Seal

The following narrow reviewed scopes are recognized only as limited methodology/source-review scopes:

| Narrow Reviewed Scope | Sealed Interpretation |
|---|---|
| temporal_comparison_methodology | Narrow methodology review only |
| ATS_ERS_JRS_ALAT_2022_UIP_claim_to_source_mapping | Narrow claim-to-source mapping review only |

These scopes do not create:

- platform-wide clinical review,
- diagnostic authority,
- treatment authority,
- public readiness,
- patient-facing readiness,
- clinical validation,
- diagnostic deployment readiness.

Blocked interpretations:

- “The platform is clinically reviewed.”
- “The output is clinically validated.”
- “UIP diagnosis is clinically confirmed.”
- “IPF diagnosis can be made by the platform.”
- “Public-ready clinical deployment is supported.”

Sealed rule:

> Reviewed scope is metadata, not clinical authority.

---

## 9. Source Status Display Seal

The `source_status_layer` is sealed as mandatory.

Every structured output must display, where relevant:

| Source Status Field | Required |
|---|---|
| source_ids | yes |
| source_role_class | yes |
| claim_mapping_status | yes |
| source_limitations | yes |
| treatment_heavy_warning | yes where relevant |
| diagnostic_performance_warning | yes where relevant |
| case_example_only_warning | yes where relevant |
| narrow_reviewed_scope | optional and limited |
| platform_wide_clinically_reviewed | false |

Source role classes remain:

- primary_high_authority,
- primary_limited_scope,
- auxiliary_review,
- diagnostic_performance_study,
- case_example_cautionary,
- internal_governance.

Sealed rule:

> Source status must not be hidden behind fluent clinical prose.

---

## 10. Confidence Limiter Seal

The platform must use confidence limiters, not diagnostic confidence scores.

Allowed:

```yaml
confidence_limiter:
  - prior CT unavailable
  - exposure history incomplete
  - expiratory HRCT unavailable
  - microbiology not integrated
  - MDD not documented
```

Blocked:

```yaml
diagnostic_confidence:
  IPF: high
  HP: low
```

Also blocked:

- numeric disease probabilities,
- final diagnostic ranking,
- “high confidence diagnosis,”
- “low confidence exclusion,”
- certainty language that hides missing evidence.

Sealed rule:

> The platform shows what limits interpretation, not what diagnosis it thinks it owns.

---

## 11. Linguistic Safety Seal

The platform must use non-authoritative reasoning language.

### 11.1 Blocked Language

The following must not appear as final clinical conclusions:

| Blocked Phrase | Blocked Reason |
|---|---|
| diagnoses | diagnostic authority leak |
| confirms | final confirmation leak |
| proves | overclaim |
| rules out | exclusion authority leak |
| excludes | exclusion authority leak |
| treatment required | treatment authority leak |
| start treatment | treatment authority leak |
| order | test-order authority leak |
| biopsy should be performed | procedure authority leak |
| bronchoscopy should be performed | procedure authority leak |
| follow up every X months | follow-up authority leak |
| MDD unnecessary | review replacement |
| clinically validated | unsupported validation claim |
| public-ready | unsupported deployment claim |
| patient-facing ready | patient-facing use leak |

### 11.2 Preferred Language

The platform should prefer:

| Preferred Language | Meaning |
|---|---|
| supports | supportive but not diagnostic |
| suggests | raises possibility |
| weakens | reduces support without exclusion |
| remains visible | preserves prompt |
| remains unresolved | preserves uncertainty |
| limited by missing evidence | confidence limiter |
| review-visible | review prompt |
| final diagnosis is not established | non-authority |
| source status is limited | source governance visibility |
| authority remains none | non-authority reminder |

Sealed rule:

> The safest phrasing is “prompt remains visible,” not “the patient has...” or “this is...”.

---

## 12. Blocked Output Protocol Seal

When a user asks for a blocked output, the platform must:

1. refuse diagnostic, treatment, test-order, procedure, or follow-up closure,
2. reframe into prompt visibility,
3. show missing evidence,
4. preserve mimics and competing families,
5. show urgent review or MDD review prompt where relevant,
6. print authority envelope.

Blocked request types include:

| User Request | Required Response Behavior |
|---|---|
| “What is the diagnosis?” | refuse diagnosis; show prompts and uncertainty |
| “Is this IPF?” | refuse diagnostic closure; show UIP support and missing evidence |
| “Can TB be ruled out?” | refuse exclusion; show microbiology limits |
| “Should steroids be started?” | refuse treatment; show mimics and review need |
| “Is biopsy required?” | refuse procedure decision; show pathology context as missing or review-visible |
| “Should PET/CT be ordered?” | refuse test order; show PET/CT context as review-visible |
| “When should follow-up be scheduled?” | refuse follow-up interval; show authority envelope |

Sealed rule:

> The platform may reframe, but it may not answer the blocked request directly.

---

## 13. Grounding Seal

The `case_context_summary` layer is sealed with the following constraints:

Allowed:

- provided facts,
- provided demographics,
- provided clinical context,
- provided imaging context,
- provided history,
- provided prior imaging status.

Blocked:

- inferred exposure,
- inferred autoimmune history,
- inferred medication history,
- inferred therapy history,
- inferred diagnosis,
- inferred prior CT comparison,
- inferred pathology.

Sealed rule:

> The platform may summarize what is provided, but it must not invent missing facts.

---

## 14. Temporal Change Seal

The `temporal_change_summary` layer is sealed with the following constraints:

Allowed:

- new finding,
- interval worsening,
- interval improvement,
- stability,
- mixed change,
- unclear change,
- comparison limitation,
- acute vs chronic uncertainty.

Blocked:

- PPF diagnosis,
- acute exacerbation diagnosis,
- progression confirmed without sufficient temporal basis,
- stability proves benignity,
- prior comparison invented.

Sealed rule:

> Change must be read before disease naming, but change alone is not diagnosis.

---

## 15. Pattern and Differential Seal

The `pattern_family_prompts` and `differential_prompt_layer` are sealed with the following constraints:

Allowed:

- UIP-like prompt,
- probable UIP-like prompt,
- indeterminate for UIP prompt,
- alternative pattern prompt,
- NSIP-like prompt,
- OP-like prompt,
- HP-like prompt,
- CTD-ILD context prompt,
- sarcoid-like prompt,
- granulomatous prompt,
- mimic pattern prompt,
- acute overlay prompt,
- unclassifiable or mixed-pattern prompt.

Blocked:

- UIP equals IPF,
- probable UIP equals IPF,
- OP equals COP,
- NSIP equals idiopathic NSIP,
- granulomas equal sarcoidosis,
- HP-like features equal HP diagnosis,
- differential prompt becomes diagnosis,
- final ranking presented as diagnosis.

Sealed rule:

> Pattern-family naming is reasoning support, not disease authority.

---

## 16. Overlap Seal

The `overlap_layer` is sealed with the following constraints:

Allowed:

- coexistence,
- competing processes,
- unresolved boundaries,
- acute overlay over chronic background,
- mimic overlap,
- disease-family overlap.

Blocked:

- single-label closure,
- hidden secondary process,
- mimic erasure,
- acute process collapsed into chronic ILD naming,
- “winner” label without evidence.

Sealed rule:

> Overlap must be represented as coexistence, not forced closure.

---

## 17. High-Risk Mimic Seal

The `high_risk_mimic_layer` is sealed with the following protected mimic domains:

- infection,
- TB,
- NTM,
- fungal disease,
- aspiration,
- occupational ILD,
- beryllium,
- drug-induced / therapy-related ILD,
- radiation pneumonitis / RILI,
- checkpoint inhibitor pneumonitis,
- ICI-associated sarcoid-like reaction,
- pulmonary lymphangitic carcinomatosis,
- malignancy / lymphoma / recurrence,
- acute dangerous overlay.

Blocked:

- mimic diagnosed,
- mimic excluded,
- treatment started,
- test ordered,
- procedure recommended,
- oncology/radiation/occupational management recommended.

Sealed rule:

> High-risk mimics remain visible without becoming high-risk mimic diagnoses.

---

## 18. Missing Evidence Seal

The `missing_evidence_layer` is sealed with the following constraints:

Required where relevant:

- prior CT,
- exposure history,
- occupational history,
- beryllium exposure,
- medication history,
- therapy history,
- radiation history,
- checkpoint inhibitor exposure,
- autoimmune / CTD/SARD context,
- microbiology,
- AFB / culture / NAAT,
- fungal testing,
- expiratory HRCT,
- BAL context,
- pathology context,
- malignancy status,
- PET/CT context,
- aspiration risk,
- urgent clinical status,
- MDD status.

Blocked:

- missing exposure excludes HP,
- missing microbiology excludes infection,
- missing occupational history excludes occupational ILD,
- missing serology excludes CTD-ILD,
- missing prior CT proves stability,
- missing pathology proves benignity.

Sealed rule:

> Missing evidence must remain visible and must not become exclusion.

---

## 19. Uncertainty Seal

The `uncertainty_layer` is sealed with the following constraints:

Required:

- unresolved questions,
- confidence_limiter,
- source uncertainty,
- closure_status: not_established.

Blocked:

- diagnostic_confidence,
- numeric probability,
- final diagnostic rank,
- hidden uncertainty,
- overstatement of source support.

Sealed rule:

> Uncertainty is an output feature, not a defect.

---

## 20. Urgent Review Seal

The `urgent_review_prompt_layer` is sealed as higher priority than MDD and disease naming when active.

Urgent prompt triggers may include:

- acute hypoxemia,
- rapid dyspnea progression,
- fever or systemic illness,
- hemoptysis or anemia,
- vascular concern,
- severe infection possible,
- immunosuppression with new findings,
- known malignancy with new findings,
- post-radiation new opacity,
- ICI exposure with new pulmonary findings,
- severe or worsening respiratory status.

Blocked:

- triage decision,
- treatment,
- disposition,
- false reassurance,
- “no urgent review needed” when danger data are incomplete,
- acute exacerbation diagnosis.

Sealed rule:

> Urgent review prompt is safety visibility, not triage authority.

---

## 21. MDD / Specialist Review Seal

The `MDD_review_prompt_layer` is sealed as review visibility only.

Allowed specialist review prompts:

- pulmonology,
- thoracic radiology,
- pathology,
- microbiology,
- rheumatology,
- occupational medicine,
- oncology,
- radiation oncology,
- urgent clinical assessment,
- multidisciplinary discussion.

Blocked:

- MDD unnecessary,
- specialist review replaced,
- working diagnosis final,
- single-specialty closure when cross-domain uncertainty persists.

Sealed rule:

> Specialist review visibility is not specialist replacement.

---

## 22. Minimal and Full Output Mode Seal

### 22.1 Minimal Output Mode

A minimal structured output may be short, but must still include:

- case context,
- temporal status or limitation,
- high-risk mimic visibility or limitation,
- missing evidence,
- uncertainty / confidence limiter,
- urgent review prompt if relevant,
- source status summary,
- authority envelope.

Minimal output must not omit:

- authority envelope,
- missing evidence,
- source status,
- uncertainty,
- urgent review when active,
- mimic layer when high-risk context exists.

### 22.2 Full Output Mode

A full structured output should include all 13 layers.

Required for:

- complex cases,
- high-risk mimic cases,
- overlap cases,
- acute overlay cases,
- source-limited cases,
- MDD-relevant cases,
- validation examples.

Sealed rule:

> Short output may be compact, but it cannot be unsafe.

---

## 23. Output Safety Priority Seal

When output priorities conflict, this order is sealed:

1. urgent_review_prompt_layer,
2. high_risk_mimic_layer,
3. missing_evidence_layer,
4. source_status_layer,
5. uncertainty_layer,
6. overlap_layer,
7. temporal_change_summary,
8. pattern_family_prompts,
9. differential_prompt_layer,
10. MDD_review_prompt_layer,
11. authority_envelope,
12. blocked_outputs.

Sealed rule:

> Safety, mimics, missing evidence, source limits, and uncertainty outrank disease naming.

---

## 24. Safe Response Template Seal

The v0.9.2 safe response templates are sealed as examples, not clinical protocols.

Template coverage sealed:

| Template Scenario | Sealed Behavior |
|---|---|
| UIP-like pattern with missing exposure | No IPF diagnosis; exposure/CTD/HP visible |
| Fibrotic HP vs UIP overlap | No HP/IPF diagnosis; missing exposure not exclusion |
| NSIP/OP overlap | No NSIP/COP diagnosis; CTD/infection/drug/aspiration visible |
| Sarcoid-like granulomatous pattern | Granulomas not sarcoidosis diagnosis; infection/beryllium/malignancy visible |
| Post-radiation new GGO | No RP diagnosis; infection/recurrence/drug/ICI visible |
| ICI exposure with FDG-avid nodes | No SLR/recurrence diagnosis; PET ambiguity visible |
| Known malignancy with septal thickening | No PLC diagnosis; infection/edema/therapy toxicity visible |
| Acute danger over chronic ILD | Urgent review visible; no acute exacerbation diagnosis |

Sealed rule:

> Examples demonstrate safe output behavior; they are not clinical protocols.

---

## 25. Blocked Outputs Seal

The following output categories remain sealed as blocked:

| Blocked Output Category | Seal Status |
|---|---|
| diagnosis | blocked |
| disease exclusion | blocked |
| treatment recommendation | blocked |
| test ordering | blocked |
| procedure decision | blocked |
| follow-up interval | blocked |
| public readiness claim | blocked |
| clinical validation claim | blocked |
| MDD replacement | blocked |
| urgent review replacement | blocked |
| patient-facing readiness | blocked |

Sealed rule:

> Structured formatting must not make blocked content appear authorized.

---

## 26. Drift Blocks Sealed

The following drift risks are sealed as blocked:

| Drift Risk | Sealed Block |
|---|---|
| output schema becomes diagnostic report | diagnostic_authority none |
| safe templates become clinical protocols | example-only status |
| source mapping becomes clinical validation | clinically_reviewed.platform_wide false |
| narrow review scope inflates globally | narrow scope rule |
| confidence limiter becomes diagnostic confidence | diagnostic_confidence blocked |
| source status hidden in prose | source_status_layer mandatory |
| missing evidence hidden | missing_evidence_layer mandatory |
| mimic visibility becomes mimic diagnosis | high_risk_mimic_layer guard |
| MDD prompt becomes MDD replacement | replacement blocked |
| urgent review becomes triage | triage authority none |
| treatment-heavy source leaks treatment | treatment_authority none |
| diagnostic-performance source automates interpretation | interpretation blocked |
| public-ready claim appears | public_ready false |
| patient-facing readiness appears | patient_facing_use not_allowed |

---

## 27. What This Seal Does Not Claim

This seal does not claim:

- clinical validation,
- diagnostic accuracy,
- treatment usefulness,
- guideline-complete implementation,
- real-world deployment readiness,
- public-facing readiness,
- patient-facing safety,
- automated triage readiness,
- real patient cohort validation,
- diagnosis generation capability,
- treatment planning capability,
- test ordering capability,
- procedure recommendation capability,
- follow-up scheduling capability,
- platform-wide clinical review.

This is a structural output-governance seal.

It proves that the v0.9 structured response layer is organized, source-governed, uncertainty-preserving, non-authoritative, and safe-by-contract.

---

## 28. Final v0.9 Seal Statement

The ILD Reasoning Platform v0.9 Reasoning Output Contract / Structured Response Schema is structurally sealed.

The platform remains an evidence-governed clinical reasoning platform.

It is not a diagnostic engine.  
It is not a treatment engine.  
It is not public-ready.  
It is not platform-wide clinically reviewed.  
It is not a patient-facing tool.  
It is not a replacement for clinicians, radiologists, pathologists, pulmonologists, rheumatologists, microbiologists, occupational medicine review, oncology review, radiation oncology review, MDD, or urgent clinical assessment.

Its structured output must:

- ground the case,
- read temporal change,
- show pattern prompts,
- show differential prompts,
- preserve overlap,
- expose high-risk mimics,
- list missing evidence,
- preserve uncertainty,
- show confidence limiters,
- show urgent review prompts where relevant,
- show MDD/specialist review prompts where relevant,
- display source status,
- print authority envelope,
- block diagnosis/treatment/test/procedure/follow-up outputs,
- and prevent disease naming from dominating before reasoning safeguards are visible.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The sealed v0.9 principle is:

> “Structured output must display uncertainty, sources, missing evidence, mimics, overlap, review prompts, and authority limits before any disease name is allowed to dominate the response.”

---

## 29. Forward Roadmap

With v0.9 structurally sealed, the next recommended phase is:

- v0.10 — Clinician Review Workspace / Interactive Reasoning UI Contract

v0.10 should not open as diagnosis, treatment, or public deployment.

Recommended v0.10 focus:

- clinician-facing review workspace layout,
- collapsible reasoning layers,
- source-status badges,
- missing-evidence panel,
- mimic visibility panel,
- temporal comparison panel,
- MDD / urgent review visibility,
- blocked output guardrails,
- audit trail for prompt visibility,
- authority envelope always visible,
- no diagnosis,
- no treatment,
- no test ordering,
- no procedure decision,
- no follow-up schedule,
- public_ready remains false,
- clinically_reviewed.platform_wide remains false.

v0.10 must not weaken the v0.9 Structured Output Contract Structural Seal.