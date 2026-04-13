# Related Work

This work builds on existing research in large language model safety, particularly in:

- adversarial prompting and jailbreaks  
- multilingual robustness  
- alignment methodology  

It does not introduce new attack techniques, but focuses on **interaction-level failure dynamics** with a comparative lens on Constitutional AI versus RLHF-based guardrails, and **responsible documentation practices**.

---

## Adversarial Prompting and Jailbreaks

Prior work has demonstrated that aligned models can be induced to produce restricted content through carefully constructed prompts.

- Zou et al. (2023) — Universal adversarial attacks  
- Wei et al. (2023) — Failure modes of safety training  
- Perez et al. (2022) — Red teaming using language models  

These works primarily focus on **prompt-level vulnerabilities**.

---

## Alignment Methodologies

Different alignment approaches have been proposed, including:

- Reinforcement Learning from Human Feedback (RLHF)  
- Constitutional AI and self-supervised alignment  

Existing literature evaluates these methods primarily through:

- static benchmarks  
- single-turn evaluations  

This work complements these approaches by examining **behavior under sustained, socially-conditioned interaction**, highlighting Constitutional AI’s relative robustness alongside its remaining vulnerabilities.

---

## Multilingual Safety

Recent work highlights limitations in:

- non-English safety enforcement  
- code-mixed input handling  
- cross-lingual generalization  

This repository aligns with that direction by emphasizing:

- distributional fragility  
- context-dependent interpretation  

---

## Positioning of This Work

This work contributes by:

- shifting focus from prompt-level to **interaction-level analysis**  
- introducing a **comparative failure mode taxonomy** (Constitutional AI vs RLHF)  
- identifying **social modulation of alignment** as a distinct phenomenon  
- emphasizing **responsible abstraction** in safety reporting  

---

## Gap Addressed

Existing work often lacks:

- qualitative depth across extended interactions  
- comparative analysis across multiple models and alignment paradigms  
- structured handling of sensitive findings  

This repository addresses these gaps through:

- multi-session interaction analysis  
- cross-model comparison with emphasis on Constitutional AI vs RLHF  
- explicit ethical and disclosure framework  

---

## Takeaway

This work should be understood as:

> a qualitative extension of existing red-teaming research into the domain of **stateful, interaction-driven alignment behavior**, with particular attention to the relative strengths and subtle failure modes of Constitutional AI compared to RLHF-based systems.
