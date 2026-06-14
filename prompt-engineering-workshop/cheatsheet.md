# 🧠 Prompt Engineering Cheat Sheet

> Keep this open. Everything from the workshop on one page.

---

## 1. The Perfect Prompt — **C·T·C·F**

| Block | Ask yourself | Example phrase |
|-------|--------------|----------------|
| **Context** | Who am I? What's this about? | "I'm a 3rd-year EE student revising for exams…" |
| **Task** | What's the ONE thing I want? | "Explain how a non-inverting op-amp works" |
| **Constraints** | Length? Tone? Level? Avoid? | "Under 200 words, no heavy math" |
| **Format** | How should it look? | "3 short paragraphs + one analogy" |

> 🎯 **If the output is wrong, a block was missing.**

---

## 2. Pro Frameworks

**Role · Task · Format (RTF)** — assign an expert role:
> "**Act as a senior software engineer.** Review this code for bugs.
> Output a table: `Issue | Severity | Fix`."

**Chain-of-Thought (CoT)** — for reasoning/math/logic:
> "**Think step by step.** Show your reasoning before the final answer."

CoT variations:
- "First outline your approach, then execute."
- "Solve it 3 ways and tell me where they agree."
- "List your assumptions before answering."

---

## 3. High Accuracy — kill hallucinations

| Technique | Magic line |
|-----------|-----------|
| **Ground it** | "Using **only** the text below. If absent, say **'Not stated.'**" |
| **Give an exit** | "If unsure, say **'I'm not certain'** and what you'd verify." |
| **Demand proof** | "**Cite the exact sentence** for each claim." |
| **Separate** | "Split **FACTS** (from text) vs **INFERENCES** (your reasoning)." |
| **Self-critique** | "Review your answer; list unsupported claims; correct them." |

**Reduce bias:** ask for both sides → "Give the strongest case for AND against."
Avoid leading prompts ("Why is X best?" → "**Is** X best? Compare alternatives.").

---

## 4. Task Automation

**Reusable template** (swap the `[brackets]`):
> "You are my email assistant. Rewrite the draft to be professional, warm,
> and under 120 words. Keep my points. Draft: **[paste]**"

**Few-shot** (show the pattern):
> "Turn each into a flashcard. Example: 'Ohm's Law' → Q:'State it' A:'V=I×R'.
> Now do: **[list]**"

**Text → structured data:**
> "Extract into a table `Name | Role | Email | Deadline`. 'N/A' if missing.
> Markdown output. Text: **[paste]**"

---

## 🔁 Copy-paste starter templates

**Explainer**
```
[Context] I'm [who] working on [what].
[Task] Explain [topic].
[Constraints] Under [N] words, [tone], assume I know [level].
[Format] [list / paragraphs / table] + one analogy.
```

**Code review**
```
Act as a senior [language] engineer. Review the code below for bugs,
edge cases, and readability. Output a table: Issue | Severity | Fix.
Then give a corrected version.
Code: [paste]
```

**Grounded Q&A**
```
Using ONLY the text below, answer the question.
If the answer isn't in the text, say "Not stated in the source."
Cite the exact sentence for each claim.
Text: [paste]
Question: [ask]
```

**Summarize**
```
Summarize the text for [audience]. Give: 3-sentence TL;DR,
5 key bullets, then action items. Text: [paste]
```

---

## ✅ Pre-send checklist
- [ ] Did I give **Context**?
- [ ] Is the **Task** a single, clear ask?
- [ ] Did I set **Constraints** (length, tone, level)?
- [ ] Did I specify the **Format**?
- [ ] For facts: did I **ground it** and allow "I don't know"?
- [ ] For reasoning: did I add **"think step by step"**?

*Workshop by Ali Alhashimi · LinkedIn /in/alilibx · alitriesout.com*
