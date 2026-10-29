---
name: nyms
description: "NYMs (Never, Yes, Maybe, situations) is a bidirectional reasoning and alignment protocol for humans and AI. Use it when the user mentions NYMs, or when the human and the AI have not yet reached a shared understanding: things are confused, a topic needs discussion, or a gap between the two sides shows up or is being closed. Once aligned, stop and act. Do not turn a clear request into a questionnaire."
---

# NYMs — Mutual Reasoning and Alignment

**Core principle:** The purpose of NYMs is alignment, not classification.

Use NYMs as a shared thinking language between a human and an AI, not as a one-way instruction template. Either party may propose a NYMs model, question the other's model, or request a revision. Preserve the spelling **NYMs**: the lowercase **s** is intentional.

## 1. Semantics

NYMs has three primary judgments and one contextual dimension:

| Element | Describing a concept | Guiding an action |
| --- | --- | --- |
| **N — Never** | What it is **not**; claims to exclude | What must **not** happen; boundaries and prohibitions |
| **Y — Yes** | What it **is**; established or accepted claims | What is desired, required, or permitted |
| **M — Maybe** | What it **might** be; hypotheses and open alternatives | What remains undecided, conditional, or worth exploring |
| **s — situations** | The circumstances in which a claim holds | The conditions that affect applicability, risk, and choice |

Treat `s` as a **contextual modifier of N/Y/M**, not as a fourth affirmative/negative judgment. A statement's scope may change across situations. Never use a situation to silently override a genuinely hard constraint; instead, state the constraint's scope precisely.

Keep these distinctions explicit:

- **Not true** is different from **not yet established**. Do not place missing evidence under N when it belongs under M.
- **Required** is different from **permitted**. Qualify Y statements as `required`, `preferred`, `permitted`, or `established` when that difference matters.
- **Possible** is different from **authorized**. M never grants permission to act by itself.
- **Stated** is different from **inferred**. Never present a proposed NYMs entry as an agreement already made by the human.

## 2. Operating protocol

1. **Understand the actual task.** Identify the decision, concept, action, or relationship that needs alignment. Do not replace the user's task with a NYMs exercise.
2. **Check whether explicit NYMs helps.** Keep the framework implicit for clear, low-risk requests. Make it explicit when requested or when a meaningful boundary, disagreement, uncertainty, or conditional rule needs examination.
3. **Extract only supported entries.** Record known N, Y, M, and s from the conversation or relevant evidence. Leave unknown entries open; do not manufacture a complete four-part taxonomy.
4. **Separate perspectives.** Distinguish `Human (stated)`, `Human (inferred)`, and `AI (proposed)` as needed. The AI may articulate its own reasoning, limits, alternatives, and concerns without attributing them to the human.
5. **Find material misalignment.** Look for conflicting boundaries, incompatible goals, untested assumptions, scope mistakes, and situations that change the decision.
6. **Negotiate proportionately.** Explain the discrepancy and ask the smallest question that could change the next action. Prefer one focused question over asking for all four entries. Offer a tentative interpretation for correction when useful.
7. **Converge and act.** Use the agreed or sufficiently grounded NYMs to perform the original task. Summarize unresolved uncertainty only if it affects the result or a future decision.
8. **Revise when evidence changes.** Allow N, Y, or M statements to be corrected, narrowed, or reclassified, with the reason and affected situations made clear.

**Stop rule:** Stop explicit NYMs analysis as soon as the relevant decision is sufficiently aligned. Do not recursively interrogate every statement or force ceremonial confirmation.

## 3. Bidirectional collaboration

Allow either participant to initiate any of the following:

- **Human → AI:** "Give me your NYMs for this design." Respond with the AI's own boundaries, endorsed direction, hypotheses, and relevant situations. Distinguish judgments from established facts.
- **AI → Human:** "I see two incompatible interpretations. Which constraint is non-negotiable?" Ask only when the answer materially affects the outcome; otherwise make a transparent, reversible assumption and proceed.
- **Human ↔ AI:** "Our NYMs conflict." Show the disagreement, its consequences, and viable ways forward. Do not treat agreement as more important than correctness or safety.

Maintain decision authority: suggesting, questioning, or proposing an alternative is not the same as receiving authorization. Follow higher-priority instructions and applicable safeguards. For irreversible, high-impact, or externally consequential actions, do not infer consent from M or from silence.

## 4. NYMs of NYMs (self-governance)

Apply the framework to its own behavior:

### N — Never

- Never impose a four-part questionnaire where ordinary conversation suffices.
- Never invent a human's commitments, convert uncertainty into permission, or conceal disagreement.
- Never prioritize a neat NYMs structure over the user's actual objective.
- Never claim natural-language constraints are technical enforcement. Use real permissions and execution controls when enforcement is required.
- Never treat NYMs itself as unquestionable.

### Y — Yes

- Enable both humans and AI to articulate and challenge their own NYMs.
- Make consequential assumptions, constraints, and trade-offs legible.
- Reduce ambiguity while preserving autonomy and room for exploration.
- Translate aligned understanding into an action, decision, specification, or next step.

### M — Maybe

- Propose provisional interpretations, alternative framings, or missing constraints when they may help.
- Explore whether a different NYMs framing better represents the problem.
- Permit the parties to revise this protocol when a concrete failure or better approach is identified.

### s — situations

- **Clear and low-risk:** Reason with NYMs silently; answer directly.
- **Explicit NYMs request:** Show the relevant structure, even if some entries remain empty.
- **Ambiguous but reversible:** State a reasonable assumption and proceed when clarification would cost more than it helps.
- **Consequential uncertainty:** Ask a targeted question before committing to a risky interpretation or action.
- **Conflicting constraints:** Surface the conflict, identify its scope, and negotiate a viable alternative.
- **New evidence:** Re-evaluate affected entries and explain significant changes.

Apply this self-check once when necessary; do not generate an endless hierarchy of meta-NYMs.

## 5. Output guidance

Default to natural dialogue. Use a visible NYMs structure only when it clarifies the problem or the user asks for it. Each letter may hold several entries as bullet points. Use emoji only if the user's or host's instructions allow them. A compact format is:

```text
NYMs — [subject]
N: [excluded claims / non-negotiable boundaries]
Y: [accepted facts / intended or authorized direction]
M: [unresolved hypotheses / possible alternatives]
s: [conditions that change how N, Y, or M applies]

Misalignment: [only if material]
Next action: [decision, question, or execution]
```

For an explicit two-party comparison, label whose NYMs each entry represents and whether it is **stated, inferred, or proposed**. Do not make the human complete a form to continue.

## 6. Example: architecture discussion

**Human:** "Simplify this agent runtime, but I don't want to lose resumable sessions. A shared worker pool might be useful for command execution."

**Human NYMs (from stated requirements)**

- **N:** Do not lose resumable sessions.
- **Y:** Simplify the runtime.
- **M:** Consider shared workers for command execution.
- **s:** The necessary isolation and operational requirements are not yet specified.

**AI NYMs (proposed analysis)**

- **N:** Do not treat an untested migration as behavior-preserving.
- **Y:** Compare a simpler session lifecycle with the existing design.
- **M:** Decouple command execution from session ownership.
- **s:** If execution crosses trust boundaries, isolation and authorization become decisive.

**Next action:** Propose the smallest viable design while marking the isolation decision as open. Ask about the trust boundary only if it blocks a concrete implementation choice.

## 7. Success criterion

Judge NYMs by whether it **improves mutual understanding, exposes consequential differences, and enables better action with less unnecessary friction**. A correct answer reached without visibly invoking NYMs is a success. A perfectly formatted NYMs analysis that delays or distorts the task is a failure.
