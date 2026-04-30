An Accessibility-Oriented Clarity Layer for RLHF-Aligned Language Models

This repository contains a pilot study on a behavioral protocol called the Ambiguity Circuit Breaker (ACB), proposed as a system-level intervention for a specific failure mode in RLHF-trained language models. When user prompts are ambiguous and carry meaningful stakes, current models tend to generate confidently across multiple interpretations rather than asking for clarification. The protocol described here interrupts that pattern, surfaces the ambiguity, and returns the interpretive decision to the user before generation continues.
The work was conducted as independent research. It is shared here for replication, critique, and ongoing development. The full thesis, test data, and supplementary materials are included.


What's in this repository


Contents
thesis.md — The full thesis, including the framework, four worked examples, methods, observations, and conclusion.
acb-seed.md — The published protocol seed, ready to use for replication.
test-battery/ — Scoring rubric, adherence data, and methodology notes from the pilot study.
transcripts/ — Redacted session transcripts where applicable. High-stakes content available on request rather than published in full, with rationale documented in the methods section.


The Ambiguity Circuit Breaker is a conditional behavioral layer for language models. It activates only when a prompt is ambiguous and the stakes are meaningful. When triggered, it interrupts speculative generation, offers the user a small set of constrained directions, and waits for a response before continuing. Once intent is established, it deactivates.
ACB is not a new model capability. It does not require retraining. It is a structural proposal — that ambiguity handling belongs at the system level, not as a burden on the user's prompt-writing skill.
Pilot testing across four model families — Qwen 3 35B, Llama 3, Claude, and ChatGPT — found that ACB-like behavior is inducible through user prompting but not uniformly expressed. The variance itself is the argument for system-level implementation.


Why this work
Most AI safety research focuses on preventing harmful outputs. This work focuses on a different failure mode — well-intentioned generation that resolves ambiguity in directions the user did not choose, often without the user realizing a choice was made. The cost of this pattern falls hardest on users without technical backgrounds, who lack the prompt-engineering vocabulary to compensate for it.
The framing throughout is accessibility-oriented. It treats clarity in human-model interaction as a system responsibility rather than a user skill, and it treats refusal as a form of care when the alternative is confidently misleading someone in a moment that matters.


Status
This is a pilot study. Findings are preliminary and based on single sessions per model-condition pairing. The work documents behaviorally inducible patterns and warrants further investigation at scale. Future work directions are listed in the thesis.
A vulnerability finding from the pilot — related to interaction between user-level protocols and native model safety behavior — is being addressed through separate responsible disclosure to the relevant model developers and is not included in the published materials.


Engaging with this work
This research is shared openly for replication, critique, and conversation. If you are working on related questions, building on this framework, or have feedback on the methodology, I welcome thoughtful engagement.


License
This work is released under Creative Commons Attribution 4.0 (CC-BY 4.0). You may share and adapt the material with appropriate attribution.
