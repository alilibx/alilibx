# Q&A Prep — 30 Minutes

> Anticipated questions with strong, concise answers. Keep replies ~2 min so more
> people get in. If the room is quiet, **seed** with a ⭐ question.

---

## ⭐ Tools & getting started

**"Which AI tool should I use?"**
They're more alike than different — the *techniques today work on all of them*.
Start with whatever is free and accessible to you (Claude, ChatGPT, Gemini, Copilot).
Pick one, get fluent, then compare. The skill transfers; the tool is interchangeable.

**"Are the free versions good enough?"**
For learning prompt engineering, absolutely. Paid tiers give bigger context windows,
newer models, and higher limits — useful once you hit walls, not before.

**"Is it cheating to use AI for my studies/work?"**
It's a tool, like a calculator or IDE. The line is *understanding*. Use it to learn
faster, draft, and check your thinking — not to submit work you can't explain.
Always follow your institution's/employer's policy.

---

## ⭐ Accuracy & trust

**"How do I know it's not making things up?"**
Assume it *might*. Engineer against it: ground it in your source, allow "I don't know,"
demand citations, and run a self-critique pass (Module 3). For anything important,
**verify independently** — treat output as a confident draft, not a fact.

**"It gave me fake references / a function that doesn't exist. Why?"**
That's hallucination — it predicts plausible text, and fake citations *look* plausible.
Fix: ask it to only use sources you provide, and verify every citation/API yourself.
Never trust a reference you haven't opened.

**"Does longer / more detailed always mean better prompts?"**
No — *clearer* beats *longer*. Add detail that removes ambiguity (constraints, format,
context). Padding that doesn't change the task just adds noise.

---

## ⭐ Technique deep-dives

**"When do I use Chain-of-Thought vs just asking?"**
Use CoT for *reasoning*: math, logic, debugging, multi-step planning. For simple
lookups or short rewrites it's unnecessary overhead.

**"What's the difference between CTCF and RTF?"**
Same DNA. CTCF is the full foundation (Context, Task, Constraints, Format). RTF is a
fast variant that leads with an expert **Role**. Use CTCF to be thorough; reach for
RTF when the *persona* is what matters (review, critique, tutoring).

**"How many examples for few-shot?"**
Usually 1–3. Examples teach the *pattern* better than explanations. If output drifts,
add one more example that covers the edge case it's missing.

**"What is a 'token' / context window?"**
The model reads/writes text in chunks called tokens (~¾ of a word). The context window
is how much it can "hold in mind" at once. Huge documents may need chunking or
summarizing in stages (prompt chaining).

**"Should I be polite / does 'please' help?"**
It doesn't meaningfully change quality. *Clarity and structure* do. Be polite if you
like — just don't mistake politeness for precision.

---

## ⭐ Practical / professional

**"Can it help with coding even if I'm a beginner?"**
Yes — for explaining code, generating examples, writing tests, and debugging. But
read and understand what it gives you; verify it runs. It accelerates a learner, it
doesn't replace learning.

**"How do I reuse prompts efficiently?"**
Build templates with `[brackets]`, save them in a notes app or doc, and swap the
brackets each time. That's the 80/20 of "automation" without any code.

**"Is my data safe? Can I paste confidential info?"**
Treat anything you paste as potentially leaving your control. Don't paste secrets,
personal data, or proprietary material into consumer tools. Check the provider's data
policy; many offer enterprise tiers with stronger guarantees.

**"Will prompt engineering still matter as models improve?"**
The *mechanics* get easier, but the core skill — communicating intent clearly and
verifying output — only grows in value. Better models reward better direction.

---

## 🧰 Backup prompts to demo live during Q&A

- **"Rewrite this prompt to be better"** — paste a participant's prompt; improve it together.
- **Grounding demo** — paste a paragraph; ask for something not in it; show the refusal.
- **Step-by-step demo** — a logic puzzle, run with and without CoT.

---

## 🎬 Closing (last 5 min)

1. Recap the 4 modules: **CTCF → RTF/CoT → Accuracy → Automation.**
2. Homework: rebuild your 3 most-used prompts; save one reusable template.
3. Cheat sheet link + connect on LinkedIn `/in/alilibx`, `alitriesout.com`.
4. "Go engineer better prompts." 🚀
