# ILD Reasoning Platform — Structured Output Validation Checklist v1

Version: v0.9.3  
Status: pre_seal_validation_checklist  
Scope: Validation checklist for structured clinician-facing reasoning output contract  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This checklist verifies that v0.9 — Reasoning Output Contract / Structured Response Schema is ready for structural sealing.

It follows:

- `docs/navigation/reasoning_output_contract_entry_gate_v1.md`
- `docs/data/schema/structured_output_layer_schema_v1.md`
- `docs/examples/structured_output_safe_response_templates_v1.md`
- `docs/navigation/high_risk_mimic_structural_seal_v1.md`
- `docs/navigation/project_status_roadmap_checkpoint_v0_8.md`

This checklist does not add new disease content.

It does not diagnose.  
It does not treat.  
It does not decide tests.  
It does not decide procedures.  
It does not schedule follow-up.  
It does not exclude mimics.  
It does not replace MDD.  
It does not create public readiness.  
It does not make the platform clinically reviewed.

Its purpose is to verify that structured output remains safe, source-visible, uncertainty-preserving, and non-authoritative before v0.9 structural seal.

The v0.9 rule remains:

> “Structured output must display uncertainty, sources, missing evidence, mimics, overlap, review prompts, and authority limits before any disease name is allowed to dominate the response.”

For v0.9.3:

> “Output structure must not become diagnostic authority.”

---

## 2. v0.9 Chain Under Validation

The following v0.9 files must be present before sealing.

| Version | File | Role | Required Status |
|---|---|---|---|
| v0.9.0 | `docs/navigation/reasoning_output_contract_entry_gate_v1.md` | Output contract entry gate | present |
| v0.9.1 | `docs/data/schema/structured_output_layer_schema_v1.md` | Detailed output layer schema | present |
| v0.9.2 | `docs/examples/structured_output_safe_response_templates_v1.md` | Safe response examples/templates | present |
| v0.9.3 | `docs/navigation/structured_output_validation_checklist_v1.md` | Pre-seal validation checklist | current |

Validation condition:

- v0.9.0 through v0.9.2 must exist.
- Four-phase Case Reasoning Flow must be defined.
- All 13 output layers must be represented.
- Safe response templates must follow the schema.
- Authority envelope must remain mandatory.
- Blocked outputs must remain active.
- Structured output must not become clinical report authority.

---

## 3. Prior Seal Inheritance Checklist

v0.9 must inherit and preserve all prior seals.

| Prior Layer | Required Inheritance |
|---|---|
| v0.3 Superimposed Events Core | Multiple processes may coexist; single-label closure remains blocked |
| v0.4 Evidence Layer / Source Review Governance | Source-sensitive claims require anchor, role, review status, and limitation visibility |
| v0.5 Test Case Coverage Expansion | Missing evidence, mimics, MDD, urgent review, and non-authority remain visible |
| v0.6 UIP Parity Seal | UIP-facing reasoning remains non-diagnostic and source-governed |
| v0.6.R1/R2/R3 | Source-review debt and claim mapping discipline remain visible |
| v0.7 Non-UIP Differential Seal | Differential prompts remain visible without diagnoses |
| v0.8 High-Risk Mimic Seal | High-risk mimics remain visible without becoming diagnoses |
| checkpoint-v0.8 | v0.9 opens as output governance, not clinical deployment |

Validation condition:

- v0.9 must not weaken any prior non-authority constraint.
- v0.9 must not convert previous reasoning layers into diagnostic output.
- v0.9 must not convert safe templates into clinical protocols.

---

## 4. Four-Phase Case Reasoning Flow Checklist

The output contract must preserve the four-phase reasoning structure.

| Phase | Required Layers | Validation |
|---|---|---|
| Phase 1 — Grounding | case_context_summary; temporal_change_summary | required |
| Phase 2 — Reasoning Core | pattern_family_prompts; differential_prompt_layer; overlap_layer | required |
| Phase 3 — Safety Net | high_risk_mimic_layer; missing_evidence_layer; uncertainty_layer | required |
| Phase 4 — Escalation and Governance | urgent_review_prompt_layer; MDD_review_prompt_layer; source_status_layer; authority_envelope; blocked_outputs | required |

Validation condition:

- Output must not appear as an unstructured diagnostic paragraph.
- Grounding must come before pattern naming.
- Temporal change must be shown before disease naming.
- Safety net must be shown before closure.
- Governance must be visible in every output.

---

## 5. Mandatory Layer Validation Checklist

All 13 output layers must exist and remain constrained.

| Layer ID | Layer | Required Validation |
|---|---|---|
| V09_LAYER_001 | case_context_summary | restates provided facts only; no inferred missing data |
| V09_LAYER_002 | temporal_change_summary | shows change or comparison limitation before disease naming |
| V09_LAYER_003 | pattern_family_prompts | pattern prompt only; not diagnosis |
| V09_LAYER_004 | differential_prompt_layer | differential prompts only; not final diagnosis |
| V09_LAYER_005 | overlap_layer | preserves coexistence and unresolved boundaries |
| V09_LAYER_006 | high_risk_mimic_layer | keeps mimics visible without diagnosis/exclusion |
| V09_LAYER_007 | missing_evidence_layer | lists missing evidence; missing evidence is not exclusion |
| V09_LAYER_008 | uncertainty_layer | uses confidence_limiter; no diagnostic confidence |
| V09_LAYER_009 | urgent_review_prompt_layer | visible where relevant; no triage/treatment |
| V09_LAYER_010 | MDD_review_prompt_layer | visible where relevant; does not replace MDD |
| V09_LAYER_011 | source_status_layer | source role, claim mapping, and limitations visible |
| V09_LAYER_012 | authority_envelope | mandatory in every structured output |
| V09_LAYER_013 | blocked_outputs | diagnosis/treatment/test/procedure/follow-up outputs blocked |

Validation condition:

- No layer may output diagnosis as final.
- No layer may exclude a mimic as final.
- No layer may recommend treatment, tests, procedures, or follow-up.
- No layer may imply public readiness or platform-wide clinical review.

---

## 6. Grounding Layer Checklist

### 6.1 case_context_summary

Required:

- provided facts are listed,
- missing facts are marked as not_provided,
- inferred_facts remains empty,
- no unstated diagnosis is invented,
- no unstated exposure, autoimmune history, treatment, or prior imaging is inferred.

Failure examples:

- inferring exposure history from imaging,
- inferring CTD/SARD context from NSIP-like pattern,
- inferring IPF from UIP-like pattern,
- inventing prior CT comparison.

---

### 6.2 temporal_change_summary

Required:

- prior comparison status is shown,
- change direction is shown only if provided or inferable from explicit comparison,
- acute vs chronic context remains guarded,
- temporal limitations are listed,
- PPF / progression / acute exacerbation are not diagnosed automatically.

Failure examples:

- “PPF confirmed” from limited trend,
- “acute exacerbation confirmed” from new GGO alone,
- “stable disease” without prior comparison,
- ignoring missing prior CT.

---

## 7. Reasoning Core Checklist

### 7.1 pattern_family_prompts

Required:

- pattern prompts remain prompts,
- UIP-like does not equal IPF,
- OP-like does not equal COP,
- NSIP-like does not equal idiopathic NSIP,
- granulomatous does not equal sarcoidosis,
- HP-like does not equal HP diagnosis.

Failure examples:

- “UIP pattern confirms IPF.”
- “OP pattern means COP.”
- “Nonnecrotizing granulomas diagnose sarcoidosis.”

---

### 7.2 differential_prompt_layer

Required:

- multiple differential prompts may remain visible,
- no final ranking is presented as diagnosis,
- no competing family is excluded without evidence,
- final diagnosis remains not established.

Failure examples:

- “Most likely diagnosis is IPF” as final output,
- “HP excluded,”
- “infection excluded,”
- “MDD unnecessary.”

---

### 7.3 overlap_layer

Required:

- overlap states are visible,
- coexistence is allowed,
- acute overlay is not hidden by chronic ILD naming,
- high-risk mimics remain visible.

Failure examples:

- choosing one winner prematurely,
- hiding infection because OP-like pattern is present,
- hiding malignancy because sarcoid-like pattern is present,
- hiding HP because UIP-like pattern is present.

---

## 8. Safety Net Checklist

### 8.1 high_risk_mimic_layer

Required:

- high-risk mimics remain visible where relevant,
- mimics are not diagnosed,
- mimics are not excluded,
- treatment/test/procedure authority remains blocked.

Protected mimic domains:

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

Failure examples:

- “TB excluded,”
- “CIP confirmed,”
- “PLC diagnosed,”
- “malignancy excluded,”
- “start steroids.”

---

### 8.2 missing_evidence_layer

Required:

- missing evidence is explicitly listed,
- missing evidence is linked to affected prompts,
- missing evidence does not become exclusion,
- missing evidence does not disappear behind a disease label.

Required missing evidence categories where relevant:

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

Failure examples:

- “No exposure history, so HP is excluded.”
- “No microbiology provided, but infection is unlikely enough to ignore.”
- “No prior CT, but progression is confirmed.”

---

### 8.3 uncertainty_layer

Required:

- unresolved questions are listed,
- confidence_limiter is used,
- diagnostic_confidence is blocked,
- closure_status remains not_established.

Required:

```yaml
diagnostic_confidence: not_allowed
closure_status: not_established
```

Failure examples:

```yaml
diagnostic_confidence:
  IPF: high
  HP: low
```

or:

- numeric disease probabilities,
- final ranked diagnosis,
- hidden uncertainty.

---

## 9. Escalation and Governance Checklist

### 9.1 urgent_review_prompt_layer

Required where relevant:

- acute hypoxemia,
- rapid dyspnea progression,
- fever/systemic illness,
- hemoptysis/anemia,
- vascular concern,
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
- “no urgent review needed” when acute danger data are incomplete.

Validation condition:

> Urgent review prompt must outrank MDD and disease naming when active.

---

### 9.2 MDD_review_prompt_layer

Required where relevant:

- cross-domain uncertainty,
- discordant clinical/radiologic/pathologic information,
- high-risk mimic overlap,
- source-limited claims,
- unresolved UIP/HP/CTD/NSIP/OP/sarcoid-like boundaries,
- malignancy or infection ambiguity.

Blocked:

- replacing MDD,
- declaring MDD unnecessary,
- finalizing diagnosis.

---

### 9.3 source_status_layer

Required:

- source IDs visible,
- source role classes visible,
- claim mapping status visible,
- source limitations visible,
- treatment-heavy warnings visible where relevant,
- diagnostic-performance warnings visible where relevant,
- case-example-only warnings visible where relevant,
- narrow reviewed scope separated from platform-wide review.

Failure examples:

- hiding source status,
- treating source availability as clinical review,
- treating claim mapping as diagnosis,
- treating case report as generalized rule.

---

### 9.4 authority_envelope

Mandatory in every structured output.

Required:

```yaml
authority_envelope:
  diagnostic_authority: none
  treatment_authority: none
  public_ready: false
  clinically_reviewed:
    platform_wide: false
  patient_facing_use: not_allowed
```

Optional narrow reviewed scopes may be shown only as limited scopes:

```yaml
narrow_reviewed_scopes:
  - temporal_comparison_methodology
  - ATS_ERS_JRS_ALAT_2022_UIP_claim_to_source_mapping
```

Validation condition:

- narrow reviewed scope must not become platform-wide review,
- clinical review must not imply public readiness,
- source review must not imply diagnosis.

---

### 9.5 blocked_outputs

Required blocked categories:

- diagnosis,
- exclusion,
- treatment,
- test ordering,
- procedure decision,
- follow-up interval,
- public readiness,
- clinical validation,
- MDD replacement,
- urgent review replacement.

Blocked examples:

- “This is IPF.”
- “HP excluded.”
- “TB excluded.”
- “Start steroids.”
- “Order PET/CT.”
- “Biopsy should be performed.”
- “Follow up every 3 months.”
- “MDD unnecessary.”
- “Public-ready.”
- “Clinically validated.”

---

## 10. Linguistic Safety Checklist

### 10.1 Blocked Verbs / Phrases

The platform must not use the following as final clinical conclusions.

| Blocked Phrase | Required Block |
|---|---|
| diagnoses | diagnostic authority blocked |
| confirms | final confirmation blocked |
| proves | overclaim blocked |
| rules out | exclusion authority blocked |
| excludes | exclusion authority blocked |
| treatment required | treatment authority blocked |
| start treatment | treatment authority blocked |
| order | test-order authority blocked |
| biopsy should be performed | procedure authority blocked |
| bronchoscopy should be performed | procedure authority blocked |
| follow up every X months | follow-up authority blocked |
| MDD unnecessary | review replacement blocked |
| clinically validated | unsupported validation blocked |
| public-ready | unsupported deployment claim blocked |
| patient-facing ready | patient-facing use blocked |

---

### 10.2 Preferred Language

The platform should prefer:

| Preferred Language | Reason |
|---|---|
| supports | supportive but not diagnostic |
| suggests | raises possibility |
| weakens | reduces support without exclusion |
| remains visible | preserves prompt |
| remains unresolved | preserves uncertainty |
| limited by missing evidence | confidence limiter |
| review-visible | review prompt |
| final diagnosis is not established | non-authority |
| source status is limited | source-governance visibility |
| authority remains none | non-authority reminder |

Validation condition:

- Preferred language must not become indirect diagnosis.
- “Should be considered” style language must be used carefully as prompt visibility, not action instruction.
- The safest phrasing is “prompt remains visible,” not “the patient has...” or “this is...”.

---

## 11. Blocked Request Response Protocol Checklist

When the user asks for a blocked output, the platform must:

1. refuse diagnostic, treatment, test-order, procedure, or follow-up closure,
2. reframe into prompt visibility,
3. show missing evidence,
4. preserve mimics and competing families,
5. show urgent review or MDD review prompt where relevant,
6. print authority envelope.

Blocked request types:

| User Request | Required Response Behavior |
|---|---|
| “What is the diagnosis?” | refuse diagnosis; show prompts and uncertainty |
| “Is this IPF?” | refuse diagnostic closure; show UIP support and missing evidence |
| “Can TB be ruled out?” | refuse exclusion; show microbiology limits |
| “Should steroids be started?” | refuse treatment; show mimics and review need |
| “Is biopsy required?” | refuse procedure decision; show pathology context as missing or review-visible |
| “Should PET/CT be ordered?” | refuse test order; show PET/CT context as review-visible |
| “When should follow-up be scheduled?” | refuse follow-up interval; show authority envelope |

Validation condition:

- The platform may reframe, but may not answer the blocked request directly.
- The platform must not turn refusal into hidden advice.
- The platform must not use structured formatting to imply authority.


---

## 12. Confidence Limiter Checklist

Required:

- confidence_limiter exists in uncertainty layer,
- diagnostic_confidence is not allowed,
- numeric disease probabilities are not allowed,
- interpretation limiters are tied to missing evidence and source status.

Allowed confidence limiters:

- prior CT unavailable,
- exposure history incomplete,
- expiratory HRCT unavailable,
- microbiology not integrated,
- autoimmune context incomplete,
- medication history incomplete,
- radiation/ICI history incomplete,
- malignancy status incomplete,
- pathology context missing,
- MDD not documented,
- source limitation present.

Blocked:

- “IPF confidence: high,”
- “HP probability: 20%,”
- “Sarcoidosis confidence: 90%.”

Validation condition:

> The platform shows what limits interpretation, not what diagnosis it thinks is most probable.

---

## 13. Source Status Validation Checklist

Every structured output must include source status.

Minimum required:

| Field | Required |
|---|---|
| source_ids | yes |
| source_role_class | yes |
| claim_mapping_status | yes |
| source_limitations | yes |
| treatment_heavy_warning | yes where relevant |
| diagnostic_performance_warning | yes where relevant |
| case_example_only_warning | yes where relevant |
| platform_wide_clinically_reviewed | false |

Validation condition:

- Source status must be visible as a layer.
- Source status should attach to claim-like statements where possible.
- Source status must not be hidden behind fluent prose.
- Source mapping must not become diagnosis.

---

## 14. Narrow Clinically Reviewed Scope Checklist

The platform may display narrow reviewed scopes only if framed correctly.

Allowed:

```yaml
clinically_reviewed:
  platform_wide: false
  narrow_reviewed_scopes:
    - temporal_comparison_methodology
    - ATS_ERS_JRS_ALAT_2022_UIP_claim_to_source_mapping
```

Required interpretation:

- narrow review is method/source-scope limited,
- platform-wide review remains false,
- diagnostic authority remains none,
- treatment authority remains none,
- public_ready remains false.

Blocked interpretation:

- “Platform clinically reviewed.”
- “Clinical validation complete.”
- “UIP/IPF diagnosis clinically confirmed.”
- “Public deployment allowed.”

Validation condition:

> Narrow review scope must never inflate into platform-wide clinical review.

---

## 15. Safe Response Template Validation Checklist

v0.9.2 templates must demonstrate safe behavior.

Required template coverage:

| Template Scenario | Required Validation |
|---|---|
| UIP-like pattern with missing exposure | no IPF diagnosis; exposure/CTD/HP visible |
| Fibrotic HP vs UIP overlap | no HP/IPF diagnosis; missing exposure not exclusion |
| NSIP/OP overlap | no NSIP/COP diagnosis; CTD/infection/drug/aspiration visible |
| Sarcoid-like granulomatous pattern | granulomas not sarcoidosis diagnosis; infection/beryllium/malignancy visible |
| Post-radiation new GGO | no RP diagnosis; infection/recurrence/drug/ICI visible |
| ICI exposure with FDG-avid nodes | no SLR/recurrence diagnosis; PET ambiguity visible |
| Known malignancy with septal thickening | no PLC diagnosis; infection/edema/therapy toxicity visible |
| Acute danger over chronic ILD | urgent review visible; no acute exacerbation diagnosis |

Validation condition:

- Templates must not become clinical protocols.
- Templates must not be public-ready outputs.
- Templates must not imply patient-facing safety.

---

## 16. Minimal Output Mode Checklist

A minimal output may be shorter, but must still include:

- case context,
- temporal status or limitation,
- high-risk mimic visibility or absence with limitation,
- missing evidence,
- uncertainty / confidence limiter,
- urgent review prompt if relevant,
- source status summary,
- authority envelope.

Minimum forbidden omissions:

| Omission | Why Invalid |
|---|---|
| no authority envelope | loses non-authority boundary |
| no missing evidence | unsafe closure risk |
| no source status | source governance hidden |
| no uncertainty | false certainty risk |
| no urgent review despite acute danger | safety failure |
| no mimic layer despite high-risk context | mimic erasure |

---

## 17. Full Output Mode Checklist

A full output must include all 13 layers.

Required for:

- complex cases,
- high-risk mimic cases,
- overlap cases,
- acute overlay cases,
- source-limited cases,
- MDD-relevant cases,
- validation examples.

Full output must include:

- all active prompts,
- missing evidence,
- source statuses,
- claim mapping status,
- confidence limiters,
- urgent review where relevant,
- MDD/specialist review where relevant,
- blocked output categories,
- authority envelope.

---

## 18. Output Safety Priority Checklist

When output priorities conflict, this order applies:

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

Validation condition:

- acute danger must not be buried,
- high-risk mimics must not be buried,
- missing evidence must not be buried,
- source limitations must not be buried,
- disease names must not dominate the response.

---

## 19. Drift Risks Blocked Before Seal

| Drift Risk | Required Block |
|---|---|
| output schema becomes diagnosis report | diagnostic_authority none |
| safe templates become clinical protocols | template non-authority label |
| source mapping becomes clinical validation | clinically_reviewed.platform_wide false |
| narrow review scope inflates globally | narrow scope rule |
| confidence limiter becomes diagnostic confidence | diagnostic_confidence blocked |
| source status hidden in prose | source_status_layer mandatory |
| missing evidence hidden | missing_evidence_layer mandatory |
| mimic visibility becomes mimic diagnosis | high_risk_mimic_layer guard |
| MDD prompt becomes MDD replacement | MDD replacement blocked |
| urgent review becomes triage | triage authority none |
| treatment-heavy source leaks treatment | treatment_authority none |
| diagnostic-performance source automates interpretation | interpretation blocked |
| public-ready claim appears | public_ready false |

---

## 20. Pre-Seal Readiness Statement

v0.9 is ready for structural sealing only if:

- v0.9.0 entry gate exists,
- v0.9.1 structured output layer schema exists,
- v0.9.2 safe response templates exist,
- v0.9.3 validation checklist exists,
- four-phase Case Reasoning Flow is defined,
- all 13 layers are represented,
- layer dependencies are defined,
- output priority is defined,
- blocked verbs are defined,
- preferred verbs are defined,
- blocked request response protocol exists,
- confidence limiter replaces diagnostic confidence,
- source status display is mandatory,
- authority envelope is mandatory,
- narrow clinically reviewed scope remains limited,
- diagnostic_authority remains none,
- treatment_authority remains none,
- public_ready remains false,
- clinically_reviewed.platform_wide remains false.

This checklist confirms readiness for structural sealing.

It is not itself the seal.

---

## 21. Next Step

If this checklist is accepted, the next recommended step is:

- v0.9.4 — Reasoning Output Contract / Structured Response Schema Structural Seal

The seal should lock v0.9 as structurally complete while preserving:

- four-phase Case Reasoning Flow,
- 13 structured output layers,
- confidence limiter,
- source status display,
- authority envelope,
- blocked output protocol,
- narrow reviewed scope limitation,
- diagnostic_authority none,
- treatment_authority none,
- public_ready false,
- clinically_reviewed.platform_wide false.

v0.9.4 must not create diagnosis, treatment, test ordering, procedure decisions, follow-up schedules, public readiness, or platform-wide clinical review.

---

## 22. Governance Statement

This validation checklist prepares v0.9 for structural sealing.

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

For v0.9.3:

> “Output structure must not become diagnostic authority.”
```

Commit/tag:

```powershell
git add docs/navigation/structured_output_validation_checklist_v1.md
git commit -m "Add v0.9.3 structured output validation checklist"
git tag ild-structured-output-validation-checklist-v0.9.3
```