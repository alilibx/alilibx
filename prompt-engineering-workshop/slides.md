---
marp: true
theme: default
paginate: true
title: Mastering Prompt Engineering for Professional Productivity
---

<!--
SLIDE DECK — paste into Marp, reveal.js, Slides.com, or Google Slides.
Each `---` is a new slide. Speaker notes are in HTML comments.
Total: ~30 content slides for a 90-minute teaching block.
-->

# Mastering Prompt Engineering
## for Professional Productivity

**IEEE Sudan Workshop**
Ali Alhashimi — AI Solutions Architect

<!-- Welcome people as they join. Drop a poll in chat: "How often do you use AI tools? Daily / Weekly / Rarely / Never" -->

---

## Agenda

1. **The Evolution of Generative AI**
2. **The Anatomy of an Effective Prompt**
3. **Advanced Prompting Patterns & Logic**
4. **Ethics, Accuracy, and Practical Application**

➡️ 90 min learning + practice, then **30 min open Q&A**

<!-- Set expectation: this is hands-on. Have your AI tool open. -->

---

## Ground rules

- 🎤 Mics off, **questions in chat anytime**
- ⌨️ Keep your AI assistant open — **you'll be typing**
- 🧪 Every concept = **a bad prompt vs a good prompt**
- 🤖 Works on **any** model: Claude, GPT, Gemini, Copilot

---

# Agenda 1
## The Evolution of Generative AI

---

## From rules to reasoning — a 70-year sprint

- **1950s–80s · Rule-based AI** — humans hand-code every "if-then." Brittle.
- **1990s–2000s · Machine learning** — systems *learn patterns* from data.
- **2012 · Deep learning** — neural nets crack images and speech.
- **2017 · The Transformer** — "Attention Is All You Need." The unlock.
- **2018–2022 · Large Language Models** — GPT, BERT scale up; language clicks.
- **2022 → now · Generative AI for everyone** — ChatGPT, Claude, Gemini;
  text, code, images, audio, agents.

<!-- Keep it fast — this is the "how we got here" arc, not a history lecture. The point: capability exploded, so the skill of *directing* it is now the differentiator. -->

---

## What changed: we stopped programming, started *instructing*

- Old world: tell the computer **exactly how** (code every step).
- New world: tell the model **what you want** — in plain language.

➡️ The interface to this power is **natural language**.
➡️ So your results depend on **how well you ask**. That's prompt engineering.

---

## What "generative" actually means

These models **predict the next token** (word-piece) from everything before it.

- 🟢 Strength: fluent, flexible, creative, fast.
- 🔴 Catch: "plausible" is the goal — **not "true."**

This single fact explains both the magic *and* the hallucinations
we'll tame later today.

---

## The model is not the bottleneck. The prompt is.

Same model. Same question. Wildly different answers.

> ❌ "write something about climate"

> ✅ "You are an environmental science tutor. Write a 150-word
> explainer on how rising temperatures affect the Nile's water
> supply, for a first-year engineering student. Use a numbered
> list of 3 mechanisms. Plain English."

<!-- Live demo: run both side by side. Let the contrast land before explaining why. -->

---

## A prompt is an instruction, not a search query

- Google: keywords → links
- LLM: **clear intent → generated answer**

You are not *searching*. You are **directing**.
Vague direction → vague work. Precise direction → useful work.

---

# Agenda 2
## The Anatomy of an Effective Prompt
### The **C·T·C·F** structure

---

## The 4 building blocks

| Block | Question it answers | Example |
|-------|--------------------|---------|
| **C**ontext | Who/what is this about? | "I'm a 3rd-year EE student…" |
| **T**ask | What exactly do you want? | "Explain how an op-amp works" |
| **C**onstraints | What are the rules/limits? | "Under 200 words, no jargon" |
| **F**ormat | How should it look? | "As a bulleted list with one analogy" |

<!-- This is the spine of the whole workshop. Get them to memorize CTCF. -->

---

## Before → After

**❌ Before**
> "explain op amps"

**✅ After (CTCF)**
> **[Context]** I'm a 3rd-year electrical engineering student revising for an exam.
> **[Task]** Explain how an operational amplifier works in a non-inverting configuration.
> **[Constraints]** Under 200 words, assume I know basic circuit theory, no heavy math.
> **[Format]** 3 short paragraphs + one real-world analogy.

<!-- Run the After live. Then tweak ONE constraint and re-run to show control. -->

---

## Why each block earns its place

- **Context** → relevance (the model tailors to *you*)
- **Task** → a single, clear deliverable (avoid 5 asks in one)
- **Constraints** → length, tone, level, what to avoid
- **Format** → makes output *usable* (table, list, JSON, email)

🧠 Rule of thumb: **if the output is wrong, a block was missing.**

---

## 🧪 Exercise 1 — Rebuild a prompt (10 min)

Take this weak prompt and rebuild it with **CTCF**:

> "help me with my report"

Then run it. Share your improved version in chat.

<!-- Circulate the shared doc. Pick 2 to read aloud — one strong, one to improve together. -->

---

# Agenda 3
## Advanced Prompting Patterns & Logic

---

## Pattern 1 — Role · Task · Format (RTF)

Assign the model an **expert role** to shift its tone and depth.

> **Role:** Act as a senior embedded-systems engineer.
> **Task:** Review this C function for memory-safety bugs.
> **Format:** Table of `Line | Issue | Severity | Fix`.

🎭 The role primes vocabulary, assumptions, and standards.

<!-- Demo: run the same code review WITHOUT the role, then WITH. Compare depth. -->

---

## RTF: pick the right expert

| Your goal | Useful role |
|-----------|-------------|
| Debug code | "senior software engineer" |
| Polish writing | "professional editor" |
| Study help | "patient tutor who asks me questions" |
| Career | "technical recruiter / hiring manager" |
| Research | "skeptical peer reviewer" |

---

## Pattern 2 — Chain-of-Thought (CoT)

For **reasoning, math, logic, multi-step** problems:

> "**Think step by step.** Show your reasoning before the final answer."

- Forces the model to *work the problem*, not guess
- Catches its own mistakes mid-stream
- You can **inspect** the logic, not just trust the result

<!-- Demo: a word problem or unit conversion. Run without CoT (often wrong), then with. -->

---

## CoT variations worth knowing

- **"Let's think step by step."** — the classic trigger
- **"First outline your approach, then execute it."** — plan then do
- **"Solve it 3 ways and tell me where they agree."** — self-consistency
- **"List your assumptions before answering."** — surfaces hidden guesses

---

## 🧪 Exercise 2 — Role + Reasoning (10 min)

Pick ONE:
- **A)** Ask an assistant to review a snippet of your code as a "senior engineer."
- **B)** Give it a tricky logic/math problem with **"think step by step."**

Notice: how did the role or CoT change the answer?

<!-- Ask: "Who got a different answer with vs without step-by-step?" Hands up / chat. -->

---

# Agenda 4
## Ethics, Accuracy & Practical Application

<!-- This block has three movements: (a) accuracy/anti-hallucination, (b) ethics & responsible use, (c) putting it to work / automation. -->

---

## Part A — Accuracy
### Killing hallucinations & bias

---

## What is a hallucination?

The model states something **false with full confidence** —
fake citations, invented APIs, wrong dates, made-up quotes.

⚠️ It's not lying. It predicts plausible text.
**Plausible ≠ true.**

Your job: **engineer the prompt so truth is the easy path.**

---

## Technique 1 — Ground it

Give the model the source material; forbid outside info.

> "Using **only** the text I pasted below, answer the question.
> If the answer isn't in the text, say **'Not stated in the source.'**"

✅ This single line prevents a huge share of made-up answers.

<!-- Demo: paste a short doc, ask something NOT in it. Show it correctly refusing. -->

---

## Technique 2 — Give it an exit

Models hallucinate partly because they feel they *must* answer.

> "If you are not sure, say **'I'm not certain'** and explain what
> you'd need to verify."

Permission to say "I don't know" → fewer confident fabrications.

---

## Technique 3 — Demand verifiable structure

> "For each claim, cite the exact sentence from the source."
> "Separate **FACTS** (from the text) from **INFERENCES** (your reasoning)."

Forcing citations/labels makes fabrication obvious to *you*.

---

## Technique 4 — Self-critique pass

Run a second prompt on the model's own output:

> "Review your previous answer. List any claims you cannot
> support, and any assumptions you made. Then correct them."

🔁 The "second look" catches errors the first pass missed.

---

## Reducing bias

- Ask for **multiple perspectives**: "Give the strongest case for AND against."
- Request **counter-evidence**: "What would change this conclusion?"
- Watch **leading prompts**: "Why is X the best?" *assumes* X is best.
  Ask "**Is** X the best? Compare alternatives."

---

## Part B — Ethics & responsible use

- 🔒 **Privacy** — don't paste secrets, personal, or proprietary data into
  consumer tools. Assume what you paste may leave your control.
- 🎓 **Academic & professional integrity** — use AI to *learn and draft*, not to
  submit work you can't explain. Follow your institution's/employer's policy.
- 📚 **Attribution & verification** — you own the output. Check facts, citations,
  and code before you ship or submit.
- ⚖️ **Bias awareness** — training data carries human bias; question confident
  claims about people, groups, and "best" choices.

<!-- Frame ethics as part of being a good engineer, not a compliance checkbox. -->

---

## The one rule that covers most of it

> **You are accountable for what you do with the output — not the model.**

Treat AI as a brilliant, fast, occasionally-wrong intern:
delegate generously, **verify before you trust**, and keep the final
judgment yours.

---

## 🧪 Exercise 3 — Trust but verify (10 min)

1. Paste a short paragraph (notes, an abstract, an email).
2. Ask a question **partly answered and partly not**.
3. Add: *"Use only the text; say 'Not stated' if missing; cite sentences."*

Did it stop making things up?

---

# Part C — Practical Application
## Task Automation: get your time back

---

## The repetitive work AI eats for breakfast

- 📄 **Summarize** long PDFs, papers, meeting notes
- ✉️ **Draft & reply** to emails in your voice
- 💻 **Generate / explain / refactor** code & write tests
- 📊 **Extract structured data** from messy text → table/JSON
- 📚 **Study aids**: flashcards, quizzes, analogies from your notes

---

## Power move — the reusable template

Build a prompt **once**, reuse it forever with `[brackets]`:

> "You are my email assistant. Rewrite the draft below to be
> professional, warm, and **under 120 words**. Keep my main points.
> Draft: **[paste]**"

Swap the bracket each time. **This is automation without code.**

---

## Power move — few-shot examples

Show the pattern you want with 1–2 examples:

> "Turn each item into a flashcard. Example:
> Input: 'Ohm's Law' → Q: 'What is Ohm's Law?' A: 'V = I × R'.
> Now do these: [list]"

Examples beat explanations. The model copies the pattern.

---

## Power move — text → structured data

> "Extract from the text below into a table:
> `Name | Role | Email | Deadline`.
> If a field is missing, write 'N/A'. Output as Markdown."

Turn unstructured chaos into something you can actually use.

<!-- Demo: paste a messy paragraph of meeting notes, get a clean table. Crowd-pleaser. -->

---

## 🧪 Exercise 4 — Automate one real task (8 min)

Pick a **real** recurring task from your week and build a
**reusable template** for it (summary, email, code, flashcards…).

Save it. You'll use it tomorrow.

<!-- Ask 2-3 people to share the template they built. -->

---

# Wrap-up

---

## The whole workshop on one slide

- **Evolution** — we moved from *programming* to *instructing* in plain language
- **Anatomy: CTCF** — Context · Task · Constraints · Format
- **Patterns: RTF + Chain-of-Thought** — expert role + "think step by step"
- **Ethics & Accuracy** — ground, cite, self-critique; verify before you trust
- **Practical: templates + few-shot + structured output** — automation

🎯 *If output is wrong, a block was missing. You own the output, not the model.*

---

## Your homework

1. Rebuild your **3 most-used prompts** with CTCF.
2. Save **one reusable template** you'll use weekly.
3. Next time the AI is "wrong," ask: **which block did I skip?**

📄 Grab the **cheat sheet** — it has all the templates.

---

# Q&A
## 30 minutes — ask me anything

Connect: LinkedIn `/in/alilibx` · `alitriesout.com`

<!-- Use qna-prep.md. If quiet, seed with: "A question I get a lot is..." -->

---

# Thank you! 🙏
### Go engineer better prompts.
