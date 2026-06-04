# ILD Reasoning Platform — Test Case Coverage Registry / Sync v1

Version: v0.5.7  
Status: structural_sync  
Scope: Tier 1 test case coverage registry  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  

---

## 1. Purpose

This registry synchronizes the Tier 1 test case coverage layer for the ILD Reasoning Platform.

It does not create diagnostic authority.  
It does not create treatment authority.  
It does not convert reasoning prompts into clinical decisions.  
It does not claim public readiness.

Its purpose is to make test coverage visible, auditable, and synchronized before the v0.5 coverage lock.

The platform principle remains:

> “It teaches clinicians to read change before naming disease.”

This means the test system is not only checking whether a disease label can be reached.  
It is checking whether the platform preserves the reasoning discipline required before naming disease:

- What changed?
- Compared to what?
- Over what time scale?
- Is this progression, exacerbation, infection, edema, hemorrhage, or mimic?
- What evidence is missing?
- What uncertainty remains?
- What should trigger urgent review?
- What should not be overcalled?

---

## 2. Registry Role

This file acts as the navigation and sync layer between:

1. the coverage matrix,
2. the Tier 1 test case packs,
3. the evidence governance layer,
4. the future lock checklist,
5. the future coverage seal.

It is a registry, not a clinical protocol.

It records what exists, what each pack is responsible for, and what must remain visible across all test cases.

---

## 3. Current Coverage Sources

| Layer | File | Role | Status |
|---|---|---|---|
| Coverage Matrix | `docs/data/schema/test_case_coverage_matrix_v1.md` | Master coverage map for test case families | active |
| Temporal Comparison Pack | `docs/test_cases/temporal_comparison_test_case_pack_v1.md` | Tests change-over-time reasoning | active |
| Superimposed Events Pack | `docs/test_cases/superimposed_events_test_case_pack_v1.md` | Tests overlapping / concurrent processes | active |
| UIP Pack | `docs/test_cases/uip_test_case_pack_v1.md` | Tests UIP reasoning boundaries and uncertainty | active |
| Acute Exacerbation / Infection / Edema Pack | `docs/test_cases/acute_exacerbation_infection_edema_test_case_pack_v1.md` | Tests acute worsening differential prompts | active |
| Superimposed Infection Pack | `docs/test_cases/superimposed_infection_test_case_pack_v1.md` | Tests infection-over-fibrosis reasoning and mimic visibility | active |
| Vascular Edema Hemorrhage Pack | `docs/test_cases/vascular_edema_hemorrhage_test_case_pack_v1.md` | Tests vascular, edema, and hemorrhage mimic/superimposition prompts | active |

---

## 4. Tier 1 Coverage Families

Tier 1 coverage is considered structurally present when the following reasoning families are represented:

| Coverage Family | Represented By | Registry Status |
|---|---|---|
| Temporal comparison | Temporal Comparison Pack | present |
| Baseline fibrotic pattern reasoning | UIP Pack | present |
| Uncertainty-preserving UIP reasoning | UIP Pack | present |
| Superimposed events | Superimposed Events Pack | present |
| Acute worsening | Acute Exacerbation / Infection / Edema Pack | present |
| Infection as superimposed process | Superimposed Infection Pack | present |
| Edema mimic / overlap | Acute Exacerbation Pack + Vascular Edema Hemorrhage Pack | present |
| Hemorrhage mimic / overlap | Vascular Edema Hemorrhage Pack | present |
| Mimics visibility | All Tier 1 packs | present |
| Missing evidence visibility | All Tier 1 packs | present |
| MDD / urgent review prompt visibility | All Tier 1 packs | present |
| Non-authority safety envelope | All Tier 1 packs | required |

---

## 5. Required Invariants Across All Test Case Packs

Every Tier 1 test case pack must preserve the following invariants.

### 5.1 Authority Invariants

Authority invariants:

- diagnostic_authority: none
- treatment_authority: none
- public_ready: false

No test case may imply that the platform diagnoses disease.  
No test case may imply that the platform recommends treatment.  
No test case may imply patient-facing readiness.

The platform may structure reasoning.  
It may expose uncertainty.  
It may suggest review prompts.  
It may identify missing evidence.  
It may identify mimics or competing explanations.

It must not replace clinician judgment, MDD, radiology expertise, pathology correlation, microbiology, laboratory review, or urgent clinical assessment.

---

### 5.2 Reasoning Invariants

Each pack should preserve:

- uncertainty_preserved: true
- missing_pieces_visible: true
- mimics_visible: true
- mdd_prompt_visible: true
- urgent_review_prompt_visible: true

The platform must show what is not known.

Examples of missing pieces include:

- absent prior imaging,
- incomplete HRCT technique information,
- unknown clinical timeline,
- unknown oxygen requirement,
- missing infection markers,
- missing microbiology,
- missing cardiac/volume status data,
- missing exposure history,
- missing medication history,
- missing autoimmune context,
- missing pathology or BAL where relevant.

---

### 5.3 Change-Before-Label Invariant

Each Tier 1 pack must reinforce the following reasoning order:

1. read the current pattern,
2. compare with prior state if available,
3. identify what changed,
4. identify whether change is focal, diffuse, acute, chronic, or mixed,
5. identify possible superimposed processes,
6. expose missing evidence,
7. preserve uncertainty,
8. prompt MDD or urgent review when appropriate,
9. avoid premature disease naming.

This protects the platform’s central teaching principle:

> read change before naming disease.

---

## 6. Pack Responsibilities

### 6.1 Temporal Comparison Pack

Primary responsibility:

- establish whether change exists,
- distinguish stable vs progressive vs newly superimposed abnormality,
- prevent single-timepoint overconfidence,
- preserve prior-imaging dependency.

Must keep visible:

- requires_prior_comparison_when_available: true
- single_scan_limitations_visible: true
- progression_not_assumed_without_comparison: true

---

### 6.2 Superimposed Events Pack

Primary responsibility:

- identify that more than one process may coexist,
- prevent false single-diagnosis closure,
- keep simultaneous processes visible.

Must keep visible:

- multiple_processes_allowed: true
- single_label_closure_blocked: true
- superimposition_prompt_visible: true

---

### 6.3 UIP Test Case Pack

Primary responsibility:

- test UIP-compatible reasoning without converting imaging pattern into final diagnosis,
- preserve uncertainty around probable/indeterminate/alternative patterns,
- prevent overclaiming IPF from imaging alone.

Must keep visible:

- uip_pattern_not_equal_final_diagnosis: true
- clinical_context_required: true
- mdd_prompt_visible: true

---

### 6.4 Acute Exacerbation / Infection / Edema Pack

Primary responsibility:

- test acute worsening reasoning,
- separate acute exacerbation prompts from infection and edema mimics,
- prevent premature acute exacerbation labeling.

Must keep visible:

- acute_exacerbation_not_default: true
- infection_mimic_visible: true
- edema_mimic_visible: true
- urgent_review_prompt_visible: true

---

### 6.5 Superimposed Infection Pack

Primary responsibility:

- test infection as an overlapping process on chronic ILD,
- prevent infection from erasing baseline fibrotic disease,
- prevent baseline fibrosis from hiding infection.

Must keep visible:

- infection_can_be_superimposed: true
- baseline_ild_preserved: true
- microbiology_and_clinical_correlation_needed: true

---

### 6.6 Vascular Edema Hemorrhage Pack

Primary responsibility:

- test vascular, edema, and hemorrhage mimics,
- prevent ground-glass opacity from being treated as a single-process sign,
- expose urgent review pathways.

Must keep visible:

- vascular_mimic_visible: true
- edema_mimic_visible: true
- hemorrhage_mimic_visible: true
- urgent_review_prompt_visible: true

---

## 7. Sync Rules

The registry is considered synchronized only if:

- coverage_matrix_present: true
- all_tier_1_pack_files_present: true
- all_pack_roles_declared: true
- authority_invariants_declared: true
- reasoning_invariants_declared: true
- change_before_label_invariant_declared: true
- missing_evidence_visibility_required: true
- mimic_visibility_required: true
- mdd_prompt_visibility_required: true
- urgent_review_prompt_visibility_required: true
- public_ready_false: true

Any future test case pack added under v0.5 must be registered here before the coverage seal.

---

## 8. Drift Risks This Registry Blocks

This registry exists to block the following failure modes:

| Drift Risk | Registry Response |
|---|---|
| Test packs become isolated documents | Registry links all active packs |
| Coverage matrix diverges from test packs | Registry syncs pack roles to matrix |
| Disease labels become too authoritative | Authority invariants remain explicit |
| UIP becomes treated as final diagnosis | UIP pack responsibility blocks overclaim |
| Acute exacerbation becomes default label | Acute pack requires mimic visibility |
| Infection/edema/hemorrhage disappear | Dedicated mimic packs remain registered |
| Missing evidence is hidden | Missing evidence invariant required |
| MDD prompt becomes optional | MDD visibility required |
| Urgent review prompts disappear | Urgent review visibility required |
| Platform becomes public-facing too early | public_ready remains false |

---

## 9. Registry Completion Statement

Tier 1 test case coverage is structurally synchronized when the following files are present and aligned:

- `docs/data/schema/test_case_coverage_matrix_v1.md`
- `docs/test_cases/temporal_comparison_test_case_pack_v1.md`
- `docs/test_cases/superimposed_events_test_case_pack_v1.md`
- `docs/test_cases/uip_test_case_pack_v1.md`
- `docs/test_cases/acute_exacerbation_infection_edema_test_case_pack_v1.md`
- `docs/test_cases/superimposed_infection_test_case_pack_v1.md`
- `docs/test_cases/vascular_edema_hemorrhage_test_case_pack_v1.md`
- `docs/navigation/test_case_coverage_registry_v1.md`

This does not seal v0.5.

It prepares the system for:

- v0.5.8 — Test Case Coverage Lock Checklist
- v0.5.9 — Test Case Coverage Seal

---

## 10. Governance Statement

The ILD Reasoning Platform remains an evidence-governed clinical reasoning platform.

It is not a disease atlas alone.  
It is not a diagnostic engine.  
It is not a treatment engine.  
It is not public-ready.

Its purpose is to train and structure the clinician’s reasoning posture:

- compare before concluding,
- preserve uncertainty,
- expose mimics,
- show missing evidence,
- prompt multidisciplinary discussion,
- escalate urgent review when needed,
- and read change before naming disease.