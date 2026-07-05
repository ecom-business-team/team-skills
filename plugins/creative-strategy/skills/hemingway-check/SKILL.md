---
name: hemingway-check
description: Runs a Hemingway-style readability analysis on ad scripts or brief copy. Flags hard sentences, passive voice, adverbs, and weak qualifiers. Reports estimated grade level with a target of Grade 6 or below for DTC ad copy. Use before finalizing any script or hook to ensure it reads clean and punchy.
---

# /hemingway-check

Run a Hemingway Editor-style readability check on a script, hook, or ad copy. Built specifically for DTC ad scripts where Grade 6 or below is the target.

## Usage

```
/hemingway-check
/hemingway-check [paste your copy here]
```

If no copy is provided, ask: "Paste the script or copy you want to check."

---

## What This Checks

Hemingway flags five things. You check all five:

| Flag | What it means | DTC standard |
|------|---------------|--------------|
| Grade Level | Flesch-Kincaid readability estimate | Grade 6 or below |
| Hard sentences | Long or structurally complex (20–28 words) | Rewrite or split |
| Very hard sentences | Dense, multi-clause (29+ words) | Must rewrite |
| Passive voice | "was given," "is used," "are seen" | Cut or flip to active |
| Adverbs | -ly modifiers (quickly, really, truly) | Cut or replace with a stronger verb |
| Weak qualifiers | very, really, quite, somewhat, rather, just | Cut |

---

## Process

### Step 1: Read the full copy

Take in the entire script, hook, or copy block as-is. Do not correct anything yet — just read it.

### Step 2: Estimate the grade level

Use the Flesch-Kincaid Grade Level formula as a mental model:

- **Short words, short sentences = lower grade.** 1–2 syllable words, under 15 words per sentence = Grade 4–6.
- **Mix of long words and medium sentences = Grade 7–9.** This is where most AI copy lands.
- **Multiple clauses, abstract nouns, -tion/-ment words = Grade 10+.** This is where copy loses viewers.

Estimate honestly. Don't round down to make it look good.

**Target: Grade 6 or below.**

### Step 3: Flag every problem line

Go sentence by sentence. For each sentence:

1. Count approximate words.
2. Identify sentence type (simple, compound, complex).
3. Check for: passive voice, adverbs, qualifiers.

**Highlight format — use these exact labels:**

- 🔴 **Very Hard** — 29+ words or multiple embedded clauses. Must rewrite.
- 🟡 **Hard** — 20–28 words or 2 clauses that could split. Consider rewriting.
- 🟣 **Passive Voice** — Flip to active.
- 🔵 **Adverb** — Cut or replace with a stronger verb.
- ⚪ **Qualifier** — "very," "really," "quite," "somewhat," "rather," "just" — cut.

**Only flag problems. Skip clean sentences.**

### Step 4: Output the analysis

Structure your output exactly like this:

---

**HEMINGWAY SCORE**

> Estimated Grade Level: [X]
> Target: Grade 6 or below
> Status: [PASS / NEEDS WORK / REWRITE]

---

**FLAGGED LINES**

[Quote the sentence exactly, then the flag label and a one-line fix.]

Example:

> "We've scientifically formulated this blend using the most bioavailable forms of each ingredient available."
> 🔴 Very Hard | Suggested: "We picked the forms your body actually absorbs."

> "This product was developed by veterinarians."
> 🟣 Passive Voice | Suggested: "Veterinarians developed this."

> "It's really easy to use."
> ⚪ Qualifier — Cut "really." → "It's easy to use."

---

**SUMMARY**

- Grade Level: [X] — [one line on what's driving it]
- Hard/Very Hard sentences: [count]
- Passive voice: [count]
- Adverbs/Qualifiers: [count]
- Biggest issue: [one sentence naming the pattern]

---

**CLEAN VERSION** *(only if 3 or more flags)*

Rewrite the full copy block with all flags resolved. Match the original tone and structure — don't reinvent it. Just make it cleaner and tighter.

---

## Standards for DTC Ad Scripts

These apply for every client in this workspace:

- **Hooks:** Grade 4–5. One idea. Under 12 words if possible.
- **Body copy:** Grade 5–6. One clause per sentence. No semicolons.
- **CTAs:** Grade 3–4. Direct imperative. No softening qualifiers.
- **Avoid:** -tion words (formulation, solution, application), -ment words, "leverage," "optimize," "ensure," "utilize."
- **Prefer:** short Anglo-Saxon words (get, use, stop, help, feel, work, try, start).

## Notes

This is a Claude-native Hemingway check — it does the same analysis as hemingway.app but inside your workflow so you never have to copy-paste between tools. Run it on any copy before it goes into a brief.
