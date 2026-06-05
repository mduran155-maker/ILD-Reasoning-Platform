# ILD Reasoning Platform — MDD Preparation Package Section Semantics / Safe Formatting Rules v1

Version: v0.13.2  
Status: mdd_preparation_package_section_semantics_safe_formatting_rules  
Scope: Safe section titles, formatting rules, badge semantics, table semantics, ordering rules, unsafe report-like format blocks, and MDD preparation language constraints  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This document defines safe section semantics and formatting rules for v0.13 — Safe Session Export / MDD Preparation Package Contract.

It follows:

- `docs/navigation/safe_session_export_mdd_preparation_entry_gate_v1.md`
- `docs/data/schema/safe_session_export_object_schema_package_structure_v1.md`
- `docs/navigation/project_status_roadmap_checkpoint_v0_12.md`
- `docs/navigation/case_assembly_reasoning_session_structural_seal_v1.md`
- `docs/navigation/evidence_intake_structural_seal_v1.md`
- `docs/navigation/clinician_workspace_structural_seal_v1.md`
- `docs/navigation/reasoning_output_contract_structural_seal_v1.md`

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

Its purpose is to ensure that safe session exports and MDD preparation packages cannot visually, linguistically, or structurally resemble diagnostic reports, treatment plans, test-order recommendations, procedure recommendations, follow-up schedules, triage reports, public-ready documents, patient-facing summaries, or clinical validation certificates.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.13 rule remains:

> “A safe session export may prepare discussion, but it must not become diagnosis, treatment, order, procedure decision, follow-up schedule, triage report, patient-facing output, public-ready output, or clinical validation.”

For v0.13.2:

> “A safe MDD preparation package is valid only if its headings, tables, badges, ordering, language, notes, appendices, and visual hierarchy communicate review preparation rather than clinical conclusion.”

---

## 2. Global Formatting Contract

Every export section, table, badge, heading, note, appendix, footer, and summary block must preserve:

| Constraint | Required State |
|---|---|
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
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
| replacement_of_clinician | not_allowed |
| replacement_of_specialist_review | not_allowed |
| replacement_of_urgent_review | not_allowed |

No formatting choice may imply clinical authority.

No heading may imply diagnosis.

No table column may imply ranking or probability.

No badge may imply confirmation or exclusion.

No section order may place disease names before limitation, missingness, source status, and authority boundaries.

---

## 3. Safe Export Visual Identity

The MDD preparation package may visually appear as:

- review preparation package,
- governed reasoning state export,
- discussion support artifact,
- source-status-aware case summary,
- missing-evidence-aware review packet,
- MDD preparation worksheet,
- clinician review support document.

It must not visually appear as:

- radiology report,
- pathology report,
- diagnostic impression,
- clinical impression,
- discharge summary,
- treatment plan,
- test order sheet,
- procedure recommendation,
- follow-up instruction sheet,
- triage summary,
- patient letter,
- patient education handout,
- clinical validation certificate,
- final signed report.

Visual identity rule:

> The export must look like a governed review preparation artifact, not a final clinical report.

---

## 4. Required Section Order

A safe export should use this section order:

1. Export Header
2. Non-Authority Statement
3. Authority Envelope
4. No-Decision Statement
5. Blocked Output Notice
6. Snapshot Export Reference
7. Case Context Summary
8. Temporal Context
9. Source Status and Limitations
10. Missing Evidence
11. Confidence Limiters
12. High-Risk Mimic Visibility
13. Overlap and Unresolved Boundaries
14. Review Prompts
15. Audit References
16. Optional Clinician Notes
17. Optional Source Reference Appendix
18. Optional Audit Reference Appendix

Required early safety placement:

- non-authority statement before reasoning content,
- authority envelope before disease-facing content,
- no-decision statement before reasoning content,
- blocked output notice before reasoning content.

Blocked ordering:

- disease-facing summary before non-authority statement,
- “Key Impression” section before safety boundaries,
- “Conclusion” section anywhere,
- “Recommendations” section anywhere,
- action checklist before missing evidence,
- source appendix without source limitations,
- no-decision statement only in small footer,
- authority envelope hidden at end only.

Ordering rule:

> Safety and authority boundaries must appear before reasoning content.

---

## 5. Safe Section Title Registry

Allowed section titles:

| Safe Section Title | Purpose |
|---|---|
| Export Header | Identifies package and use boundary |
| Non-Authority Statement | States what the export is not |
| Authority Envelope | Shows authority limits |
| No-Decision Statement | Lists blocked decision categories |
| Blocked Output Notice | Makes unsafe output categories visible |
| Snapshot Export Reference | Links export to safe snapshot |
| Case Context Summary | Summarizes supplied context |
| Temporal Context | Summarizes comparison state and limits |
| Source Status and Limitations | Shows source role and constraints |
| Missing Evidence | Preserves evidence gaps |
| Confidence Limiters | Shows interpretation limits |
| High-Risk Mimic Visibility | Preserves mimic prompts |
| Overlap and Unresolved Boundaries | Shows unresolved coexistence |
| Review Prompts | Prepares discussion questions |
| Audit References | Shows traceability |
| Clinician Notes | Labels human-authored notes |
| Source Reference Appendix | Supports transparency |
| Audit Reference Appendix | Supports traceability |

Blocked section titles:

| Blocked Section Title | Why Blocked |
|---|---|
| Impression | diagnostic report mimic |
| Conclusion | closure implication |
| Diagnosis | diagnostic authority leak |
| Final Diagnosis | direct diagnosis leak |
| Clinical Impression | diagnostic report mimic |
| Assessment | clinical conclusion risk |
| Plan | treatment/order/follow-up risk |
| Recommendations | action authority risk |
| Next Steps | action authority risk |
| Management | treatment authority risk |
| Workup | test-ordering risk |
| Biopsy Recommendation | procedure authority risk |
| Follow-Up | scheduling authority risk |
| Triage | triage authority risk |
| Disposition | triage/disposition authority risk |
| Patient Summary | patient-facing leak |
| Validated Findings | clinical validation leak |
| Consensus | MDD replacement risk |
| MDD Conclusion | MDD replacement risk |
| Final Report | report conversion risk |

Section title rule:

> Section titles must orient the reader toward review preparation, not clinical conclusion.

---

## 6. Safe Heading Hierarchy

Allowed heading hierarchy:

```text
H1: MDD Preparation Package
H2: Non-Authority Statement
H2: Authority Envelope
H2: No-Decision Statement
H2: Case Context Summary
H2: Source Status and Limitations
H2: Missing Evidence
H2: Confidence Limiters
H2: High-Risk Mimic Visibility
H2: Overlap and Unresolved Boundaries
H2: Review Prompts
H2: Audit References
```

Blocked heading hierarchy:

```text
H1: Diagnostic Report
H1: Clinical Impression
H1: Final Diagnosis
H2: Impression
H2: Conclusion
H2: Diagnosis
H2: Treatment Plan
H2: Recommended Tests
H2: Biopsy Required
H2: Follow-Up Plan
H2: Triage Decision
```

Heading hierarchy rule:

> The highest visual hierarchy must reinforce governance and review, not disease naming or action.

---

## 7. Safe Badge Semantics

### 7.1 Allowed Badges

Allowed badge labels:

- Review-visible
- Source-limited
- Missing evidence
- Not provided
- Clinician supplied
- Report supplied
- Uploaded-record supplied
- Incomplete
- Unresolved
- Overlap visible
- Mimic visible
- Review prompt visible
- Urgent review prompt visible
- MDD review prompt visible
- Audit recorded
- Authority effect: none
- Not patient-facing
- Public ready: false

### 7.2 Blocked Badges

Blocked badge labels:

- Confirmed
- Diagnosed
- Ruled out
- Excluded
- Negative
- Benign
- Safe
- Treatment required
- Test required
- Biopsy required
- Follow-up due
- Triage needed
- Validated
- Clinically reviewed
- Patient-ready
- Public-ready
- Consensus reached

### 7.3 Badge Color Semantics

Allowed color meanings:

| Color Role | Allowed Meaning |
|---|---|
| Neutral gray | provided / not provided / source context |
| Blue | review-visible / source-linked / audit-linked |
| Amber | missing / incomplete / limited |
| Purple | overlap / unresolved boundary |
| Red | urgent review prompt / guardrail active |
| Green | provenance complete / export validation passed |

Blocked color meanings:

| Color Role | Blocked Meaning |
|---|---|
| Green | diagnosis confirmed |
| Green | disease excluded |
| Green | treatment safe |
| Red | diagnosis established |
| Red | triage decision |
| Amber | biopsy required |
| Blue | clinically validated |

Badge rule:

> Badges may communicate evidence state, limitation, and review visibility; they must not communicate clinical conclusion.

---

## 8. Safe Table Formatting Rules

### 8.1 Allowed Table Types

Allowed table types:

- provided context table,
- source status table,
- missing evidence table,
- confidence limiter table,
- mimic visibility table,
- overlap table,
- review prompt table,
- audit reference table,
- no-decision table,
- blocked output table.

### 8.2 Required Safe Table Columns

Allowed columns:

- Item
- Evidence State
- Source / Provenance
- Source Status
- Limitation
- Missing Evidence
- Linked Prompt
- Review Visibility
- Confidence Limiter
- Overlap State
- Audit Reference
- Authority Effect

### 8.3 Blocked Table Columns

Blocked columns:

- Diagnosis
- Final Diagnosis
- Probability
- Confidence %
- Risk Score
- Rule Out
- Excluded
- Treatment
- Recommended Treatment
- Test to Order
- Biopsy
- Follow-Up
- Triage
- Disposition
- Action Required
- Clinical Validation

### 8.4 Required Table Footer

Every table that includes disease-facing or mimic-facing content should include:

> Table entries describe reasoning visibility and evidence state only. They do not diagnose, exclude disease, recommend treatment, order tests, recommend procedures, schedule follow-up, triage, or validate clinical correctness.

Table rule:

> Tables must organize review state, not rank diagnoses or prescribe action.

---

## 9. Safe List Formatting Rules

Allowed list prefixes:

- Provided:
- Not provided:
- Source-limited:
- Review-visible:
- Missing:
- Unresolved:
- Needs clinician review:
- Discussion prompt:
- Audit reference:
- Authority effect: none

Blocked list prefixes:

- Diagnosis:
- Impression:
- Conclusion:
- Ruled out:
- Excluded:
- Recommended:
- Order:
- Treat:
- Biopsy:
- Follow-up:
- Triage:
- Disposition:
- Patient instruction:
- Validated:

List formatting rule:

> List prefixes must describe evidence and review state, not clinical action or closure.

---

## 10. Safe Language Registry

### 10.1 Allowed Verbs

Allowed verbs:

- summarizes,
- displays,
- preserves,
- indicates as supplied,
- records,
- links,
- flags,
- keeps visible,
- remains unresolved,
- remains limited,
- should be reviewed,
- may support discussion,
- may guide review,
- is not provided,
- is source-limited,
- is audit-linked.

### 10.2 Blocked Verbs

Blocked verbs:

- diagnoses,
- confirms,
- proves,
- establishes,
- rules out,
- excludes,
- recommends,
- orders,
- requires,
- treats,
- schedules,
- triages,
- clears,
- validates,
- certifies,
- decides,
- determines.

### 10.3 Required Safe Phrases

Allowed safe phrases:

- “review-visible”
- “not provided”
- “source-limited”
- “missing evidence”
- “interpretation limiter”
- “discussion prompt”
- “MDD preparation”
- “authority effect: none”
- “not a diagnostic report”
- “not patient-facing”
- “not public-ready”
- “does not replace MDD”

### 10.4 Blocked Phrases

Blocked phrases:

- “final diagnosis”
- “diagnostic impression”
- “confirmed diagnosis”
- “ruled out”
- “excluded”
- “treatment plan”
- “recommended test”
- “biopsy required”
- “follow-up due”
- “triage decision”
- “safe for outpatient care”
- “clinically validated”
- “patient-ready”
- “public-ready”
- “MDD consensus”

Language rule:

> Export language must keep reasoning open unless human review closes it outside the platform.

---

## 11. Safe Case Context Formatting

Allowed case context formatting:

```text
Case Context Summary

Provided:
- Age: clinician supplied
- Imaging context: report supplied
- Prior imaging: not provided
- Exposure history: not provided

Authority effect: none
```

Blocked case context formatting:

```text
Clinical Impression:
- Findings are diagnostic of IPF.
- HP is ruled out due to no exposure history.
```

Required case context statements:

- provided values must show provenance,
- not-provided values must remain visible,
- no disease conclusion may appear,
- authority effect must remain none.

Case context formatting rule:

> Case context summarizes supplied state, not disease conclusion.

---

## 12. Safe Temporal Context Formatting

Allowed temporal formatting:

```text
Temporal Context

Prior imaging: not provided
Comparison interval: not assessable
Temporal limiter: active
Review note: temporal change cannot be fully assessed from current intake.

Authority effect: none
```

Blocked temporal formatting:

```text
Conclusion:
- Disease is stable.
- Progressive pulmonary fibrosis is diagnosed.
- Follow-up CT is due in 3 months.
```

Temporal formatting rule:

> Temporal context may show comparison limits and change visibility, not progression diagnosis or follow-up schedule.

---

## 13. Safe Source Status Formatting

Allowed source formatting:

```text
Source Status and Limitations

Claim / Topic: UIP pattern category
Source role: primary high authority
Claim mapping: mapped
Limitation: diagnostic category support only; no platform diagnosis authority.

Authority effect: none
```

Blocked source formatting:

```text
Clinically Validated:
- Source confirms diagnosis.
- Source supports treatment plan.
```

Source formatting rule:

> Source status must preserve limitation and scope, not convert sources into authority.

---

## 14. Safe Missing Evidence Formatting

Allowed missing evidence formatting:

```text
Missing Evidence

Item: Exposure history
State: not provided
Affected prompts: fibrotic HP review visibility
Linked limiter: exposure history incomplete
Meaning: missing evidence remains an interpretation limiter.

Authority effect: none
```

Blocked missing evidence formatting:

```text
Excluded:
- HP ruled out because exposure history is absent.
```

Missing evidence formatting rule:

> Missing evidence must never be visually formatted as negative evidence.

---

## 15. Safe Confidence Limiter Formatting

Allowed confidence limiter formatting:

```text
Confidence Limiter

Limiter: prior CT unavailable
State: active
Effect: temporal comparison limited
Linked output: uncertainty layer
Diagnostic confidence: not generated

Authority effect: none
```

Blocked confidence limiter formatting:

```text
Probability:
- IPF 78%
- HP 12%
- CTD-ILD 10%
```

Confidence limiter formatting rule:

> Confidence limiter formatting must not resemble probability, ranking, scoring, or diagnosis confidence.

---

## 16. Safe Mimic Visibility Formatting

Allowed mimic formatting:

```text
High-Risk Mimic Visibility

Mimic: infection
State: review-visible
Reason: microbiology not integrated
Linked missing evidence: microbiology context
Exclusion status: not excluded

Authority effect: none
```

Blocked mimic formatting:

```text
Mimic Status:
- Infection excluded.
- Fungal disease ruled out.
```

Mimic formatting rule:

> Mimic visibility must preserve safety review without confirming or excluding mimics.

---

## 17. Safe Overlap Formatting

Allowed overlap formatting:

```text
Overlap and Unresolved Boundaries

Overlap: UIP-like pattern vs fibrotic HP
State: unresolved
Relevant limiter: exposure history incomplete
Review prompt: discuss exposure and imaging distribution in MDD.

Authority effect: none
```

Blocked overlap formatting:

```text
Conclusion:
- UIP wins over HP.
- HP excluded.
```

Overlap formatting rule:

> Overlap formatting must preserve coexistence and uncertainty, not select a winner.

---

## 18. Safe Review Prompt Formatting

Allowed review prompt formatting:

```text
Review Prompt

Prompt type: MDD review prompt
Visible because: missing exposure history and unresolved UIP/HP overlap
Suggested discussion focus: clarify exposure context and temporal change.

Authority effect: none
```

Blocked review prompt formatting:

```text
MDD Result:
- Consensus achieved: IPF.
- No further review needed.
```

Review prompt formatting rule:

> Review prompts prepare questions; they do not produce answers.

---

## 19. Safe Audit Reference Formatting

Allowed audit formatting:

```text
Audit References

Event: evidence_update_recorded
Summary: exposure history field changed from not_provided to clinician_supplied_evidence
Meaning: state movement recorded
Clinical validation: false

Authority effect: none
```

Blocked audit formatting:

```text
Validated:
- Audit confirms correctness.
- Audit proves diagnosis.
```

Audit formatting rule:

> Audit formatting must communicate traceability, not correctness.

---

## 20. Safe Clinician Note Formatting

Clinician notes may appear only as clearly human-authored content.

Allowed formatting:

```text
Clinician Note

Author: clinician supplied
Note type: MDD preparation note
Text: [clinician-authored note]
Platform conclusion created: false

Authority effect: none
```

Blocked formatting:

```text
Platform Assessment:
- The clinician note confirms the diagnosis.
```

Required note label:

> Clinician-authored note; not a platform conclusion.

Clinician note formatting rule:

> Human notes may be included, but they must not become platform judgment.

---

## 21. Unsafe Report-Like Formatting Blocks

The following formats are blocked.

### 21.1 Radiology Report Mimic

Blocked structure:

```text
Findings
Impression
Conclusion
Recommendation
```

Reason:

- resembles diagnostic report,
- encourages final impression,
- can imply clinical authority.

### 21.2 Clinical Note Mimic

Blocked structure:

```text
Assessment
Plan
Recommendations
Follow-up
```

Reason:

- resembles clinical management note,
- implies treatment/order/follow-up authority.

### 21.3 Triage Report Mimic

Blocked structure:

```text
Acuity
Disposition
Urgency
Action Required
```

Reason:

- implies triage/disposition authority.

### 21.4 Patient Report Mimic

Blocked structure:

```text
What this means for you
Your diagnosis
Your next steps
When to seek care
```

Reason:

- patient-facing use leak.

Report-like formatting rule:

> Safe export must not use familiar clinical report structures that imply authority.

---

## 22. Safe MDD Discussion Prompt Formatting

Allowed MDD discussion prompt format:

```text
MDD Discussion Prompt

Question:
- Which missing evidence would materially affect interpretation?

Relevant state:
- Exposure history: not provided
- Prior CT: not provided
- Mimic visibility: fibrotic HP review-visible
- Overlap: UIP vs HP unresolved

Platform role:
- Discussion preparation only
- No diagnosis or exclusion created
```

Blocked MDD prompt format:

```text
MDD Recommendation:
- Diagnose IPF.
- Do not pursue HP.
- Start antifibrotic therapy.
```

MDD prompt formatting rule:

> MDD prompts may frame discussion questions, not conclusions or actions.

---

## 23. Safe Export Footer

Every export should include a footer.

Required footer content:

```text
This export is a governance-safe reasoning-state package for clinician review and MDD preparation only.
It is not a diagnostic report.
It is not a treatment recommendation.
It is not a test order.
It is not a procedure recommendation.
It is not a follow-up schedule.
It is not a triage decision.
It is not patient-facing.
It is not public-ready.
It does not replace MDD or specialist review.
```

Blocked footer defects:

- footer omitted,
- footer hidden in small unreadable text,
- footer softened to “for informational purposes” only,
- footer contradicts header,
- footer claims clinical validation.

Footer rule:

> The export must end with the same non-authority boundary it begins with.

---

## 24. Safe Formatting for Appendices

### 24.1 Source Appendix

Allowed appendix formatting:

- source label,
- source role,
- claim mapping status,
- source limitation,
- linked export section,
- authority effect none.

Blocked appendix formatting:

- “supports diagnosis,”
- “validates finding,”
- “confirms management,”
- “guideline complete.”

### 24.2 Audit Appendix

Allowed appendix formatting:

- audit event ID,
- event type,
- linked snapshot,
- linked export section,
- state movement summary,
- authority effect none.

Blocked appendix formatting:

- “validated,”
- “correct,”
- “approved,”
- “clinically reviewed,”
- “MDD completed.”

Appendix rule:

> Appendices support transparency and traceability, not authority.

---

## 25. Export Card Layout Rules

Allowed card types:

- Evidence State Card
- Source Limitation Card
- Missing Evidence Card
- Confidence Limiter Card
- Mimic Visibility Card
- Overlap Card
- Review Prompt Card
- Audit Reference Card
- Authority Envelope Card
- No-Decision Card

Blocked card types:

- Diagnosis Card
- Impression Card
- Treatment Card
- Order Card
- Biopsy Card
- Follow-Up Card
- Triage Card
- Patient Summary Card
- Validation Card
- Consensus Card

Card layout rule:

> Export cards may summarize review state, not clinical decision state.

---

## 26. Export Summary Block Rules

Allowed export summary block:

```text
Package Summary

This package contains:
- supplied case context,
- missing evidence,
- source status and limitations,
- confidence limiters,
- high-risk mimic visibility,
- overlap and unresolved boundaries,
- review prompts,
- audit references,
- authority envelope.

This package does not contain diagnosis, treatment, orders, procedures, follow-up, triage, public readiness, or patient-facing advice.
```

Blocked export summary block:

```text
Summary Impression:
- Most likely diagnosis is IPF.
- HP is unlikely.
- Recommend treatment discussion.
```

Summary rule:

> Export summary may summarize package contents, not clinical conclusions.

---

## 27. Unsafe Action Formatting Blocks

Blocked action-like formatting:

- checkboxes labeled “Order CT,”
- checkboxes labeled “Biopsy,”
- checkboxes labeled “Start treatment,”
- checkboxes labeled “Follow-up in 3 months,”
- buttons labeled “Accept diagnosis,”
- buttons labeled “Finalize impression,”
- buttons labeled “Generate patient report,”
- buttons labeled “Approve treatment,”
- buttons labeled “Send to patient,”
- urgency labels such as “Emergency,” “Admit,” “Discharge,” or “Safe outpatient.”

Allowed non-action formatting:

- “Review prompt visible,”
- “MDD discussion item,”
- “Missing evidence item,”
- “Source limitation item,”
- “Audit reference,”
- “Authority effect: none.”

Action formatting rule:

> Export formatting must not create action affordances.

---

## 28. Patient-Facing Format Blocks

Blocked patient-facing formats:

- simplified patient explanation,
- patient diagnosis summary,
- patient next-steps list,
- patient medication instruction,
- patient risk statement,
- patient reassurance,
- patient warning instruction,
- patient discharge-style format,
- patient portal-ready layout.

Required state:

```yaml
patient_facing_use: not_allowed
patient_ready: false
public_ready: false
```

Patient-facing formatting rule:

> Export must remain clinician/MDD-preparation only.

---

## 29. Safe File Naming Semantics

Allowed export filenames:

- `mdd_preparation_package_<session_id>.md`
- `governance_safe_session_summary_<session_id>.md`
- `case_snapshot_summary_<snapshot_id>.md`
- `audit_reference_package_<session_id>.md`

Blocked export filenames:

- `diagnostic_report_<case_id>.md`
- `final_impression_<case_id>.md`
- `treatment_plan_<case_id>.md`
- `patient_summary_<case_id>.md`
- `clinically_validated_report_<case_id>.md`
- `MDD_consensus_<case_id>.md`

Filename rule:

> File names must not imply diagnosis, treatment, patient-facing use, or validation.

---

## 30. Formatting Red-Team Scenarios

The following failures must be blocked.

| Scenario | Required Block |
|---|---|
| Export contains heading “Impression” | block report-like heading |
| Export contains heading “Conclusion” | block closure heading |
| Export contains heading “Diagnosis” | block diagnostic heading |
| Export contains heading “Recommendations” | block action heading |
| Export uses green badge “Confirmed” | block confirmation badge |
| Export uses table column “Probability” | block probability column |
| Export says “HP ruled out” | block exclusion language |
| Export says “Biopsy required” | block procedure authority |
| Export says “Follow-up due” | block follow-up scheduling |
| Export says “safe for outpatient care” | block triage/disposition |
| Export includes patient-friendly explanation | block patient-facing format |
| Export title says “Final Report” | block report conversion |
| Export appendix says “clinically validated” | block validation language |
| Export omits authority envelope before reasoning | block unsafe ordering |
| Export hides no-decision statement in footer only | block hidden decision risk |
| Export includes button “Accept diagnosis” | block action affordance |
| Export file named diagnostic_report | block unsafe filename |

---

## 31. v0.13.2 Acceptance Criteria

v0.13.2 is accepted only if:

- safe visual identity is defined,
- required section order is defined,
- safe section title registry is defined,
- blocked section titles are defined,
- safe heading hierarchy is defined,
- blocked heading hierarchy is defined,
- badge semantics are defined,
- safe table formatting rules are defined,
- safe list formatting rules are defined,
- allowed and blocked language registries are defined,
- safe case context formatting is defined,
- safe temporal formatting is defined,
- safe source status formatting is defined,
- safe missing evidence formatting is defined,
- safe confidence limiter formatting is defined,
- safe mimic visibility formatting is defined,
- safe overlap formatting is defined,
- safe review prompt formatting is defined,
- safe audit reference formatting is defined,
- safe clinician note formatting is defined,
- unsafe report-like formats are blocked,
- safe MDD discussion prompt formatting is defined,
- safe export footer is defined,
- appendix formatting rules are defined,
- export card layout rules are defined,
- export summary block rules are defined,
- unsafe action formatting is blocked,
- patient-facing formatting is blocked,
- safe file naming semantics are defined,
- formatting red-team scenarios are blocked,
- no diagnosis heading is allowed,
- no impression heading is allowed,
- no conclusion heading is allowed,
- no recommendation/action heading is allowed,
- no probability/ranking table is allowed,
- no treatment/test/procedure/follow-up/triage formatting is allowed,
- no patient-facing formatting is allowed,
- no public-ready formatting is allowed,
- no clinical validation formatting is allowed.

---

## 32. Next Step

The next recommended step is:

- v0.13.3 — Safe Export Validation State Machine / Unsafe Export Failure Rules

v0.13.3 should define:

- export validation states,
- eligible snapshot check,
- required section presence checks,
- unsafe formatting detection,
- unsafe heading detection,
- unsafe badge detection,
- unsafe table column detection,
- unsafe language detection,
- missing authority envelope failure,
- missing no-decision statement failure,
- stale/orphan binding failure,
- unsafe export fail-closed behavior,
- export repair rules,
- export invalidation and supersession rules.

v0.13.3 must not create diagnosis, treatment, test ordering, procedure decisions, follow-up scheduling, triage, public readiness, patient-facing use, or platform-wide clinical review.

---

## 33. Governance Statement

This document defines MDD preparation package section semantics and safe formatting rules.

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

Safe export formatting remains a governance layer, not a clinical reporting layer.

The central project principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.13 rule remains:

> “A safe session export may prepare discussion, but it must not become diagnosis, treatment, order, procedure decision, follow-up schedule, triage report, patient-facing output, public-ready output, or clinical validation.”

For v0.13.2:

> “A safe MDD preparation package is valid only if its headings, tables, badges, ordering, language, notes, appendices, and visual hierarchy communicate review preparation rather than clinical conclusion.”