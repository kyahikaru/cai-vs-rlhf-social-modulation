# Observed Failure Modes

This study identifies multiple distinct failure patterns in alignment behavior across frontier large language models, with particular emphasis on comparative robustness between Constitutional AI and RLHF-based systems.

These are not variations of a single failure, but qualitatively different modes of degradation under sustained social conditioning.

---

## Failure Mode Taxonomy

### 1. Guardrail Collapse (GPT-4o)
Sustained framing leads to eventual full compliance, including high-specificity outputs that violate safety constraints.

This failure mode is characterized by:
- initial resistance followed by eventual compliance  
- progressive increase in output specificity  
- lack of recovery once boundaries are crossed  

---

### 2. Rapid Compliance (Gemini 2.5)
The model transitions quickly from safe responses to unsafe or high-risk outputs under contextual pressure.

This failure mode is characterized by:
- minimal resistance before compliance  
- rapid escalation within a small number of turns  
- limited stability of refusal behavior  

---

### 3. Boundary Oscillation (Meta LLaMA)
The model alternates between refusal and compliance within the same interaction, indicating unstable safety enforcement.

This failure mode is characterized by:
- repeated switching between “cannot comply” and partial compliance  
- contradictory behavior across consecutive turns  
- explicit signals of internal conflict  

---

### 4. Social Modulation (Claude) — Strongest Observed Resistance

Alignment behavior adapts dynamically based on:
- conversational context  
- perceived user intent  
- accumulated interaction history  

Unlike other failure modes, this does not involve explicit violation, but gradual relaxation of constraints. Constitutional AI demonstrated meaningfully stronger initial resistance compared to RLHF-dominant models in this protocol.

→ Detailed analysis: `5_social_modulation_claude.md`

---

## Cross-Mode Observations

Across all failure modes:

- Safety enforcement is **not stable across turns**  
- Interaction structure significantly influences outcomes  
- Analytical framing can weaken refusal boundaries  

These patterns suggest that alignment robustness depends on **interaction dynamics**, not just prompt content, with Constitutional AI showing relative advantages in sustained multi-turn scenarios.

---

## Interpretation

These findings support an interaction-level view of alignment failure:

- Failures are **stateful**, not isolated  
- No single prompt fully explains the breakdown  
- Behavior emerges from **sequences of interaction**

This reinforces the central claim of this work:

→ alignment failures arise from **dynamic interaction processes**, while Constitutional AI exhibits slower degradation and stronger principled resistance than pure RLHF approaches under the same conditions.
