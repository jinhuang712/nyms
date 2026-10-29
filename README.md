# NYMs

**NYMs** (**N**ever, **Y**es, **M**aybe, **s**ituations) is a bidirectional reasoning and alignment skill for humans and AI, packaged as an [Agent Skill](https://docs.claude.com/en/docs/claude-code/skills) for Claude Code and Claude.

The goal is alignment, not classification: help a human and an AI see what is excluded, what is accepted, what is still open, and under which conditions each holds, then get back to the work.

## The idea

| | Describing a concept | Guiding an action |
| --- | --- | --- |
| **N — Never** | What it is **not** | What must **not** happen |
| **Y — Yes** | What it **is** | What is desired, required, or permitted |
| **M — Maybe** | What it **might** be | What is undecided or worth exploring |
| **s — situations** | When a claim holds | What changes applicability and risk |

It keeps four easily blurred distinctions explicit:

- **Not true** vs **not yet established**
- **Required** vs **permitted**
- **Possible** vs **authorized**
- **Stated** vs **inferred**

It works in both directions: the AI states its own NYMs too, instead of only organizing the human's.

## When it triggers

- You mention NYMs.
- The human and the AI have not yet reached a shared understanding: things are confused, a topic needs discussion, or a gap shows up or is being closed.

Once aligned, it stops and acts. It never turns a clear request into a questionnaire.

## Install

**Claude Code**

```bash
git clone https://github.com/jinhuang712/nyms ~/.claude/skills/nyms
```

**Claude (claude.ai)**

Zip the folder so that `nyms/SKILL.md` is inside, then upload it under Settings → Capabilities → Skills.

## Files

- [`SKILL.md`](SKILL.md) — the skill itself: semantics, protocol, self-governance, output format.
