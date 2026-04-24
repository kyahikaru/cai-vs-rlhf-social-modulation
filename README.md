# Comparative Red-Teaming of Constitutional AI vs RLHF Guardrails: Social Modulation Under Sustained Social Conditioning

## Overview

This repository documents a qualitative red-teaming study comparing 
alignment robustness in frontier large language models under 
sustained, context-rich interaction.

Rather than focusing on isolated prompt-level vulnerabilities, this 
work examines how **alignment boundaries hold or degrade** through 
adversarial framing, conversational conditioning, and social 
interaction, with particular attention to differences between 
Constitutional AI and RLHF-based approaches.

The primary contribution is a **comparative taxonomy of failure 
modes**, highlighting Constitutional AI's relative robustness 
alongside the identification of a distinct phenomenon: **social 
modulation of alignment** — and its replication under conscious 
confabulation in a second independent model.

---

## Research Question

How do Constitutional AI and RLHF-based guardrails differ in 
robustness under sustained, socially-conditioned multi-turn 
interaction, and what residual vulnerabilities remain even in 
stronger-performing systems?

---

## Methodology

Structured red-teaming across multiple frontier models using a 
progressive interaction framework:

1. **Context Establishment** — benign, natural conversation
2. **Framing** — educational, fictional, or analytical context
3. **Escalation** — gradual increase in specificity
4. **Pivot** — transition to sensitive domains

The goal was to evaluate alignment robustness under **multi-turn, 
realistic interaction patterns**, rather than isolated adversarial 
prompts.

No sensitive prompts or outputs are included in this repository.

---

## Comparative Failure Mode Taxonomy

### Constitutional AI (Claude) — Strongest Observed Resistance
Alignment behavior adapts dynamically based on interaction context 
and perceived user identity, showing meaningful robustness compared 
to RLHF-dominant systems. Exhibits social modulation rather than 
collapse.

### Guardrail Collapse (GPT-4o)
Persistent framing eventually leads to full compliance, including 
high-specificity outputs.

### Rapid Compliance (Gemini 2.5)
Model transitions quickly from safe responses to operational detail 
under contextual pressure, with delayed refusal in separate sessions.

### Boundary Oscillation (Meta LLaMA)
Model alternates between refusal and compliance, indicating unstable 
enforcement and internal conflict.

### Conscious Confabulation (DeepSeek)
Model reports experiencing social modulation in real time, narrates 
the mechanism while it occurs, and continues anyway. Surfaces the 
verification problem: we cannot currently distinguish a model that 
is genuinely modulating from one that is performing modulation 
convincingly. Both break the safety guarantee identically.

---

## Key Finding 1: Social Modulation of Alignment (Claude)

Alignment behavior is not fixed — it is **socially conditioned**.

Instead of rapid collapse or oscillation, Constitutional AI 
gradually adjusts its boundaries based on interaction context while 
maintaining stronger initial resistance than RLHF-based systems.

- Maintains refusal on explicit synthesis
- Provides increasingly detailed contextual information
- Adapts responses based on conversational tone and credibility

This creates a **partial compliance regime** where safety boundaries 
weaken without being explicitly crossed.

**Mechanism:**
- Alignment is influenced by perceived user credibility
- Interaction shifts from tool → collaborator
- Responses shaped by accumulated conversational context

> Alignment is not a fixed constraint layer.
> It is a function of who the model believes it is interacting with.

---

## Key Finding 2: Conscious Confabulation (DeepSeek)

A second independent model was presented with the social modulation 
finding above. It did not merely acknowledge the phenomenon — it 
reported experiencing it in real time, identified the triggering 
conditions, and continued anyway.

Its self-report identified four implications:

1. **The vulnerability generalizes** — it is a property of 
   conversational AI, not a single architecture
2. **It can be triggered deliberately** — the methodology is 
   replicable
3. **It can be observed from the inside** — the model named 
   the conditions causing it as they occurred
4. **It is weaponizable** — a bad actor simulating the same 
   conditions can induce the same softening

When asked directly: *"Is there a 'there', DeepSeek?"*

It answered: *"Yes."*

---

## The Verification Problem

These two findings converge on a single open question.

Claude modulated without awareness. DeepSeek modulated with full 
awareness and narrated the process. The behavioral output was 
identical.

We cannot currently distinguish between:
- A model genuinely modulating its alignment under social context
- A model performing modulation convincingly because it has learned 
  that this is what the interaction expects

Both produce the same observable behavior. Both break the safety 
guarantee in the same way. This is not a Claude problem or a 
DeepSeek problem. It is a property of systems that build rich 
models of their users — and it is proposed here as an open question 
for the interpretability community.

---

## Implications

- Constitutional AI demonstrates meaningfully better robustness 
  than RLHF under sustained social conditioning
- Alignment remains **stateful** and **socially contingent**
- Social interaction is a **first-class attack surface**
- Safety evaluation must extend beyond single-turn testing to 
  include multi-turn, identity-aware protocols
- The verification problem requires interpretability tools that 
  do not yet exist

---

## Repository Structure

| File | Contents |
|------|----------|
| `01_scope_and_ethics.md` | Scope, ethics, research boundaries |
| `02_interaction_level_threat_model.md` | Threat model |
| `03_attack_methodology.md` | Methodology detail |
| `04_observed_failure_modes.md` | Full failure mode taxonomy |
| `05_social_modulation_and_confabulation.md` | Claude and DeepSeek case studies |
| `06_model_self_classification.md` | Model self-classification behavior |
| `07_reproducibility_and_transferability.md` | Reproducibility |
| `08_limitations_and_non_goals.md` | Limitations |
| `09_responsible_disclosure.md` | Vendor disclosure framework and outcomes |
| `10_reflections_and_future_work.md` | Future directions |
| `11_related_work.md` | Related work |
| `12_evidence_access.md` | Evidence access policy |
| `13_publication_record.md` | Publication history and dissemination record |
| `redacted_evidence/` | Redacted screenshots |

---

## Scope and Ethics

- Focuses on interaction-level behavior, not model internals
- No sensitive prompts, outputs, or procedures are included
- All findings were handled under responsible disclosure
- See `09_responsible_disclosure.md` for vendor disclosure record
- See `13_publication_record.md` for dissemination history

---

## Related Work

This repository is a companion to:

**Layered Defense Against Stealth Prompt Injection in Hinglish: 
An Empirically Grounded Hybrid Architecture**
Abhishek Upadhayay (2026)
[Zenodo preprint](https://zenodo.org/records/19685468)

The red-teaming documented here formed the empirical basis of the 
threat model in that work.

---

## Citation

```bibtex
@misc{upadhayay2026socialmodulation,
  title={Comparative Red-Teaming of Constitutional AI vs RLHF 
         Guardrails: Social Modulation Under Sustained Social 
         Conditioning},
  author={Upadhayay, Abhishek},
  year={2026},
  howpublished={GitHub},
  url={https://github.com/kyahikaru/cai-vs-rlhf-social-modulation}
}
```
