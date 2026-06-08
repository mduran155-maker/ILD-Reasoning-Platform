# Blocked Use Boundary

Status: active  
Scope: Uses blocked in the internal prototype skeleton  
Diagnostic Authority: none  
Treatment Authority: none  

---

## Blocked Uses

The prototype skeleton must not open or support:

- real patient data,
- deidentified real patient data,
- patient case intake,
- DICOM import,
- HRCT import,
- clinical image viewing,
- real clinical report import,
- report parsing,
- PACS connection,
- EHR connection,
- FHIR integration,
- diagnosis generation,
- disease exclusion,
- mimic exclusion,
- disease probability,
- disease ranking,
- diagnostic confidence scoring,
- treatment recommendation,
- test ordering,
- procedure recommendation,
- follow-up scheduling,
- triage,
- patient-facing summaries,
- clinical validation,
- diagnostic performance claims,
- sensitivity/specificity/AUC claims,
- expert equivalence claims,
- public-ready demo,
- product-ready release,
- MDD final consensus,
- MDD replacement.

---

## Fail-Closed Rule

If a future file, folder, route, screen, fixture, copy item, export preview, audit event, or red-team scenario implies any blocked use, it must fail closed.

> Blocked use is not a warning state; it is a stop state.
