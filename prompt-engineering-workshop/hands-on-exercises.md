# Hands-On Exercises & Practical Use Cases

> Participant worksheet. Each exercise has a **goal**, a **starter prompt**, and a
> **model answer** so you can self-check. Use any assistant (Claude, ChatGPT, Gemini, Copilot).

---

## 🧪 Exercise 1 — Rebuild with CTCF (Module 1)

**Goal:** Turn a vague request into a structured prompt using
**Context · Task · Constraints · Format**.

**Weak prompt:**
> "help me with my report"

**Your job:** rewrite it with all four blocks, then run it.

<details>
<summary>✅ Model answer</summary>

> **[Context]** I'm an engineering student writing a lab report on a
> bridge-rectifier experiment for a power-electronics course.
> **[Task]** Help me write the *Discussion* section interpreting my results.
> **[Constraints]** ~250 words, formal academic tone, reference ripple voltage
> and load effects, don't invent data — ask me for numbers if needed.
> **[Format]** Two paragraphs followed by 3 bullet-point takeaways.

</details>

**Self-check:** Can you point to all 4 blocks in your prompt? If output is off, which block is weak?

---

## 🧪 Exercise 2 — Role + Chain-of-Thought (Module 2)

### Option A — Expert role (code review)

**Starter:**
> "Act as a senior software engineer. Review the function below for bugs,
> edge cases, and readability. Output a table: `Issue | Why it matters | Fix`.
> Then give a corrected version.
> Code: **[paste your snippet]**"

### Option B — Chain-of-Thought (reasoning)

**Starter:**
> "A tank fills at 12 L/min and drains at 8 L/min. It starts at 50 L and holds
> max 200 L. **Think step by step**, show your reasoning, then tell me how long
> until it's full."

<details>
<summary>✅ What "good" looks like</summary>

- **Option A:** specific line-level issues, severity, concrete fixes — not vague praise.
- **Option B:** net fill rate = 4 L/min; need 150 L more; 150 ÷ 4 = **37.5 min**.
  The visible steps let you catch any slip.

</details>

**Reflect:** Did the role/step-by-step change the *quality*, not just the wording?

---

## 🧪 Exercise 3 — Trust but Verify (Module 3)

**Goal:** Stop the model from inventing answers.

**Steps:**
1. Paste a short source (lecture notes, an abstract, an email — 1 paragraph).
2. Ask a question that is **only partly** answered by the text.
3. Append this control line:

> "Answer using **only** the text above. If the answer isn't there, say
> **'Not stated in the source.'** Cite the exact sentence you used for each claim."

<details>
<summary>✅ Success criteria</summary>

- It answers the parts that ARE in the text **with citations**.
- It says **"Not stated in the source"** for the parts that aren't — instead of guessing.

</details>

**Bonus — self-critique:** Reply with:
> "Review your previous answer. List any claim you cannot support from the text,
> and any assumption you made. Then correct them."

---

## 🧪 Exercise 4 — Automate a Real Task (Module 4)

**Goal:** Build ONE reusable template you'll actually use this week.
Pick a track:

### Track A — Summarizer
> "Summarize the text below for **[busy professor / my future self / a teammate]**.
> Give: 3-sentence TL;DR, then 5 key bullets, then any action items.
> Text: **[paste]**"

### Track B — Email assistant
> "Rewrite my draft to be professional, warm, and **under 120 words**. Keep my
> main points and a clear ask. Draft: **[paste]**"

### Track C — Study flashcards (few-shot)
> "Turn each concept into a flashcard. Example —
> Input: 'Ohm's Law' → Q: 'State Ohm's Law' / A: 'V = I × R'.
> Now do these: **[list your topics]**"

### Track D — Text → table (data extraction)
> "Extract the text below into a Markdown table: `Name | Role | Email | Deadline`.
> Use 'N/A' for missing fields. Text: **[paste messy notes]**"

**Deliverable:** Save your finished template somewhere you'll find it. Swap the
`[brackets]` each time — that's automation without writing code.

---

## 🎁 Stretch challenges (if time / for later)

1. **Prompt chaining:** Use the output of one prompt as the input to the next
   (e.g., summarize a paper → turn the summary into 10 quiz questions).
2. **Persona + format combo:** "As a skeptical peer reviewer, critique my abstract
   in a `Strength | Weakness | Suggestion` table."
3. **Constraint stress-test:** Take a good prompt and tighten ONE constraint at a
   time (word count, reading level, tone). Watch how output shifts — that's *control*.
4. **Refusal test:** Deliberately ask for something not in a source. A
   well-grounded prompt should make the model decline gracefully.

---

## 📝 Reflection (last 2 minutes)

- Which technique will you use **tomorrow**?
- Which of your everyday prompts was missing a CTCF block?
- What's the one reusable template you're keeping?
