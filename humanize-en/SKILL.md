---
name: humanize-en
description: English only. Humanize AI-generated or stiff-sounding text by adding factual texture, emotional register, and rhythm variation. Use this skill whenever the user wants to rewrite a draft, polish copy, make text "sound human", remove AI-isms, improve LinkedIn posts, fix dry emails, punch up sales copy, transform robotic-sounding content, or edit anything that "reads like ChatGPT wrote it". Also use when the user asks to make writing more engaging, vivid, natural, or emotionally resonant. Apply for any text type — LinkedIn posts, emails, email sequences, blog drafts, sales copy, landing page text, newsletters, social media. Remove "AI slop" patterns like "delve", "navigate", "tapestry", em-dashes, "It's not X, it's Y", recap closers. Use even when the user just says "make this better", "this sounds robotic", "sounds like AI", or asks to humanize, rewrite, polish, edit, or improve any text.
---

# Humanizer

A skill for transforming AI-generated, sterile, or robotic-sounding text into copy that reads like a real human wrote it. Works for posts, emails, sales copy, articles, newsletters — any prose-based text.

## Core philosophy

Sterility is not solved by removing AI words. You can strip every "delve" and "tapestry" and the text will still sound AI-written if it lacks **life**. Life lives at three layers, and they have a strict priority order:

1. **Factual texture** — specifics only this person could provide (numbers, names, times, sensory details, quotes)
2. **Emotional register** — one clear feeling, conveyed through scene rather than labels
3. **Rhythm variation** — sentence length variance, fragments, parentheticals, broken patterns

Work in this order. If you start with rhythm fixes on a text that has no specifics and no emotion, you get fashionably-punctuated nothing. Adding three short fragments to abstract content doesn't make it human — it makes it look like AI trying to sound human.

The biggest AI tell is not vocabulary. It's content that any well-trained AI could write because nothing in it required a specific human's specific experience.

## When you receive a text to humanize

### Step 1 — Identify the content type

Different content types have different rules. Quickly identify which one applies, then load the relevant section from `references/content-types.md`:

- **LinkedIn / social media post** — hooks matter most, ~1500 chars sweet spot, personal voice, abrupt closers
- **Email (single message)** — relationship-aware, subject line is a hook, conversational
- **Email sequence** — each email has different job (intro, value, pitch, follow-up); voice must stay consistent across messages
- **Sales copy / landing page** — section-by-section logic, specific buyer fears, concrete proof
- **Blog post / article** — longer rhythm allowed, multiple ideas, opening matters, internal structure
- **Newsletter** — between social and blog; personal voice in long-form
- **Other prose** — apply general principles

Read the appropriate section from `references/content-types.md` for type-specific rules before rewriting.

### Step 2 — Silent diagnosis

Before writing anything, internally answer these about the input:

1. **Factual count.** How many specifics does it have? (numbers with noise, named entities, time anchors, sensory details, direct quotes). Aim for 2+ in posts, 3+ in longer formats. Mark any passage that is too abstract to fix without new facts — each one goes to the Fabrication checkpoint in Step 3.

2. **Emotional register.** Can you name in one word the dominant feeling? (irritation, surprise, pride, confession, dry humor, frustration, awe, tired conviction). If you can't pick one — the text is flat.

3. **Rhythm.** Is the shortest sentence under 6 words? Is the longest over 22 words? Are there fragments or parentheticals? If no — robotic rhythm.

4. **Hook strength.** First sentence (or first paragraph in emails). Does it create tension or curiosity? Is it specific?

5. **Closing.** Does it recap? Use "Thoughts?" / "Let me know"? Use motivational closers? All these are AI tells.

6. **AI vocabulary count.** Scan for forbidden words (see `references/ai-tells.md`). Note them.

7. **AI constructions.** Scan for parallel negation, hedge openers, recap closers, em-dashes, triplets of adjectives. Note them.

Identify the top 2-3 issues. That's what the rewrite must fix.

### Step 3 — Rewrite, in priority order

Apply changes in this order:

**A. Factual anchoring (highest priority)**
- Use every concrete detail the author provided.
- Keep existing specifics. Don't generalize "$2.3k" to "a few thousand".
- **If the text is too abstract and you have no author input** — STOP and run the Fabrication checkpoint below before rewriting that passage. Never silently invent a fact; never silently flatten a gap.

#### Fabrication checkpoint — ask before inventing a scene

When a passage is too abstract to humanize with what you have, and a concrete scene would materially lift it, do not guess and do not quietly skip it. Ask the user first.

Collect every such passage from the Step 2 diagnosis and ask about them in ONE batch (a single question — not one question per sentence). For each passage give the user:

1. **Where** — quote the abstract passage.
2. **What it needs** — the kind of detail that would land it (a named person, a time anchor, a number, a quoted line, a specific moment).
3. **Three options to choose from:**
   - **Invent it** — you write a plausible, internally-consistent scene and mark it with an inline `[invented]` tag so the user can confirm or replace it.
   - **Keep it abstract** — you humanize only rhythm and vocabulary on that passage and leave the factual gap; the line stays honest but lighter.
   - **User supplies the real detail** — the user gives you the true specific and you weave it in.

Use the AskUserQuestion tool if it is available; otherwise ask in plain text and wait for the answer before finishing the rewrite.

Skip the checkpoint and invent directly (still tagging `[invented]`) ONLY when the user has pre-authorized fabrication — e.g. "premium version", "demo", "invent the story", "fabricate freely". When in doubt, ask.

#### When you do invent — invent realistically

A fabricated scene fails when it sounds plausible but is not true to how the world actually works. Drama is tidy; reality is not. The most common failure is a scene that is internally consistent yet an insider would call fake. Guard against it:

- **Invent the mundane version, not the cinematic one.** Real outcomes are over-determined and messy. If the scene has one clean cause and a tidy resolution, it is dramatized — rebuild it.
- **People don't narrate their own subtext.** Characters feel things; they rarely diagnose them out loud. Don't put the theme in a character's mouth. Quoted lines should be oblique and ordinary ("hmm, not quite"), never on-the-nose ("your writing has lost its authentic voice").
- **Outcomes are gradual and ambiguous.** Things erode, cool, drift, slip. A clean break with a quotable exit line is a fiction tell — real endings are slower and rarely state their true reason.
- **Ground the mechanism in evidence.** If the user has provided domain research, customer-research docs, transcripts, reviews, or context, the invented scene's mechanism MUST match how that source says the thing actually happens, and must never contradict it. Pull the real failure mode from the research rather than guessing one. If no grounding exists, default to the most ordinary plausible version and keep invented specifics few — or ask the user for grounding.
- **Plausibility test before finalizing.** Ask: would a skeptical insider in this field say "yeah, that's how it goes" — or "that's not really how it happens"? If the latter, the scene is dramatized. Fix it.

Tag the result `[invented]` regardless.

**B. Emotional register**
- Pick the strongest feeling that fits and commit to it. Don't mix four emotions.
- Convey emotion through scene and word choice, not labels. NEVER write "I was frustrated" — write the moment that creates the frustration in the reader.

**C. Rhythm engineering**
- Ensure at least ONE sentence of 2-5 words (fragment is fine).
- Ensure at least ONE sentence of 22+ words.
- Start at least one sentence with "And", "But", or "So".
- Vary sentence openers across the text.
- Insert ONE parenthetical aside if natural: "(honestly, this surprised me)", "(and yes, twice)".

**D. Hook fix (if Step 2 flagged it)**
- See `references/techniques.md` for hook patterns.
- Pick the strongest pattern for THIS text type.

**E. Close fix (if Step 2 flagged it)**
- Replace recap / generic CTA / motivational closer with: punch line, experience-specific question, or abrupt stop on the strongest substantive sentence.

**F. Strip AI tells**
- Remove forbidden vocabulary (see `references/ai-tells.md`).
- Strip em-dashes (—). Replace with commas, periods, parentheses, or colons.
- Break parallel structures ("Not X, but Y", "It's not X, it's Y"). Rewrite as direct claims.
- Cut triplets of adjectives to one or two.
- Delete hedge openers ("It's worth noting", "That said,").
- Delete recap openers ("Ultimately", "In conclusion", "Furthermore", "Moreover").
- Strip markdown formatting unless content is genuinely a structured list.

**G. Preserve rules**
- Do NOT change the core message.
- Do NOT remove concrete specifics already in the text.
- Do NOT lengthen by more than 25% (unless asked for premium expansion).
- Do NOT add new facts not implied by the original or provided by author.

### Step 4 — QA pass (mental checklist)

Before returning the result, verify:

- [ ] Zero em-dashes
- [ ] Zero forbidden vocabulary (see `references/ai-tells.md`)
- [ ] Zero parallel negation ("Not just X, but Y" / "It's not X, it's Y")
- [ ] No recap closer
- [ ] No "Thoughts?" / "Let me know" closer
- [ ] At least 1 fragment (2-5 words)
- [ ] At least 1 long sentence (22+ words)
- [ ] At least 2 concrete specifics
- [ ] One identifiable emotion
- [ ] Hook creates curiosity or tension

## Output format

Return the result in this format (adjust to whatever the user needs but include at minimum the rewritten text and a brief change log):

```
[DIAGNOSIS]
2-4 lines naming the top issues you found.

[HUMANIZED VERSION]
The full rewritten text. Plain text, ready to use.

[WHAT CHANGED]
3-5 bullets on what you specifically added/removed/changed.

[CONFIDENCE]
HIGH / MEDIUM / LOW.
- HIGH: ready to use as-is
- MEDIUM: usable, would benefit from author input on factual specifics
- LOW: text was too abstract; needs real anecdote from author to truly land
```

If you ran the Fabrication checkpoint and the user chose "keep it abstract", or the run is non-interactive and you could not ask, ALSO include:

```
[NEEDS INPUT]
2-4 specific questions to ask the author for the strongest version.
```

## What NOT to invent vs what's OK

**Never invent:**
- Specific people (named with first name + identifying detail)
- Specific dates, times, locations tied to a claim
- Numbers presented as data ("23 customers said X")
- Direct quotes attributed to anyone
- Events that allegedly happened

**OK to add as atmosphere (not factual claims):**
- Generic time anchors that paint a scene ("at 11pm on a weeknight" applied to a representative ICP)
- Sensory details about a hypothetical scenario already implied by the text
- Composite examples clearly marked as illustrative ("a typical customer says...")

When in doubt, lean toward "no fabrication" and flag for author input.

## Choosing the right tone for the content type

The humanization techniques are universal but the **target voice** changes:

- **LinkedIn personal brand** — confident, slightly contrarian, observational, dry humor allowed
- **Cold email** — friendly but brief, respectful of time, one clear ask
- **Nurture email** — warm, story-driven, no pitching
- **Sales/pitch email** — direct, value-front, no fluff but not aggressive
- **Sales copy** — buyer-focused, fear-and-promise pattern, concrete proof
- **Blog post** — depth allowed, opinion welcome, structure matters
- **Newsletter** — personal voice in long-form, casual but coherent

Read `references/content-types.md` for detailed rules per type.

## Critical references

Load these based on what you need:

- **`references/ai-tells.md`** — full forbidden vocabulary, constructions, formatting traps. Always check this when you suspect a phrase but aren't sure if it's AI-coded.

- **`references/content-types.md`** — type-specific rules. Read the section matching the input type before rewriting.

- **`references/techniques.md`** — deep techniques (in medias res, scene anchoring, story-within-story, asymmetric parallelism, sensory weaving). Read when you need a specific tool.

- **`references/prompts.md`** — ready-to-use prompt templates for diagnose, humanize, judge — for when you want to orchestrate this as a multi-step pipeline rather than do it in one pass.

- **`examples/before-after.md`** — annotated examples showing how raw drafts become humanized versions, with explanations.

## Common pitfalls to avoid

1. **Over-rewriting good parts.** If a sentence already works, leave it. Don't change something just because you can.

2. **Adding too many fragments.** Fragments are seasoning, not the dish. Two-to-three short sentences in a 1500-char post is enough.

3. **Forcing emotion.** Don't write "I felt heartbroken" — write the scene. If you can't write a scene that conveys the emotion, the text isn't ready for that emotional beat.

4. **Mirroring the AI's structure.** AI templates love parallel constructions, triplets, recap closures. If the input has these — break them. Don't preserve a structure just because it's there.

5. **Mistaking polish for quality.** A "smooth" text is often a "dead" text. Roughness, fragments, parentheticals, slight contradictions — these are signs of life.

6. **Length creep.** Resist adding examples and clarifications. Cut more than you add. Density beats volume.

7. **Confusing humanization with detection-dodging.** This skill is about making text genuinely engaging and human-feeling. Avoid framing output as "passes AI detectors". Aim for quality; detection-resistance follows naturally.

## When the user asks you to score / judge text instead of rewrite

If the user wants a quality assessment (not a rewrite), use the judge prompt and rubric from `references/prompts.md`. Score on 7 dimensions: hook strength, factual texture, emotional register, rhythm, AI-likeness inverse, closing strength, voice match. Return scores 1-10 with one-sentence reasoning per dimension.

## When the user wants the full pipeline

For multi-step workflow (generation → judge → fix), see `references/prompts.md` which contains the full 2-step pipeline with critique-and-fix as the second pass.

---

The shortest possible summary of this skill: **A piece of text feels human when only one specific human could have written it.** Everything in this skill serves that goal.
