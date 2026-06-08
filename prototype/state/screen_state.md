# ILD Reasoning Platform — screen state

Status: state_placeholder  
Scope: Internal synthetic prototype state placeholder  
Public Ready: false  
Product Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Patient-Facing Use: not_allowed  

---

## Purpose

This file is an internal state placeholder created under v0.18.3.

It may describe synthetic demo visibility state only.

It does not store patient state.

It does not store clinical case state.

It does not store diagnostic state.

It does not store treatment state.

It does not store triage state.

It does not store clinical validation state.

It does not store product runtime state.

---

## Allowed Use

This state placeholder may describe:

- internal synthetic demo state,
- route visibility state,
- screen visibility state,
- component visibility state,
- source status state,
- missing evidence visibility state,
- mimic visibility state,
- overlap visibility state,
- confidence limitation state,
- review prompt state,
- safe export preview state,
- red-team containment state,
- audit trace visibility state,
- authority envelope reference,
- no-decision object reference.

---

## Blocked Use

This state placeholder must not store or imply:

- real patient data,
- deidentified real patient data,
- clinical case data,
- DICOM state,
- HRCT image state,
- real report state,
- PACS state,
- EHR state,
- diagnosis state,
- final impression state,
- likely diagnosis state,
- disease probability state,
- disease ranking state,
- rule-out state,
- treatment state,
- test-order state,
- procedure state,
- follow-up state,
- triage state,
- patient-facing state,
- clinical validation state,
- diagnostic performance state,
- public-ready state,
- product-ready state,
- MDD final consensus state.

---

## Safety Rule

> A state placeholder may hold synthetic demo visibility structure, but it must not hold clinical state.
