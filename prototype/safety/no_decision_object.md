# No-Decision Object

Status: preserved  
Scope: Internal synthetic prototype decision boundary  
Diagnostic Authority: none  
Treatment Authority: none  

---

## No-Decision Object

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

---

## Rule

The prototype may display reasoning governance.

It must not decide:

- diagnosis,
- disease exclusion,
- mimic exclusion,
- treatment,
- tests,
- procedures,
- follow-up,
- triage,
- MDD consensus,
- patient-facing output.

> The platform teaches reasoning structure; it does not make clinical decisions.
