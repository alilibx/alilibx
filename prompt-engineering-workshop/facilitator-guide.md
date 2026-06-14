# Facilitator Guide — Minute-by-Minute Script

> Run this with `slides.md` on screen and a chat assistant open in a second window
> for **live demos**. Timings are guidelines — protect the exercise time; trim talk if needed.

**Legend:** 🎤 = say it · 🖥️ = live demo · 🧪 = participants do it · 💬 = chat interaction

---

## 0:00 – 0:10 · Welcome & Why Prompting Matters

🎤 **Open warmly (1 min).**
"Welcome, everyone. In the next two hours you'll stop *chatting* with AI and start
*directing* it. By the end you'll have a structure you can use today, plus a cheat
sheet to keep."

💬 **Poll (1 min).** Drop in chat: *"How often do you use AI tools? Daily / Weekly / Rarely / Never."*
Read the room out loud. This tells you how deep to go.

🎤 **The core idea (2 min).**
"Most people think a better answer needs a better model. Usually it just needs a
better prompt. The prompt is the steering wheel."

🖥️ **The hook demo (5 min).** Run these two live, side by side:
- ❌ `write something about climate`
- ✅ `You are an environmental science tutor. Write a 150-word explainer on how rising temperatures affect the Nile's water supply, for a first-year engineering student. Use a numbered list of 3 mechanisms. Plain English.`

Let the difference speak. Then: "Notice I didn't change the model. I changed the
instructions. That's prompt engineering — and it's a *skill*, not a trick."

🎤 **Transition.** "Everything today builds on one structure. Let's learn it."

---

## 0:10 – 0:30 · Module 1 — The Perfect Prompt (CTCF)

### Mini-talk (0:10–0:20)

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

### 🧪 Exercise 1 (0:20–0:30)

🧪 Post in chat/shared doc:
> Rebuild this weak prompt with CTCF, then run it:
> **"help me with my report"**

Give them ~6 min to write + run. Circulate the shared doc.
💬 Pick **2 submissions**: read a strong one aloud, then improve a weaker one *together*
live by naming the missing block. End on time.

---

## 0:30 – 0:52 · Module 2 — Pro Frameworks (RTF + CoT)

### Mini-talk (0:30–0:42)

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

### 🧪 Exercise 2 (0:42–0:52)

🧪 Post:
> Pick ONE:
> **A)** Review a snippet of your code as a "senior engineer."
> **B)** Give a tricky logic/math problem with "think step by step."

💬 After ~7 min: "Who got a *different* (better) answer with the role or step-by-step?"
Take 1–2 quick shares.

---

## 0:52 – 1:14 · Module 3 — High Accuracy (anti-hallucination)

### Mini-talk (0:52–1:04)

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

🎤 **Bias (brief).** Watch leading prompts. "Why is X best?" assumes X is best. Ask
for both sides and counter-evidence: "What would change this conclusion?"

### 🧪 Exercise 3 (1:04–1:14)

🧪 Post:
> 1. Paste a short paragraph (notes, abstract, email).
> 2. Ask a question that's only *partly* answered by it.
> 3. Add: "Use only the text; say 'Not stated' if missing; cite the sentence."

💬 "Did it stop inventing answers?" Quick shares.

---

## 1:14 – 1:30 · Module 4 — Task Automation

### Mini-talk (1:14–1:22)

🎤 "Now we make it *save you time*." Walk the use cases (summaries, emails, code,
data extraction, study aids), then the three power moves:
- **Reusable template** with `[brackets]` — automation without code.
- **Few-shot examples** — show 1–2 examples; the model copies the pattern.
- **Text → structured data** — messy text into a clean table/JSON.

🖥️ **Demo the crowd-pleaser.** Paste a messy paragraph of "meeting notes" and extract
to a table: `Name | Role | Email | Deadline`, "N/A" for missing, Markdown output.

### 🧪 Exercise 4 (1:22–1:30)

🧪 Post:
> Build a **reusable template** for one real recurring task in your week
> (summary, email, code, flashcards). Save it — you'll use it tomorrow.

💬 Ask 2–3 people to paste the template they built. End the teaching block here.

🎤 **Recap on one slide.** Read the "whole workshop on one slide" summary. Give the
homework. Point everyone to the cheat sheet.

---

## 1:30 – 1:55 · Open Q&A

🎤 "That's the toolkit. Now — ask me anything." Use `qna-prep.md`.
If it's quiet, seed it: *"A question I get a lot is… 'Which AI tool should I use?'"*
Keep answers tight (~2 min each) so more people get in.

## 1:55 – 2:00 · Close

🎤 Recap the 4 modules in one breath. Thank them. Share LinkedIn `/in/alilibx` and
`alitriesout.com`. Remind them to download the cheat sheet. End on energy:
*"Go engineer better prompts."*

---

## ⏲️ If you're running behind

- **Cut** one CoT variation and the bias sub-section (mention, don't demo).
- **Shorten** exercises to 5 min and take only one share each.
- **Never** cut the live demos — they're the highest-value minutes.

## 🆘 If a live demo flops

- Have **screenshots of good outputs** ready as a fallback.
- Narrate it: "This is exactly the unpredictability we're taming today" — turn it
  into a teachable moment, then show the saved good result.
