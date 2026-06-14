# Facilitator Guide — Minute-by-Minute Script

> Run this with `slides.md` on screen and a chat assistant open in a second window
> for **live demos**. Timings are guidelines — protect the exercise time; trim talk if needed.

**Legend:** 🎤 = say it · 🖥️ = live demo · 🧪 = participants do it · 💬 = chat interaction

---

## 0:00 – 0:05 · Welcome & poll

🎤 **Open warmly (1 min).**
"Welcome, everyone. In the next two hours you'll stop *chatting* with AI and start
*directing* it. By the end you'll have a structure you can use today, plus a cheat
sheet to keep."

💬 **Poll (1 min).** Drop in chat: *"How often do you use AI tools? Daily / Weekly / Rarely / Never."*
Read the room out loud — it tells you how deep to go.

🎤 **Agenda (1 min).** Walk the four blocks: (1) Evolution of Generative AI,
(2) Anatomy of an Effective Prompt, (3) Advanced Patterns & Logic,
(4) Ethics, Accuracy & Practical Application — then 30 min Q&A.

🎤 **Ground rules (1 min).** Mics off, questions in chat anytime, keep your AI tool
open — you'll be typing.

---

## 0:05 – 0:18 · Agenda 1 — The Evolution of Generative AI

🎤 **The arc (4 min).** Walk the timeline slide: rule-based AI → machine learning →
deep learning → the **2017 Transformer** → LLMs → today's generative AI for everyone.
Keep it fast. The point isn't history — it's: *capability exploded, so the skill of
**directing** it is now the differentiator.*

🎤 **The shift (2 min).** "We went from *programming* (tell the computer exactly how)
to *instructing* (tell the model what you want, in plain language). The interface to
all this power is natural language — so your results depend on how well you ask."

🎤 **What 'generative' means (2 min).** Models predict the next token to produce
*plausible* text. Plausible isn't always true — that one fact explains both the magic
and the hallucinations we'll tame in Agenda 4.

🖥️ **The hook demo (5 min).** Run these two live, side by side:
- ❌ `write something about climate`
- ✅ `You are an environmental science tutor. Write a 150-word explainer on how rising temperatures affect the Nile's water supply, for a first-year engineering student. Use a numbered list of 3 mechanisms. Plain English.`

Let the difference land. "Same model. I changed the *instructions*. That's prompt
engineering — a skill, not a trick. Let's learn the structure behind it."

---

## 0:18 – 0:42 · Agenda 2 — The Anatomy of an Effective Prompt (CTCF)

### Mini-talk (0:18–0:30)

🎤 Introduce the 4 blocks (slide "The 4 building blocks"). Spell it: **C-T-C-F**.
- **Context** — who you are, what this is about → drives *relevance*.
- **Task** — the ONE thing you want → keep it singular.
- **Constraints** — length, tone, level, what to avoid → drives *control*.
- **Format** — list, table, email, JSON → makes it *usable*.

🖥️ **Demo (Before → After).** Run `explain op amps`, then run the full CTCF version
from the slides. After the good one lands, **change one constraint live** (e.g.,
"now make it under 80 words") to show how constraints give you a control panel.

🎤 **Land the rule:** "If the output is wrong or off, you almost always skipped a block.
Diagnosing prompts becomes: *which block is missing?*"

### 🧪 Exercise 1 (0:30–0:42)

🧪 Post in chat/shared doc:
> Rebuild this weak prompt with CTCF, then run it:
> **"help me with my report"**

Give them ~8 min to write + run. Circulate the shared doc.
💬 Pick **2 submissions**: read a strong one aloud, then improve a weaker one *together*
live by naming the missing block. End on time.

---

## 0:42 – 1:06 · Agenda 3 — Advanced Prompting Patterns & Logic (RTF + CoT)

### Mini-talk (0:42–0:54)

🎤 **RTF (Role-Task-Format).** "CTCF is the foundation. RTF is a fast variant: give
the model an expert *role* and it shifts vocabulary, depth, and standards."

🖥️ **Demo the role effect.** Take a short buggy code snippet (keep one ready):
- First: "find issues in this code" (generic).
- Then: "Act as a senior embedded-systems engineer. Review this C function for
  memory-safety bugs. Output a table: Line | Issue | Severity | Fix."
Compare the depth and structure.

🎤 **Chain-of-Thought.** "For anything with *reasoning* — math, logic, multi-step —
add *'think step by step.'* It makes the model work the problem instead of guessing,
and you can inspect the logic."

🖥️ **Demo CoT.** Use a small word problem or unit conversion. Run once plain (often
sloppy/wrong), then with "think step by step, show reasoning before the answer."
Mention the variations: plan-then-do, solve-3-ways, list-assumptions.

### 🧪 Exercise 2 (0:54–1:06)

🧪 Post:
> Pick ONE:
> **A)** Review a snippet of your code as a "senior engineer."
> **B)** Give a tricky logic/math problem with "think step by step."

💬 After ~9 min: "Who got a *different* (better) answer with the role or step-by-step?"
Take 1–2 quick shares.

---

## 1:06 – 1:30 · Agenda 4 — Ethics, Accuracy & Practical Application

> Three movements: **(A) Accuracy → (B) Ethics → (C) Practical/Automation.**

### Mini-talk — Part A: Accuracy (1:06–1:14)

🎤 **Define hallucination.** "The model states false things confidently — fake
citations, invented functions, wrong facts. It's not lying; it predicts plausible
text. Plausible isn't true. We engineer prompts so truth is the easy path."

Walk the 4 techniques (one slide each):
1. **Ground it** — "Using only the text below… if not present, say 'Not stated.'"
2. **Give an exit** — "If unsure, say 'I'm not certain' and what you'd verify."
3. **Demand verifiable structure** — cite exact sentences; separate FACTS vs INFERENCES.
4. **Self-critique** — "Review your last answer; list unsupported claims; correct them."

🖥️ **Demo grounding.** Paste a short paragraph, then ask something **not** in it with
the grounding line. Show it correctly answering "Not stated in the source." This is
the money demo — it visibly *stops* the model from making things up.

### Mini-talk — Part B: Ethics & responsible use (1:14–1:17)

🎤 Walk the ethics slide as *good-engineering practice, not a compliance checkbox*:
- **Privacy** — don't paste secrets/personal/proprietary data into consumer tools.
- **Integrity** — use AI to learn and draft, not to submit work you can't explain;
  follow your institution's/employer's policy.
- **Verification & attribution** — you own the output; check facts, citations, code.
- **Bias** — training data carries human bias; question confident claims and avoid
  leading prompts ("Why is X best?" → "**Is** X best? Compare alternatives.").

🎤 **Land the one rule:** "You're accountable for what you do with the output — not the
model. Treat it like a brilliant, fast, occasionally-wrong intern: verify before you trust."

### 🧪 Exercise 3 — Trust but verify (1:17–1:24)

🧪 Post:
> 1. Paste a short paragraph (notes, abstract, email).
> 2. Ask a question that's only *partly* answered by it.
> 3. Add: "Use only the text; say 'Not stated' if missing; cite the sentence."

💬 "Did it stop inventing answers?" Quick shares.

### Mini-talk — Part C: Practical application / automation (1:24–1:29)

🎤 "Now we make it *save you time*." Walk the use cases (summaries, emails, code,
data extraction, study aids), then the three power moves:
- **Reusable template** with `[brackets]` — automation without code.
- **Few-shot examples** — show 1–2 examples; the model copies the pattern.
- **Text → structured data** — messy text into a clean table/JSON.

🖥️ **Demo the crowd-pleaser.** Paste a messy paragraph of "meeting notes" and extract
to a table: `Name | Role | Email | Deadline`, "N/A" for missing, Markdown output.

🧪 **Take-home (Exercise 4).** "Build a reusable template for one recurring task this
week — summary, email, code, flashcards. Save it; you'll use it tomorrow." (If you're
ahead of time, give 5 min now and take 2–3 shares.)

### Recap (1:29–1:30)

🎤 **Recap on one slide.** Read the "whole workshop on one slide" summary. Give the
homework. Point everyone to the cheat sheet.

---

## 1:30 – 1:55 · Open Q&A

🎤 "That's the toolkit. Now — ask me anything." Use `qna-prep.md`.
If it's quiet, seed it: *"A question I get a lot is… 'Which AI tool should I use?'"*
Keep answers tight (~2 min each) so more people get in.

## 1:55 – 2:00 · Close

🎤 Recap the 4 agenda blocks in one breath. Thank them. Share LinkedIn `/in/alilibx` and
`alitriesout.com`. Remind them to download the cheat sheet. End on energy:
*"Go engineer better prompts."*

---

## ⏲️ If you're running behind

- **Trim** the Evolution timeline to one slide and one CoT variation.
- **Make Exercise 4 take-home** (it already is) and shorten others to 5 min.
- **Never** cut the live demos or the ethics rule — highest-value minutes.

## 🆘 If a live demo flops

- Have **screenshots of good outputs** ready as a fallback.
- Narrate it: "This is exactly the unpredictability we're taming today" — turn it
  into a teachable moment, then show the saved good result.
