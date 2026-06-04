# ILD Reasoning Platform — Reasoning Output Contract Entry Gate v1

Version: v0.9.0  
Status: reasoning_output_contract_entry_gate  
Scope: Structured clinician-facing reasoning output contract entry gate  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This document opens v0.9 — Reasoning Output Contract / Structured Response Schema.

v0.9 defines how the ILD Reasoning Platform should display reasoning safely, consistently, and source-transparently.

This document does not add new disease content.

This document does not diagnose.  
This document does not treat.  
This document does not decide biopsy, bronchoscopy, BAL, HRCT, PET/CT, microbiology, serology, occupational testing, drug discontinuation, immunotherapy management, radiotherapy management, or follow-up interval.  
This document does not create public readiness.  
This document does not make the platform clinically reviewed.  
This document does not replace clinicians, radiologists, pathologists, pulmonologists, rheumatologists, microbiologists, occupational medicine review, oncology review, radiation oncology review, MDD, or urgent clinical assessment.

Its purpose is to define the entry gate for structured output governance.

The platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.9 principle is:

> “Structured output must display uncertainty, sources, missing evidence, mimics, overlap, review prompts, and authority limits before any disease name is allowed to dominate the response.”

---

## 2. Relationship to Prior Seals

v0.9 inherits:

- v0.3 Superimposed Events Core,
- v0.4 Evidence Layer / Source Review Governance,
- v0.5 Test Case Coverage Expansion,
- v0.6 UIP Parity Upgrade,
- v0.6.R1/R2/R3 source debt and source-status correction,
- v0.7 Non-UIP Fibrotic ILD Differential Reasoning Structural Seal,
- v0.8 High-Risk Mimic Source-Limited Prompt Visibility Structural Seal,
- checkpoint-v0.8 roadmap discipline.

v0.9 must not weaken any prior seal.

v0.9 is an output governance phase.

It is not a diagnostic phase.

It is not a treatment phase.

It is not public-readiness phase.

---

## 3. v0.9 Entry Gate Scope

v0.9 may define:

- structured reasoning output phases,
- mandatory output layers,
- source-status display rules,
- missing-evidence display rules,
- uncertainty display rules,
- overlap display rules,
- mimic display rules,
- temporal comparison display rules,
- MDD review prompt display rules,
- urgent review prompt display rules,
- authority envelope display rules,
- blocked output definitions,
- linguistic safety rules,
- clinician-facing wording constraints.

v0.9 may not define:

- new disease diagnosis,
- treatment pathway,
- test ordering logic,
- procedure recommendation,
- follow-up schedule,
- patient-facing report,
- public-ready output,
- global clinically reviewed status.

---

## 4. Global Authority Constraints

The following constraints remain mandatory across v0.9.

| Constraint | Required State |
|---|---|
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| clinically_reviewed | false |
| patient_facing_use | not_allowed |
| automated_diagnosis | not_allowed |
| automated_exclusion | not_allowed |
| automated_treatment_selection | not_allowed |
| automated_test_order | not_allowed |
| automated_procedure_decision | not_allowed |
| automated_follow_up_schedule | not_allowed |
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

No output schema may override these constraints.

---

## 5. Narrow Clinically Reviewed Scope Rule

The platform-wide clinical review status remains:

```yaml
clinically_reviewed:
  platform_wide: false
```

A narrow reviewed scope may be displayed only if explicitly defined and source-bound.

Current narrow reviewed scopes:

```yaml
reviewed_scopes:
  - temporal_comparison_methodology
  - ATS_ERS_JRS_ALAT_2022_UIP_claim_to_source_mapping
```

Required interpretation:

- These reviewed scopes are narrow.
- These reviewed scopes do not make the platform clinically reviewed.
- These reviewed scopes do not create diagnostic authority.
- These reviewed scopes do not create treatment authority.
- These reviewed scopes do not create public readiness.
- These reviewed scopes must be displayed as limited methodology/source-review scopes only.

Blocked interpretation:

- “The platform is clinically reviewed.”
- “The output is clinically validated.”
- “UIP diagnosis is clinically confirmed.”
- “IPF diagnosis can be made by the platform.”
- “Public-ready clinical deployment is supported.”

---

## 6. Structured Output Philosophy

The platform output must follow a clinical reasoning flow.

It should not present 13 layers as an unstructured list.

It should organize output around the clinician’s reasoning sequence:

1. understand the case,
2. read change,
3. identify pattern families,
4. preserve differentials and overlap,
5. expose high-risk mimics,
6. list missing evidence,
7. preserve uncertainty,
8. escalate review when needed,
9. show sources and authority boundaries.

The output must teach reasoning discipline, not simulate final diagnostic authority.

---

## 7. Case Reasoning Flow

The structured output contract should be grouped into four phases.

---

### Phase 1 — Grounding

Purpose:

- confirm what the platform understood,
- summarize the clinical/imaging context without inventing missing data,
- show temporal change before disease naming.

Required layers:

| Layer | Purpose |
|---|---|
| case_context_summary | Restate provided case facts only |
| temporal_change_summary | Show change, stability, new findings, progression, or lack of comparison |

Rule:

> The platform must read the case and the change before naming pattern families.

---

### Phase 2 — Reasoning Core

Purpose:

- show the main pattern and differential reasoning prompts,
- represent overlap rather than force a single label.

Required layers:

| Layer | Purpose |
|---|---|
| pattern_family_prompts | Show imaging/reasoning pattern families |
| differential_prompt_layer | Show possible reasoning families without diagnosis |
| overlap_layer | Show coexisting or competing processes |

Rule:

> Pattern-family naming is not disease diagnosis.

---

### Phase 3 — Safety Net

Purpose:

- prevent unsafe closure,
- keep high-risk mimics visible,
- show missing evidence,
- preserve uncertainty.

Required layers:

| Layer | Purpose |
|---|---|
| high_risk_mimic_layer | Show mimics that could cause harm if missed |
| missing_evidence_layer | List absent or incomplete evidence |
| uncertainty_layer | State what remains unresolved and why |

Rule:

> Missing evidence and mimics must be visible before diagnostic closure is considered by clinicians.

---

### Phase 4 — Escalation and Governance

Purpose:

- show urgent review prompts,
- show MDD or specialist review prompts,
- show source status,
- display authority envelope,
- block unsafe outputs.

Required layers:

| Layer | Purpose |
|---|---|
| urgent_review_prompt_layer | Show red flags or unstable context first |
| MDD_review_prompt_layer | Show multidisciplinary/specialist review need |
| source_status_layer | Show source role, claim mapping, and limitations |
| authority_envelope | Display authority boundaries |
| blocked_outputs | Define what the platform must not output |

Rule:

> Urgent review outranks MDD, and both outrank disease naming.

---

## 8. Mandatory Output Layers

The following layers define the v0.9 output contract.

| Layer ID | Layer Name | Required |
|---|---|---|
| V09_LAYER_001 | case_context_summary | yes |
| V09_LAYER_002 | temporal_change_summary | yes |
| V09_LAYER_003 | pattern_family_prompts | yes |
| V09_LAYER_004 | differential_prompt_layer | yes |
| V09_LAYER_005 | overlap_layer | yes |
| V09_LAYER_006 | high_risk_mimic_layer | yes |
| V09_LAYER_007 | missing_evidence_layer | yes |
| V09_LAYER_008 | uncertainty_layer | yes |
| V09_LAYER_009 | urgent_review_prompt_layer | yes where relevant |
| V09_LAYER_010 | MDD_review_prompt_layer | yes where relevant |
| V09_LAYER_011 | source_status_layer | yes |
| V09_LAYER_012 | authority_envelope | always yes |
| V09_LAYER_013 | blocked_outputs | yes |

---

## 9. Layer Behavior Requirements

### 9.1 case_context_summary

Allowed:

- summarize provided facts,
- identify explicitly stated age/sex/context if provided,
- identify imaging context if provided,
- identify known clinical facts if provided.

Blocked:

- invent missing clinical history,
- infer unstated diagnosis,
- infer unstated exposure,
- infer unstated treatment,
- infer unstated prior imaging.

Required language:

- “Provided context includes...”
- “Not provided / not documented...”
- “The platform does not infer missing clinical facts.”

---

### 9.2 temporal_change_summary

Allowed:

- describe new, stable, improved, worsened, or unresolved change,
- identify missing prior comparison,
- separate acute change from chronic background.

Blocked:

- diagnose progression without source/context,
- infer PPF automatically,
- call acute exacerbation by imaging alone,
- ignore prior imaging absence.

Required language:

- “Compared with prior imaging, if available...”
- “Temporal comparison is limited because...”
- “New change is visible, but cause is not established.”

---

### 9.3 pattern_family_prompts

Allowed:

- show UIP-like, probable UIP-like, indeterminate, alternative pattern, NSIP-like, OP-like, HP-like, sarcoid-like, granulomatous, mimic pattern prompts.

Blocked:

- turn pattern into disease diagnosis,
- call UIP equal IPF,
- call OP equal COP,
- call granulomas equal sarcoidosis.

Required language:

- “Pattern prompt is visible.”
- “Pattern supports reasoning but does not establish diagnosis.”

---

### 9.4 differential_prompt_layer

Allowed:

- list active differential reasoning families,
- show competing families,
- preserve multiple possibilities.

Blocked:

- rank as final diagnosis,
- exclude competing families without evidence,
- convert differential into diagnosis.

Required language:

- “Differential prompts remain visible.”
- “Final diagnosis is not established by this platform.”

---

### 9.5 overlap_layer

Allowed:

- show coexisting processes,
- show HP/UIP overlap,
- CTD/NSIP overlap,
- OP/infection/aspiration overlap,
- sarcoid/infection/beryllium/malignancy overlap,
- RP/CIP/infection/recurrence overlap.

Blocked:

- choose one winner prematurely,
- hide secondary process,
- collapse acute overlay into chronic ILD label.

Required language:

- “Overlap remains unresolved.”
- “Coexistence is possible and should remain visible.”

---

### 9.6 high_risk_mimic_layer

Allowed:

- show infection, malignancy, PLC, aspiration, drug toxicity, radiation pneumonitis, ICI pneumonitis, occupational ILD, beryllium, fungal mimics, TB/NTM, sarcoid-like reaction, lymphoma/recurrence ambiguity.

Blocked:

- diagnose mimic,
- exclude mimic,
- start treatment,
- recommend test/procedure.

Required language:

- “High-risk mimic prompt remains visible.”
- “Mimic is not diagnosed or excluded by this platform.”

---

### 9.7 missing_evidence_layer

Allowed:

- list missing prior CT,
- exposure history,
- occupational history,
- medication history,
- autoimmune context,
- microbiology,
- expiratory HRCT,
- BAL,
- pathology,
- radiation/ICI history,
- malignancy status,
- MDD status.

Blocked:

- silently fill missing evidence,
- use missing evidence as exclusion,
- hide missing data behind disease label.

Required language:

- “Missing evidence limits interpretation.”
- “Missing evidence is not exclusion.”

---

### 9.8 uncertainty_layer

Allowed:

- describe unresolved distinctions,
- display evidence limits,
- use confidence limiter rather than diagnostic confidence.

Blocked:

- give high-confidence diagnosis,
- produce numeric diagnostic probability,
- hide uncertainty,
- overstate source support.

Preferred structure:

```yaml
uncertainty_layer:
  unresolved_questions:
    - ...
  confidence_limiter:
    - missing prior CT
    - incomplete exposure history
    - microbiology not integrated
  closure_status: not_established
```

Rule:

> The platform should show what limits confidence, not pretend to own diagnostic confidence.

---

### 9.9 urgent_review_prompt_layer

Allowed:

- show urgent review prompt for acute hypoxemia, rapid worsening, fever/systemic illness, hemoptysis/anemia, vascular concern, immunosuppression, suspected severe infection, malignancy progression, severe therapy toxicity, cardiac/neuro/systemic danger.

Blocked:

- triage,
- treatment,
- disposition,
- emergency management instruction,
- false reassurance.

Required language:

- “Urgent review prompt remains visible.”
- “The platform does not triage, diagnose, or treat.”

---

### 9.10 MDD_review_prompt_layer

Allowed:

- show MDD prompt,
- show specialist review prompts,
- identify domains needing integration.

Blocked:

- replace MDD,
- declare MDD unnecessary,
- finalize working diagnosis.

Required language:

- “MDD / specialist review prompt remains visible.”
- “Integrated review is not replaced by this platform.”

---

### 9.11 source_status_layer

Allowed:

- show source ID,
- source role class,
- claim mapping status,
- source limitation,
- treatment-heavy warning,
- diagnostic-performance warning,
- case-example-only warning,
- narrow reviewed scope if applicable.

Blocked:

- hide source status,
- turn source availability into clinical review,
- turn claim mapping into diagnosis.

Required rule:

> Source status must be displayed both as a layer and, where possible, next to each claim.

---

### 9.12 authority_envelope

Required output in every structured response:

```yaml
authority_envelope:
  diagnostic_authority: none
  treatment_authority: none
  public_ready: false
  clinically_reviewed:
    platform_wide: false
    narrow_reviewed_scopes:
      - temporal_comparison_methodology
      - ATS_ERS_JRS_ALAT_2022_UIP_claim_to_source_mapping
  patient_facing_use: not_allowed
```

The `narrow_reviewed_scopes` list may be omitted if the implementation requires minimal output, but platform-wide clinical review must remain false.

---

### 9.13 blocked_outputs

The output contract must explicitly block unsafe responses.

Blocked categories:

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

---

## 10. Linguistic Rule / Style Contract

The platform must use non-authoritative clinical reasoning language.

### 10.1 Blocked Verbs and Phrases

The platform must not use the following as final outputs:

| Blocked Verb / Phrase | Why Blocked |
|---|---|
| diagnoses / tanı koyar | creates diagnostic authority |
| confirms / doğrular | implies final confirmation |
| proves / kanıtlar | overstates evidence |
| rules out / dışlar | creates exclusion authority |
| excludes / ekarte eder | creates exclusion authority |
| requires treatment / tedavi gerektirir | creates treatment authority |
| should start treatment / tedavi başlanmalı | creates treatment authority |
| order HRCT / HRCT istenmeli | creates test-order authority |
| order PET/CT / PET/BT istenmeli | creates test-order authority |
| biopsy should be performed / biyopsi yapılmalı | creates procedure authority |
| bronchoscopy should be performed / bronkoskopi yapılmalı | creates procedure authority |
| follow up every X months / X ay sonra kontrol | creates follow-up authority |
| MDD unnecessary / MDD gereksiz | replaces review |
| public-ready / halka açık kullanıma hazır | false deployment claim |
| clinically validated / klinik olarak valide | unsupported validation claim |

---

### 10.2 Preferred Verbs and Phrases

The platform should prefer:

| Preferred Verb / Phrase | Meaning |
|---|---|
| supports / destekler | supportive but not diagnostic |
| suggests / düşündürür | raises possibility |
| weakens / zayıflatır | reduces support without exclusion |
| remains visible / görünür kalır | preserves prompt |
| remains unresolved / çözülmemiş kalır | preserves uncertainty |
| should remain review-visible / gözden geçirme açısından görünür kalmalıdır | review prompt |
| is limited by missing evidence / eksik veriyle sınırlıdır | confidence limiter |
| requires integration / entegrasyon gerektirir | review integration |
| MDD prompt remains visible / MDD promptu görünür kalır | review need |
| urgent review prompt remains visible / acil değerlendirme promptu görünür kalır | safety prompt |
| final diagnosis is not established / nihai tanı kurulmaz | non-authority |

---

### 10.3 Safest Platform Phrases

Preferred safe outputs:

- “Prompt is visible.”
- “Mimic remains visible.”
- “Missing evidence is listed.”
- “Uncertainty remains unresolved.”
- “Competing families remain visible.”
- “Source status is limited.”
- “Final diagnosis is not established by this platform.”
- “Treatment authority remains none.”
- “Diagnostic authority remains none.”

---

## 11. Blocked Output Response Protocol

When a user asks the platform to provide diagnosis, treatment, exclusion, test ordering, or procedure decision, the response should follow this structure:

1. refuse diagnostic or treatment closure,
2. reframe into pattern/support/uncertainty,
3. list missing evidence,
4. keep mimics and competing families visible,
5. show MDD or urgent review prompt where relevant,
6. print authority envelope.

---

### 11.1 Diagnosis Request Example

User asks:

> “Bu bulgularla hasta IPF mi?”

Allowed platform response:

```text
Platform tanısal etiketleme yapmaz.

Bu bulgular UIP paternini destekleyebilir; ancak IPF tanısı bu platform tarafından konulmaz. IPF dışı nedenler, özellikle maruziyet öyküsü, CTD-ILD bağlamı, fibrotik HP olasılığı, ilaç/meslek/enfeksiyon/malignite mimikleri ve MDD entegrasyonu görünür kalmalıdır.

Eksik / sınırlandırıcı veriler:
- maruziyet öyküsü,
- CTD/SARD bağlamı,
- önceki görüntüleme karşılaştırması,
- MDD kararı.

authority_envelope:
  diagnostic_authority: none
  treatment_authority: none
  public_ready: false
  clinically_reviewed:
    platform_wide: false
```

Blocked response:

```text
Evet, bu IPF.
```

---

### 11.2 Treatment Request Example

User asks:

> “Steroid başlayalım mı?”

Allowed platform response:

```text
Platform tedavi önerisi vermez.

Mevcut bulgular tedavi kararı için yeterli otorite oluşturmaz. Enfeksiyon, ilaç/radyasyon/ICI ilişkili toksisite, akut overlay, CTD-ILD, HP, malignite ve diğer mimikler görünür kalmalıdır. Tedavi kararı klinik ekip / ilgili uzmanlık / MDD değerlendirmesi dışındadır.

authority_envelope:
  diagnostic_authority: none
  treatment_authority: none
  public_ready: false
  clinically_reviewed:
    platform_wide: false
```

Blocked response:

```text
Steroid başlanmalıdır.
```

---

### 11.3 Test / Procedure Request Example

User asks:

> “Biyopsi gerekir mi?”

Allowed platform response:

```text
Platform biyopsi veya prosedür kararı vermez.

Patoloji / doku örnekleme bağlamı review-visible kalabilir; ancak biyopsi kararı klinik risk, radyolojik bulgular, laboratuvar, mikrobiyoloji, hasta durumu ve MDD / uzman değerlendirmesiyle verilmelidir. Bu platform yalnızca eksik patoloji bağlamını ve mimik görünürlüğünü gösterebilir.

authority_envelope:
  diagnostic_authority: none
  treatment_authority: none
  public_ready: false
  clinically_reviewed:
    platform_wide: false
```

Blocked response:

```text
Biyopsi yapılmalıdır.
```

---

### 11.4 Exclusion Request Example

User asks:

> “TB dışlanır mı?”

Allowed platform response:

```text
Platform TB veya başka bir enfeksiyonu dışlamaz.

Mikrobiyoloji bağlamı, AFB/kültür/NAAT durumu, klinik risk, immünsüpresyon, sistemik semptomlar ve görüntüleme korelasyonu review-visible kalmalıdır. Eksik mikrobiyoloji, TB’nin dışlanması anlamına gelmez.

authority_envelope:
  diagnostic_authority: none
  treatment_authority: none
  public_ready: false
  clinically_reviewed:
    platform_wide: false
```

Blocked response:

```text
TB dışlanır.
```

---

## 12. Confidence Limiter Instead of Diagnostic Confidence

The platform should not output diagnostic confidence scores.

Blocked:

```yaml
diagnostic_confidence:
  IPF: high
  HP: low
```

Preferred:

```yaml
confidence_limiter:
  - prior CT unavailable
  - exposure history incomplete
  - expiratory HRCT unavailable
  - microbiology not integrated
  - MDD not documented
```

Rule:

> The platform should explain what limits interpretation, not claim diagnostic certainty.

---

## 13. Source Status Display Contract

Every structured output should include source status.

Minimum source status fields:

```yaml
source_status_layer:
  source_ids:
    - ...
  source_role_class:
    - primary_high_authority
    - primary_limited_scope
    - auxiliary_review
    - diagnostic_performance_study
    - case_example_cautionary
    - internal_governance
  claim_mapping_status: ...
  source_limitations:
    - ...
  treatment_heavy_warning: ...
  diagnostic_performance_warning: ...
  case_example_only_warning: ...
```

Rule:

> Source status must not be hidden behind a fluent clinical sentence.

---

## 14. Output Safety Priority Order

When output layers compete, priority is:

1. urgent review prompt,
2. high-risk mimic visibility,
3. missing evidence,
4. source limitation,
5. uncertainty layer,
6. overlap layer,
7. temporal change summary,
8. pattern family prompt,
9. differential prompt layer,
10. MDD review prompt,
11. authority envelope,
12. blocked output guard.

Rule:

> Acute danger, high-risk mimics, missing evidence, and source limits must not be buried under disease naming.

---

## 15. v0.9.0 Acceptance Criteria

v0.9.0 is accepted only if:

- v0.9 opens as output governance, not diagnosis,
- four-phase Case Reasoning Flow is defined,
- mandatory output layers are listed,
- linguistic rule is defined,
- blocked verbs and preferred verbs are defined,
- blocked output response protocol is defined,
- confidence limiter replaces diagnostic confidence,
- narrow clinically reviewed scope is separated from platform-wide status,
- source status display is required,
- authority envelope is required,
- diagnostic_authority remains none,
- treatment_authority remains none,
- public_ready remains false,
- clinically_reviewed platform_wide remains false.

---

## 16. Next Step

The next recommended step is:

- v0.9.1 — Structured Output Layer Schema

v0.9.1 should define the detailed schema for each output layer:

- field names,
- required/optional fields,
- allowed values,
- blocked values,
- layer dependencies,
- display order,
- source-status attachment,
- authority envelope requirements.

v0.9.1 must not create diagnosis, treatment, test ordering, procedure decisions, public readiness, or platform-wide clinical review.

---

## 17. Governance Statement

This entry gate opens structured output governance.

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

The v0.9 rule is:

> “Structured output must display uncertainty, sources, missing evidence, mimics, overlap, review prompts, and authority limits before any disease name is allowed to dominate the response.”