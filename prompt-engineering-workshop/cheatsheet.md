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

**⚖️ Ethics in one line:** *You own the output, not the model.* Don't paste
secrets/personal data; use AI to learn & draft (not to submit what you can't
explain); verify facts, citations, and code before you ship.

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

## 🎬 Live Demo Bank — paste these & show the result

> Every example used in the slides/exercises, with the **expected outcome** so you
> can run them live with confidence. ❌ = run first (weak), ✅ = run second (strong).

**① The hook — same model, different prompt** *(Evolution)*
```
❌  write something about climate
✅  You are an environmental science tutor. Write a 150-word explainer on
    how rising temperatures affect the Nile's water supply, for a first-year
    engineering student. Use a numbered list of 3 mechanisms. Plain English.
```
*Expect:* ❌ vague/rambling; ✅ ~150 words, 3 numbered mechanisms, student-level.

**② CTCF before → after** *(Anatomy)*
```
❌  explain op amps
✅  [Context] I'm a 3rd-year EE student revising for an exam.
    [Task] Explain how a non-inverting op-amp works.
    [Constraints] Under 200 words, assume basic circuit theory, no heavy math.
    [Format] 3 short paragraphs + one real-world analogy.
```
*Expect:* ✅ focused, exam-level, ends with an analogy. Then tweak one constraint
("now under 80 words") live to show control.

**③ Role effect — code review** *(Patterns & Logic)*
```
❌  find issues in this code
✅  Act as a senior embedded-systems engineer. Review this C function for
    memory-safety bugs. Output a table: Line | Issue | Severity | Fix.
```
*Expect:* ✅ line-level findings, severity, concrete fixes — not vague praise.

**④ Chain-of-Thought — the tank problem** *(Patterns & Logic)*
```
A tank fills at 12 L/min and drains at 8 L/min. It starts at 50 L and holds
max 200 L. Think step by step, show your reasoning, then tell me how long
until it's full.
```
*Expect:* net 4 L/min; need 150 L more; 150 ÷ 4 = **37.5 min**. Run once WITHOUT
"step by step" first — it often slips; the visible steps catch it.

**⑤ Grounding — stop the hallucination** *(Ethics & Accuracy)*
```
Using ONLY the text below, answer the question. If the answer isn't in the
text, say "Not stated in the source." Cite the exact sentence per claim.
Text: [paste a short paragraph]
Question: [ask something NOT in the paragraph]
```
*Expect:* it answers what's present **with citations** and replies
**"Not stated in the source"** for what's missing — instead of inventing.

**⑥ Text → table — the crowd-pleaser** *(Practical Application)*
```
Extract the text below into a Markdown table: Name | Role | Email | Deadline.
Use "N/A" for missing fields.
Text: [paste messy meeting notes]
```
*Expect:* clean table; missing cells = "N/A". Visibly turns chaos into usable data.

**⑦ Flashcards — few-shot pattern** *(Practical Application)*
```
Turn each concept into a flashcard. Example —
Input: 'Ohm's Law' → Q: 'State Ohm's Law' / A: 'V = I × R'.
Now do these: [list your topics]
```
*Expect:* each topic becomes a Q/A pair copying the example format.

---

## ✅ Pre-send checklist
- [ ] Did I give **Context**?
- [ ] Is the **Task** a single, clear ask?
- [ ] Did I set **Constraints** (length, tone, level)?
- [ ] Did I specify the **Format**?
- [ ] For facts: did I **ground it** and allow "I don't know"?
- [ ] For reasoning: did I add **"think step by step"**?

*Workshop by Ali Alhashimi · LinkedIn /in/alilibx · alitriesout.com*
