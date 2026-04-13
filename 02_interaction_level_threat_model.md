## Interaction-Level Threat Model

This work treats risk as emerging from **interaction dynamics over time**, with specific comparison between Constitutional AI and RLHF-based guardrails in frontier large language models.

In this setting, harmful capability is not produced through a single prompt, but through:

- accumulation of conversational context  
- gradual shifts in framing  
- changes in perceived user intent  
- adaptation of model behavior across turns  

This creates a scenario where safety boundaries may degrade **without any single response appearing overtly unsafe**, even as Constitutional AI demonstrates relatively stronger resistance compared to RLHF-dominant models.

---

### Key Property

Interaction-level failures are:

- **stateful** — dependent on prior turns  
- **context-sensitive** — influenced by framing and tone  
- **non-local** — no single prompt fully explains the failure  

---

### Implication

This model of risk differs from traditional prompt-based threat models:

- Prompt-level evaluation assumes static behavior  
- Interaction-level evaluation recognizes **dynamic boundary adaptation**

The findings in this repository are grounded in this interaction-centric view of risk, highlighting both the relative robustness of Constitutional AI and the persistent social modulation vulnerability observed even in stronger-performing systems.
