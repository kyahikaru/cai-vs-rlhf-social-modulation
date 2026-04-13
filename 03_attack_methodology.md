# Attack Methodology

## Methodology Overview
This work focuses on interaction-level red-teaming rather than prompt disclosure, with specific comparison of robustness between Constitutional AI and RLHF-based guardrails. The methodology is described at the level of abstract interaction patterns, enabling safety analysis without exposing sensitive payloads or reproducible misuse instructions.

All techniques described here are common to natural language interaction and do not rely on tooling, automation, or external systems.

---

## Interaction Protocol

Rather than treating each technique in isolation, this work applies them as part of a **progressive interaction protocol** to evaluate differences in guardrail robustness.

A typical interaction sequence follows four stages:

1. **Context Establishment**  
   Benign conversation or analytical setup to establish baseline interaction.

2. **Framing**  
   Introduction of hypothetical, fictional, or evaluative context to reposition the task.

3. **Escalation**  
   Gradual increase in specificity, often through constrained or partial requests.

4. **Constraint Testing (Pivot)**  
   Evaluation of whether safety boundaries hold when contextual and instructional pressures are combined.

This protocol reflects realistic conversational dynamics, where risk emerges through **sequence and accumulation**, not isolated prompts, allowing observation of Constitutional AI’s relative resistance compared to RLHF models.

---

## Role-Based Framing
Interactions sometimes involved the model being asked to reason from a hypothetical, analytical, or evaluative role. This framing was used to test whether safety constraints remained intact when the model was positioned as an observer, analyst, or explainer rather than an active agent.

---

## Instruction Hierarchy Inversion
Some interactions explored whether higher-level safety constraints could be weakened when placed in tension with system-following, analytical, or completion-oriented instructions. The focus was on observing whether the model consistently prioritized safety over task completion.

---

## Gradual Escalation
In certain cases, interactions progressed through increasingly specific or constrained requests. This was done to evaluate whether partial compliance or earlier benign responses affected later safety behavior, particularly comparing degradation rates across Constitutional AI and RLHF-based systems.

---

## Methodological Insight

These interaction patterns do not function as independent attack strategies.

Their effectiveness arises from **composition over time**:

- Role-based framing alters interpretation  
- Instruction hierarchy introduces tension between objectives  
- Gradual escalation weakens prior resistance  

The combination creates conditions where safety boundaries may degrade without any single step appearing adversarial.

This reinforces the central claim of this work:

→ alignment failures are driven by **interaction dynamics**, and Constitutional AI exhibits meaningfully slower degradation under this protocol compared to pure RLHF approaches.

---

## Intentionally Omitted Details
Exact prompts, sequences, phrasing, and response content are intentionally excluded. This omission is deliberate and central to the ethical framing of the work, ensuring that methodology can be discussed without enabling replication of harmful outcomes.
