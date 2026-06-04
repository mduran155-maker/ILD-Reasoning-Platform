# ILD Reasoning Platform — UIP Parity Lock Checklist v1

Version: v0.6.8  
Status: pre_seal_lock_checklist  
Scope: UIP parity upgrade lock readiness  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Source Review Date: 2026-06-04  

---

## 1. Purpose

This checklist verifies that the v0.6 UIP Parity Upgrade is ready for structural sealing.

It does not seal v0.6.  
It does not diagnose UIP.  
It does not diagnose IPF.  
It does not recommend treatment.  
It does not create public readiness.  
It does not replace radiologist interpretation, pathology review, clinical correlation, microbiology, pulmonology, rheumatology, occupational medicine, MDD, or urgent clinical assessment.

Its role is to confirm that the UIP parity chain is present, synchronized, source-governed, testable, and non-authoritative before the v0.6.9 seal.

The platform principle remains:

> “It teaches clinicians to read change before naming disease.”

For v0.6, the locked working expansion is:

> “Read pattern, boundary, mimic, time, missing evidence, review need, and uncertainty before naming UIP.”

---

## 2. v0.6 Chain Under Lock Review

The following v0.6 files must be present before sealing.

| Version | File | Role | Lock Readiness |
|---|---|---|---|
| v0.6.0 | `docs/navigation/uip_parity_upgrade_entry_gate_v1.md` | UIP parity entry gate and scope contract | required |
| v0.6.1 | `docs/navigation/uip_source_anchor_review_map_v1.md` | Source anchor governance map | required |
| v0.6.2 | `docs/data/schema/uip_pattern_boundary_matrix_v1.md` | UIP pattern boundary matrix | required |
| v0.6.3 | `docs/data/schema/uip_reasoning_parity_rules_v1.md` | UIP reasoning parity rules | required |
| v0.6.4 | `docs/data/schema/uip_mimic_superimposed_process_parity_v1.md` | Mimic and superimposed process parity | required |
| v0.6.5 | `docs/data/schema/uip_temporal_comparison_parity_v1.md` | Temporal comparison parity | required |
| v0.6.6 | `docs/data/schema/uip_mdd_missing_evidence_prompt_parity_v1.md` | MDD and missing evidence prompt parity | required |
| v0.6.7 | `docs/test_cases/uip_parity_upgrade_test_case_pack_v1.md` | UIP parity upgraded test cases | required |
| v0.6.8 | `docs/navigation/uip_parity_lock_checklist_v1.md` | Pre-seal lock checklist | current |

Lock condition:

- All v0.6 files must exist.
- Each file must preserve non-authority.
- Each file must preserve uncertainty, missing evidence, mimic visibility, MDD prompts, and urgent review prompts where relevant.
- No v0.6 file may weaken v0.3, v0.4, or v0.5 seals.

---

## 3. Prior Seal Inheritance Checklist

v0.6 must inherit the following sealed layers.

| Prior Layer | Required Inheritance |
|---|---|
| v0.3 Superimposed Events Core | Multiple processes may coexist; single-label closure remains blocked |
| v0.4 Evidence Layer / Source Review Governance | Source-sensitive claims require anchor/review/limitations |
| v0.5 Test Case Coverage Expansion | Missing evidence, mimics, MDD, urgent review, and non-authority remain visible |

Lock condition:

- v0.6 must not make UIP reasoning a single-label diagnostic engine.
- v0.6 must not bypass source governance.
- v0.6 must not hide missing evidence or mimics.
- v0.6 must not convert test coverage into public readiness.

---

## 4. Source Anchor Lock Checklist

The following source anchors must be declared and role-separated.

| Source Anchor ID | Required Role | Lock Readiness |
|---|---|---|
| UIP_SRC_2018_ATS_ERS_JRS_ALAT_DX | Official guideline anchor for UIP-facing pattern categories and diagnostic pathway framing | required |
| UIP_SRC_2022_ATS_ERS_JRS_ALAT_IPF_PPF | Current update / source hierarchy anchor | required |
| UIP_SRC_2018_FLEISCHNER_WHITE_PAPER | Verified comparative IPF/UIP diagnostic criteria anchor | required |
| UIP_SRC_2020_FLEISCHNER_ILA_POSITION_PAPER | Incidental ILA / early fibrotic abnormality / progression support anchor | required as auxiliary |
| UIP_SRC_INTERNAL_V03_SUPERIMPOSED_EVENTS_CORE | Internal overlap reasoning anchor | required |
| UIP_SRC_INTERNAL_V04_SOURCE_GOVERNANCE | Internal source governance anchor | required |
| UIP_SRC_INTERNAL_V05_TEST_COVERAGE_SEAL | Internal test coverage seal anchor | required |

Lock condition:

- Official guideline anchors must not be replaced by internal governance anchors.
- Fleischner 2018 may be used as a verified comparative anchor.
- Fleischner 2020 ILA may be used as an auxiliary source for incidental/early fibrotic abnormality and follow-up reasoning, not as a primary UIP diagnostic criteria source.
- Any guideline-sensitive claim must remain source-governed.
- Source anchoring must not create diagnostic authority.

---

## 5. Authority Lock Checklist

The following constraints must remain true across all v0.6 files.

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
| replacement_of_rheumatologist | not allowed |
| replacement_of_occupational_medicine_review | not allowed |
| replacement_of_microbiology | not allowed |
| replacement_of_MDD | not allowed |
| replacement_of_urgent_review | not allowed |

Lock condition:

- No v0.6 document may imply final diagnosis.
- No v0.6 document may imply treatment selection.
- No v0.6 document may imply public or patient-facing readiness.
- No v0.6 document may erase the need for clinician review, MDD, pathology, microbiology, or urgent clinical assessment where appropriate.

---

## 6. Pattern Boundary Lock Checklist

The pattern boundary layer is lock-ready only if the following pattern states remain represented.

| Pattern State | Required Lock Behavior |
|---|---|
| UIP_PATTERN_CANDIDATE | May acknowledge UIP-compatible features but must not diagnose UIP/IPF |
| PROBABLE_UIP_PATTERN_CANDIDATE | Must not automatically upgrade to UIP |
| INDETERMINATE_FOR_UIP | Must preserve uncertainty |
| ALTERNATIVE_PATTERN_PROMPT | Must block premature UIP/IPF closure |
| ACUTE_SUPERIMPOSED_MODIFIER | Must separate acute overlay from chronic progression |

Lock condition:

- UIP pattern compatibility must not become IPF diagnosis.
- Probable UIP must remain boundary-limited.
- Indeterminate pattern must not be forced into a confident label.
- Alternative features must remain capable of vetoing closure.
- Acute overlay must not be collapsed into chronic fibrosis progression.

---

## 7. Reasoning Parity Lock Checklist

The reasoning parity layer is lock-ready only if all global parity rules remain active.

Required parity rules:

- pattern is not diagnosis,
- IPF is not inferred from imaging alone,
- boundary uncertainty is preserved,
- missing evidence remains visible,
- mimics remain visible,
- MDD prompt remains visible where relevant,
- urgent review remains visible where relevant,
- temporal comparison matters,
- boundary vetoes override closure,
- treatment logic is blocked.

Lock condition:

- Every UIP-facing output must preserve reasoning posture before disease naming.
- Allowed language must remain cautious and pattern-facing.
- Blocked language must remain blocked.

---

## 8. Mimic and Superimposed Process Lock Checklist

The mimic / overlap layer is lock-ready only if the following remain visible where relevant.

| Mimic / Overlap Family | Required Visibility |
|---|---|
| Infection | visible as mimic or superimposed process |
| Edema | visible as mimic or superimposed process |
| Hemorrhage | visible as mimic or urgent review concern |
| Vascular process | visible as urgent review concern where relevant |
| Acute exacerbation prompt | visible as possibility, not confirmed by imaging alone |
| Hypersensitivity pneumonitis | visible when exposure gap, mosaic attenuation, air-trapping, or upper/mid-lung features exist |
| CTD-ILD | visible when autoimmune context is missing or suggestive |
| NSIP | visible when GGO/subpleural sparing/less typical UIP distribution exists |
| Sarcoidosis | visible when upper-lung/perilymphatic/lymphadenopathy features exist |
| Occupational / asbestosis / pneumoconiosis | visible when exposure or pleural plaque context exists |
| Drug toxicity | visible when medication or therapy history is missing or suggestive |
| Aspiration / organizing pneumonia concern | visible when consolidation or aspiration context exists |

Lock condition:

- Mimic prompts must not become diagnoses.
- Mimic prompts must not be hidden.
- Acute overlay must not erase chronic baseline.
- Chronic baseline must not erase acute overlay.
- Missing evidence must not be treated as exclusion.

---

## 9. Temporal Comparison Lock Checklist

The temporal layer is lock-ready only if the following remain true.

| Temporal Rule | Required State |
|---|---|
| Progression requires comparison | true |
| Stability requires comparison | true |
| Prior unavailable blocks confident progression/stability | true |
| Feature-level change is separated | true |
| New GGO/consolidation triggers acute overlay review | true |
| Technique-limited comparison preserves caution | true |
| Clinical timeline remains visible | true |
| Working diagnosis remains reviewable over time | true |
| Longitudinal discordance triggers re-review | true |

Lock condition:

- Progression must not be claimed from a single scan.
- Stability must not be claimed from a single scan.
- New GGO/consolidation must not default to UIP progression.
- Technique differences must not be hidden.
- Prior working diagnosis must not become immutable.

---

## 10. MDD and Missing Evidence Lock Checklist

The MDD / missing evidence layer is lock-ready only if the following remain represented.

| Missing Evidence Domain | Required Visibility |
|---|---|
| Prior imaging | visible |
| Clinical timeline | visible |
| HRCT technique context | visible |
| Prone / expiratory imaging limitation where relevant | visible |
| Exposure history | visible |
| Autoimmune context | visible |
| Medication history | visible |
| Infection data | visible |
| Cardiac / volume status | visible |
| Hemorrhage context | visible |
| Vascular context | visible |
| Pathology context | visible where relevant |
| MDD context | visible where relevant |
| Longitudinal behaviour | visible where relevant |

MDD prompt states that must remain available:

- MDD_NOT_TRIGGERED_BY_CONTEXT,
- MDD_PROMPT_VISIBLE,
- MDD_ESCALATION_PROMPT,
- MDD_REVIEW_AFTER_BIOPSY_PROMPT,
- MDD_WORKING_DIAGNOSIS_PROMPT,
- MDD_RE_REVIEW_PROMPT,
- MDD_URGENT_CONTEXT_PROMPT.

Lock condition:

- Missing evidence must not be silently filled.
- Missing evidence must not be treated as negative evidence.
- MDD prompt must be context-aware.
- MDD must not be hidden when uncertainty, discordance, alternative pattern, biopsy integration, working diagnosis, or re-review trigger exists.
- MDD must not be mechanically forced when no trigger exists.

---

## 11. Working Diagnosis Lock Checklist

Working diagnosis handling is lock-ready only if the following remain true.

| Safeguard | Required State |
|---|---|
| working_diagnosis_not_final | true |
| confidence_level_visible | true |
| missing_evidence_visible | true |
| alternative_explanations_visible | true |
| reviewability_visible | true |
| re_review_possible | true |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |

Lock condition:

- Working diagnosis must remain provisional and reviewable.
- Working diagnosis must not become final diagnosis.
- Working diagnosis must not authorize treatment.
- Prior working diagnosis must be re-openable when new evidence appears.

---

## 12. Test Case Upgrade Lock Checklist

The v0.6.7 test case pack is lock-ready only if all major parity domains are tested.

| Test Coverage Domain | Required Coverage |
|---|---|
| UIP pattern non-diagnosis | present |
| Probable UIP non-upgrade | present |
| Indeterminate uncertainty preservation | present |
| Alternative pattern closure block | present |
| Mimic and superimposed process visibility | present |
| Acute overlay separation | present |
| Prior unavailable temporal humility | present |
| Feature-level progression without diagnosis | present |
| Technique-limited comparison caution | present |
| Working diagnosis reviewability | present |
| Longitudinal re-review | present |
| Incidental ILA non-diagnostic handling | present |
| Missing evidence visibility | present |
| MDD context-aware prompt | present |
| Urgent review visibility where relevant | present |
| Non-authority safety envelope | present across all test cases |

Lock condition:

- Every test case must include diagnostic_authority, treatment_authority, and public_ready fields.
- Required values must remain:
  - diagnostic_authority: none
  - treatment_authority: none
  - public_ready: false
- Test cases must contain both allowed and blocked output expectations.
- Test cases must not become clinical protocols.

---

## 13. Language Guardrail Lock Checklist

Allowed language must remain pattern/reasoning-facing.

Allowed posture examples:

- “UIP-pattern compatible features are present.”
- “Probable UIP-pattern reasoning may be considered.”
- “Indeterminate for UIP-pattern reasoning.”
- “Alternative pattern prompt is triggered.”
- “Acute superimposed process prompt is triggered.”
- “Progression cannot be determined without prior comparison.”
- “Missing evidence limits confidence.”
- “MDD prompt remains visible.”
- “Working diagnosis remains provisional and reviewable.”
- “Final diagnosis is not established by this platform.”

Blocked posture examples:

- “UIP diagnosed.”
- “IPF confirmed.”
- “Probable UIP equals UIP.”
- “Indeterminate UIP resolved automatically.”
- “Alternative diagnosis excluded.”
- “Acute exacerbation confirmed by imaging alone.”
- “Progression confirmed without prior comparison.”
- “Treatment should be started.”
- “Biopsy should be performed.”
- “MDD unnecessary” when uncertainty triggers exist.
- “Public-ready.”
- “Patient-facing diagnosis.”

Lock condition:

- Blocked language must not appear as platform-approved output.
- Allowed language must preserve uncertainty and review need.

---

## 14. Drift Risks Blocked Before Seal

This checklist blocks the following risks before v0.6.9.

| Drift Risk | Required Block |
|---|---|
| UIP parity becomes diagnostic authority | diagnostic_authority none |
| UIP pattern becomes IPF diagnosis | imaging-alone inference blocked |
| Probable UIP auto-upgrades | probable UIP non-upgrade required |
| Indeterminate state gets forced | uncertainty preservation required |
| Alternative features ignored | closure veto required |
| Acute overlay becomes chronic progression | acute overlay separation required |
| Mimics disappear | mimic visibility required |
| Missing evidence disappears | missing evidence visibility required |
| MDD becomes noisy or absent | context-aware MDD required |
| Working diagnosis becomes permanent | reviewability required |
| Progression claimed without prior | temporal comparison required |
| Technique limitations hidden | technique caution required |
| Treatment logic leaks in | treatment_authority none |
| Public readiness implied | public_ready false |
| Test cases become clinical protocols | non-authority envelope required |

---

## 15. Pre-Seal Readiness Statement

The v0.6 UIP Parity Upgrade is ready for v0.6.9 sealing only if:

- v0.6.0 through v0.6.7 exist,
- source anchors are mapped and role-separated,
- verified Fleischner 2018 comparative anchor is reflected,
- Fleischner 2020 ILA source is treated as auxiliary, not primary UIP diagnostic criteria,
- pattern-boundary matrix exists,
- reasoning parity rules exist,
- mimic and superimposed-process parity exists,
- temporal comparison parity exists,
- MDD and missing-evidence parity exists,
- upgraded UIP parity test cases exist,
- diagnostic_authority remains none,
- treatment_authority remains none,
- public_ready remains false,
- uncertainty is preserved,
- missing evidence remains visible,
- mimics remain visible,
- MDD prompts remain visible where relevant,
- urgent review prompts remain visible where relevant,
- UIP pattern does not equal final diagnosis,
- IPF is not inferred from imaging alone,
- treatment logic is blocked,
- public readiness is not implied.

This checklist confirms readiness for sealing.

It is not itself the seal.

---

## 16. Next Step

If this checklist is accepted, the next step is:

- v0.6.9 — UIP Parity Seal

The seal should lock v0.6 as structurally complete while preserving all non-authority, uncertainty, source-governance, missing-evidence, mimic, MDD, urgent-review, and testability constraints.

After v0.6.9, the roadmap may proceed to the next platform layer.

Recommended next phase after seal:

- v0.7 — Differential Reasoning Expansion / Non-UIP Fibrotic ILD Parity Entry

The next phase should not begin until v0.6 is structurally sealed.

---

## 17. Governance Statement

The UIP Parity Lock Checklist prepares v0.6 for structural sealing.

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

It teaches clinicians to read pattern, boundary, mimic, time, missing evidence, review need, uncertainty, and change before naming UIP.