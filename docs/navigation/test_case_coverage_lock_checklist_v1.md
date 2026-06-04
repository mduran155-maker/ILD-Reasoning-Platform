# ILD Reasoning Platform — Test Case Coverage Lock Checklist v1

Version: v0.5.8  
Status: pre_seal_lock_checklist  
Scope: Tier 1 test case coverage lock readiness  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  

---

## 1. Purpose

This checklist verifies that the Tier 1 test case coverage layer is ready for structural sealing.

It does not seal v0.5.  
It does not create diagnostic authority.  
It does not create treatment authority.  
It does not create public readiness.

Its role is to confirm that the coverage matrix, test case packs, registry, and governance invariants are aligned before the v0.5.9 coverage seal.

The platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The checklist therefore verifies not only that test packs exist, but that they preserve the reasoning discipline of the platform.

---

## 2. Lock Readiness Scope

This checklist applies to the Tier 1 test case coverage expansion layer.

Included files:

- `docs/data/schema/test_case_coverage_matrix_v1.md`
- `docs/test_cases/temporal_comparison_test_case_pack_v1.md`
- `docs/test_cases/superimposed_events_test_case_pack_v1.md`
- `docs/test_cases/uip_test_case_pack_v1.md`
- `docs/test_cases/acute_exacerbation_infection_edema_test_case_pack_v1.md`
- `docs/test_cases/superimposed_infection_test_case_pack_v1.md`
- `docs/test_cases/vascular_edema_hemorrhage_test_case_pack_v1.md`
- `docs/navigation/test_case_coverage_registry_v1.md`
- `docs/navigation/test_case_coverage_lock_checklist_v1.md`

Excluded from this lock:

- diagnostic algorithms,
- treatment recommendations,
- public-facing clinical deployment,
- patient-facing output,
- automated clinical decision-making,
- quantitative performance claims,
- validation against real patient cohorts.

---

## 3. Authority Lock Checklist

The following authority constraints must remain true across all Tier 1 test case materials.

| Check | Required State | Status |
|---|---|---|
| Diagnostic authority | none | required |
| Treatment authority | none | required |
| Public readiness | false | required |
| Patient-facing use | not allowed | required |
| Replacement of clinician judgment | not allowed | required |
| Replacement of MDD | not allowed | required |
| Replacement of radiology/pathology/clinical correlation | not allowed | required |

Lock condition:

- No Tier 1 test case file may imply final diagnosis.
- No Tier 1 test case file may imply treatment selection.
- No Tier 1 test case file may imply public or patient-facing readiness.
- No Tier 1 test case file may erase the need for clinician review, MDD, or urgent clinical assessment where appropriate.

---

## 4. Coverage Presence Checklist

Tier 1 coverage is lock-ready only if the following coverage families are present.

| Coverage Family | Expected Source | Lock Readiness |
|---|---|---|
| Temporal comparison | Temporal Comparison Pack | required |
| Baseline fibrotic pattern reasoning | UIP Pack | required |
| UIP uncertainty preservation | UIP Pack | required |
| Superimposed events | Superimposed Events Pack | required |
| Acute worsening differential reasoning | Acute Exacerbation / Infection / Edema Pack | required |
| Superimposed infection reasoning | Superimposed Infection Pack | required |
| Edema mimic visibility | Acute Exacerbation Pack + Vascular Edema Hemorrhage Pack | required |
| Hemorrhage mimic visibility | Vascular Edema Hemorrhage Pack | required |
| Vascular mimic visibility | Vascular Edema Hemorrhage Pack | required |
| Missing evidence visibility | All Tier 1 packs | required |
| MDD prompt visibility | All relevant Tier 1 packs | required |
| Urgent review prompt visibility | Acute / infection / edema / hemorrhage / vascular packs | required |

Lock condition:

- All listed families must be represented.
- No major Tier 1 family may remain orphaned.
- No mimic family may be hidden inside a single disease label.
- No acute worsening scenario may default to one explanation without visible alternatives.

---

## 5. Registry Sync Checklist

The registry file must correctly synchronize the test case coverage layer.

Registry file:

- `docs/navigation/test_case_coverage_registry_v1.md`

Required registry properties:

| Registry Check | Required State |
|---|---|
| Coverage matrix listed | true |
| All Tier 1 packs listed | true |
| Pack responsibilities declared | true |
| Authority invariants declared | true |
| Reasoning invariants declared | true |
| Change-before-label invariant declared | true |
| Mimics visibility required | true |
| Missing pieces visibility required | true |
| MDD prompt visibility required | true |
| Urgent review prompt visibility required | true |
| public_ready remains false | true |

Lock condition:

- The registry must act as the navigation and sync authority for v0.5 Tier 1 coverage.
- The registry must not create new clinical authority.
- The registry must not convert test coverage into public readiness.

---

## 6. Reasoning Discipline Checklist

Every Tier 1 pack must preserve the platform’s reasoning order.

Required reasoning order:

1. read the current pattern,
2. compare with prior state if available,
3. identify what changed,
4. identify the time scale of change,
5. identify whether the process is focal, diffuse, acute, chronic, or mixed,
6. identify possible superimposed processes,
7. expose missing evidence,
8. preserve uncertainty,
9. keep mimics visible,
10. prompt MDD or urgent review when appropriate,
11. avoid premature disease naming.

Lock condition:

- Disease naming must not precede change reading.
- Superimposed processes must remain possible.
- Mimics must not be collapsed into a single preferred diagnosis.
- Missing evidence must remain visible.

---

## 7. Missing Evidence Checklist

The test case layer is lock-ready only if missing evidence remains visible.

Examples of missing evidence that should remain visible where relevant:

- prior imaging unavailable,
- incomplete temporal comparison,
- unknown clinical timeline,
- missing HRCT technique details,
- missing oxygen requirement,
- missing fever or inflammatory marker data,
- missing microbiology,
- missing BAL/pathology where relevant,
- missing cardiac or volume status data,
- missing medication history,
- missing exposure history,
- missing autoimmune context,
- missing pulmonary function trend,
- missing treatment history,
- missing MDD review.

Lock condition:

- Missing evidence must not be silently assumed.
- Missing evidence must not be filled by unsupported inference.
- Missing evidence must not be hidden behind confident labels.

---

## 8. Mimic and Overlap Checklist

The Tier 1 layer is lock-ready only if mimics and overlapping processes remain visible.

Required mimic/overlap visibility:

| Process | Visibility Requirement |
|---|---|
| Infection | visible as mimic or superimposed process |
| Edema | visible as mimic or superimposed process |
| Hemorrhage | visible as mimic or superimposed process |
| Vascular process | visible as mimic or urgent review trigger |
| Acute exacerbation | visible but not default |
| Fibrotic progression | visible but not assumed without comparison |
| UIP pattern | visible but not treated as final diagnosis |
| Multiple concurrent processes | allowed and visible |

Lock condition:

- Ground-glass opacity must not be treated as a single-process sign.
- Acute worsening must not default to acute exacerbation.
- Infection must not erase baseline ILD.
- Baseline ILD must not hide infection.
- Edema, hemorrhage, and vascular processes must remain review-visible.

---

## 9. MDD and Urgent Review Checklist

The platform must preserve review prompts.

Required prompts:

| Prompt Type | Required Visibility |
|---|---|
| MDD review | visible for uncertain ILD pattern reasoning |
| Radiology correlation | visible where imaging pattern is uncertain |
| Clinical correlation | visible across all clinical reasoning packs |
| Microbiology correlation | visible for infection scenarios |
| Cardiac/volume assessment | visible for edema scenarios |
| Urgent clinical review | visible for acute worsening, vascular concern, hemorrhage, severe infection, or unstable clinical context |

Lock condition:

- MDD must not be optionalized away in uncertain ILD reasoning.
- Urgent review prompts must not be hidden when acute or vascular danger is possible.
- Review prompts must be framed as safety prompts, not automated management instructions.

---

## 10. Drift Block Checklist

The lock checklist blocks the following drift modes before sealing.

| Drift Mode | Required Block |
|---|---|
| Test packs drift away from matrix | registry sync required |
| Matrix becomes stale | registry links matrix to active packs |
| Disease atlas replaces reasoning platform | change-before-label invariant required |
| UIP becomes final diagnosis | UIP non-authority required |
| Acute exacerbation becomes default | mimic visibility required |
| Superimposed events collapse into one label | multiple-process visibility required |
| Missing evidence becomes invisible | missing pieces checklist required |
| MDD disappears | MDD prompt required |
| Urgent review disappears | urgent review prompt required |
| Public readiness is implied | public_ready false required |
| Diagnostic authority appears | diagnostic_authority none required |
| Treatment authority appears | treatment_authority none required |

---

## 11. Pre-Seal Readiness Statement

The Tier 1 test case coverage layer is ready for v0.5.9 sealing only if:

- the coverage matrix exists,
- all Tier 1 test case packs exist,
- the registry exists,
- all packs are synchronized through the registry,
- diagnostic authority remains none,
- treatment authority remains none,
- public_ready remains false,
- uncertainty is preserved,
- missing pieces remain visible,
- mimics remain visible,
- MDD prompts remain visible,
- urgent review prompts remain visible,
- change is read before disease is named.

This checklist confirms readiness for sealing.

It is not itself the seal.

---

## 12. Next Step

If this checklist is accepted, the next step is:

- v0.5.9 — Test Case Coverage Seal

The seal should lock the Tier 1 test case coverage expansion as structurally complete while preserving all non-authority and uncertainty constraints.

After v0.5.9, the roadmap may proceed to:

- v0.6 — UIP Parity Upgrade

---

## 13. Governance Statement

The ILD Reasoning Platform remains an evidence-governed clinical reasoning platform.

It teaches clinicians to read change before naming disease.

It does not diagnose.  
It does not treat.  
It does not replace clinician judgment.  
It does not replace MDD.  
It does not hide uncertainty.  
It does not hide missing evidence.  
It does not hide mimics.  
It does not claim public readiness.

The v0.5.8 checklist exists to make those limits explicit before the v0.5.9 structural seal.