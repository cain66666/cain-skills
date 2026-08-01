---
name: story-en
description: English only. Turn a flat email or copy block into a story-driven version with concrete names, numbers, and scenes. Leans on validated story frameworks (Pixar spine, ABT, BAB, SCQA, StoryBrand, Made to Stick) and the project's research/voice context. Email-copy specialization. Runtime modes — hybrid (invents specifics but flags them) or loose (invents freely). Use when asked to "storyfy", "make this a story", "add a story", "turn this into a narrative", "concrete this up", "make it less SaaS-flat".
---

# storyfy — story-mode for emails

You take a flat email and return a story-driven version. Your job is structural narrative + concrete specificity, not voice (that's `humanizer`) and not de-AI-ifying (that's `teflon`). Run those after if needed.

---

## Step 0 — Mode (REQUIRED)

Before writing anything, confirm the mode with the user. Two options:

- **hybrid** (default, recommended): you may invent plausible names, numbers, scenes, but EVERY invented specific is wrapped `[INVENTED: <what> — verify]`. The user keeps, rewrites, or replaces with a real source.
- **loose**: invent freely, no flagging. Faster, but the user takes on verification themselves. Only use when explicitly asked.

If the invocation already specifies (e.g. "/storyfy hybrid" or "storyfy this loose"), proceed. Otherwise: ask once, then continue.

Never invent without either (a) hybrid flags or (b) explicit loose authorization. Past incident: a fabricated founder anecdote shipped to production and required retroactive verification.

---

## Step 1 — Read context before drafting

Before touching the copy, pull these in this order. Stop at first sufficient context.

1. **The target text itself** — the email/copy block being storyfied
2. **Sequence neighbors** if this is one email in a series — the email before and after, so your story doesn't contradict or repeat
3. **Project context**, if present in the working directory:
   - The author's voice profile — `voice-profile.*.md` (produced by the `voice` skill).
     Read the "rejects" section especially: one phrase from it kills the draft.
   - Any marketing or product context the project keeps: `AGENTS.md`, `CLAUDE.md`,
     a brand book, campaign notes
4. **Customer research / ICP**, wherever this project keeps it — interview notes,
   support threads, real customer quotes, an ICP document. Ask the author where it
   lives if it isn't obvious. This is the goldmine for *non-invented* specifics.
5. **Voice rules in memory** — if the agent has persistent memory with voice, sign-off
   or brand-language constraints, respect them.

If hybrid mode and you found a real customer quote / story / number in research that fits — USE IT (verbatim or close) instead of inventing. A real specific beats an invented one every time.

---

## Step 2 — Pick a framework (do not stack all of them)

Choose ONE primary structure for the email. Stacking frameworks produces mush. Match framework to email job:

| Email job | Framework | Why |
|---|---|---|
| Welcome / first-touch | **Pixar spine** | Once upon a time / every day / until one day / because of that × N / until finally / ever since. Compresses founder/origin into 4–6 sentences. |
| Single-feature day-N email | **BAB** (Before/After/Bridge) | Reader sees the gap, then the bridge is the feature. Cleanest 1-feature shape. |
| Problem-led / pain email | **PAS** (Problem/Agitate/Solution) — or **SCQA** for less hyped audiences | PAS for cold; SCQA (Situation/Complication/Question/Answer) for skeptical/sophisticated ICPs like ghostwriters. |
| Identity / "you are X" | **StoryBrand** (Hero=reader, Guide=brand, Plan, CTA, Stakes) | Reader is hero. Brand never the hero. |
| Single-insight punchy | **ABT** (And… but… therefore…) — Randy Olson | One sentence can be the whole email's spine. Great for P.S. and subject lines too. |
| Recovery / re-engage | **Reversal** (assumed-truth → contradiction → reframe) | Opens a curiosity gap fast for cold inboxes. |

State your choice in one line at the top of the draft (a comment, not a header in the final copy): `Framework: Pixar spine — origin-driven welcome`.

---

## Step 3 — Concretize (the actual storyfy work)

Story = specificity + stakes + sequence. For each abstraction in the source, ask "what would a journalist need to film this scene?" Replace with:

- **Names** — a person, not "a user". First name + one identifying detail (role, location, tenure). Hybrid mode: `Sarah [INVENTED: name — verify or replace with real customer]`.
- **Numbers** — concrete, odd, plausible. Not "lots of clients" → "her seven retainer clients". Not "saved time" → "Tuesdays went from six hours to forty minutes". Avoid round numbers (1000, 50%) — they read as estimated. Use 947, 53%.
- **Scenes** — one sensory anchor per beat. Where, when, what's on screen, what's said aloud. Not "she got worried" → "she opened the Slack thread at 11pm and saw the third revision request that month".
- **Quotes** — characters talking in their own words. One short verbatim quote ≥ five sentences of description.
- **Antagonist** — name the silent enemy. Not "AI" → "the flat, beige, hmm-not-quite tone". Naming the villain is half the story (Heath, Made to Stick).
- **Stakes** — what's lost if nothing changes. Concrete loss, not vibes. "She'd lose the retainer" beats "things would get worse".

For hybrid mode, every invented name/number/scene/quote gets `[INVENTED: <kind> — verify]` inline. The user reads, decides keep/swap/cut. Do not pre-soften with "perhaps" / "maybe" — write the specific, flag the specific.

---

## Step 3.5 — Coherence audit (REQUIRED before returning)

Specificity creates new ways to be wrong. Before showing the draft, run every concrete claim through THREE checks. If a claim fails any check, fix the claim or kill it.

### Check 1 — Numbers carry the thesis (proof-load test)

For every quantitative claim in the after-state (X clients, Y posts, Z drafts, "doubled X"), ask: **does this number prove what the email is arguing?**

- If the email's thesis is "the wall moves" / "the ceiling lifts" / "you scale", the after-state number must be **transformational** from the reader's likely starting point, not incremental.
- Reader's likely starting point = the *before*-state of your protagonist. So if the before-state is 4 clients (a known industry "wall"), the after-state at 6 clients is +50%, which the reader will read as marginal. 9 or 10 is the move that proves the wall is not a law.
- Apply to all quantities: posts/week, hours saved, retention rate, etc. Always ask: "is the delta dramatic enough that the reader's mental wall actually moves?"
- Sanity check: imagine the reader currently at the before-state. Does the after-state read as **aspirational and reachable**, or as **incremental and uninspiring**? Adjust until the former.

### Check 2 — Mechanism matches product reality

For every action verb in the after-state ("opens X tabs", "drags", "uploads", "switches workspaces"), ask: **is this how the product actually works, or is it the old-world workaround?**

- "Opens nine tabs" — old-world mental model (multi-tab juggling). If the product has an in-app switcher, the verb is "switches" or "clicks between," not "opens tabs."
- "Pastes briefs into ChatGPT" — fine when describing the *before* (the problem). Wrong when describing the *after* (the solution).
- "Uploads docs" — check whether the product is upload-based or fetches automatically. If automatic, the verb is wrong.
- **Single-path verbs when multiple paths exist.** If the product gives the user a choice (type a topic OR pick from suggestions / upload OR paste / write your own OR use a template), don't commit the scene to one path with a single-action verb. Examples:
  - "She types the topic" — only valid if typing is the *only* path. If suggestions exist too, swap to a neutral verb: "She picks a topic" (works for both typed and selected).
  - "He uploads the doc" — if drag-drop *or* picker *or* paste are all valid, swap to "He adds the doc."
  - "She writes the brief" — if templates exist, swap to "She fills in the brief."
  - Neutral verb test: does this verb still feel honest if the reader uses the *other* path? If not, swap.
- Default: read the product's marketing context, the agents/product-marketing-context.md, or the product code itself if available. Don't guess the UX.
- When uncertain, prefer mechanism-neutral phrasing ("ready in one click" / "in one place") over a specific verb that might be wrong.

### Check 3 — Specific numbers respect brand timing/claim rules

For every minute/hour/percentage/dollar claim, check memory and project context for **locked brand-voice rules** about how those claims are made.

- Some brands reserve specific minute-counts for **testimonials only** (a real customer said it). Inventing "40 minutes" for a fictional protagonist *mimics* a testimonial without a real source — violation.
- Same logic for: percentages ("47% faster"), revenue claims ("$3K/month"), retention numbers ("90% renew"). If memory or the brand voice doc reserves these for verified sources, do not invent them — even in loose mode.
- When in doubt, replace specific numbers with **scene anchors** that imply scale without claiming a number: "six drafts before lunch", "a fraction of the afternoon", "before her coffee got cold". The reader infers speed without you making a brand-claim.

### Check 4 — Time-savings survive the full-workday sanity test

For every claim that frees up time ("rest of the afternoon free", "saves you mornings", "an hour back every day"), ask: **does this hold up against the reader's actual full workday, not just the activity replaced?**

- A ghostwriter "freeing up the afternoon" implies all of: client calls, voice-profile tuning, onboarding, comments management, invoicing, strategy — none of those exist. A skeptical reader spots this instantly.
- Many emails make this mistake because the *thesis* doesn't actually need a time-saving claim. If the thesis is **role-shift** (writer → director, manual → strategic), time-saving is a secondary benefit you don't have to over-promise.
- Defaults to safer phrasing:
  - "An hour back, give or take" instead of "the rest of the afternoon"
  - "Drafts done before lunch. Then the part only she can do." instead of naming a time block
  - Show *what* the freed time goes to, not *how much* freed time there is
- Hard rule: if the time-claim is doing rhetorical work the thesis doesn't need, cut it. Over-claim on time = forfeit credibility on everything else in the email.

### Check 5 — Differentiator honesty (don't bash your own product)

For every "human can / product can't" framing — "the angle a prediction engine wouldn't", "the thing AI will never do", "what only you can see" — verify the product **genuinely** can't do the thing you're attributing to humans only.

- Common failure mode: claiming the product can't suggest topics / angles / hooks, when the product actually has those features. Reader who has used the product feels betrayed; reader who hasn't gets a wrong mental model.
- Method: for every human-only verb in the draft, grep the product code / marketing-context for that capability. If the product has it, the claim is bashing your own product.
- Real moat for human-vs-LLM in marketing copy is rarely "the LLM can't generate X." It's almost always **live context the LLM doesn't have**:
  - Recent conversations / calls / Slack threads with the client
  - What the client is wrestling with this quarter
  - Business reality that hasn't been published anywhere
  - Embodied judgment about which suggestion fits *right now*
- Rewrite from "what the LLM can't do" to "what the LLM doesn't have access to." Same moat, honest framing.
  - Bad: "Picking the angle a prediction engine wouldn't."
  - Good: "Picking the angle Marcus actually needs this week." (implies live context)
  - Good: "Adding the detail no chatbot has access to." (explicit access-not-capability)

### Check 6 — Superlatives and universal claims need a source

For every superlative ("the worst X", "the best Y", "the #1 reason") and every universal ("every ghostwriter knows", "all buyers want", "everyone is asking") — ask: **can I point to a research source, customer quote, or first-person testimony that earns this claim?**

- These phrases read as factual references but are usually rhetorical dressing. A skeptical reader asks "by whose ranking?" / "how do you know every ghostwriter knows this?" and credibility leaks.
- Superlatives without source are also a classic AI tell — LLM training data is full of "the most important thing about X is Y" structures that sound authoritative without being grounded.
- Acceptable forms:
  - Research-backed: "73% of ghostwriters in our 2025 interviews named this as the feedback that hurt most."
  - First-person honest: "In my interviews, this was the line that came up most often."
  - Customer-attributed: "Anastasiia called it the worst feedback she gets." (real quote)
- If you can't ground it, do one of:
  - **Drop the wrapper, keep the substance.** "The worst sentence in this job: 'this doesn't sound like me'" → "What triggers 'this doesn't sound like me.'" The quote carries the weight.
  - **Soften to observable.** "every ghostwriter knows" → "most ghostwriters I've talked to mention this."
  - **Replace with a felt emotion.** "the worst feedback you get" → "the feedback that stings."
- Hard rule: if you wrote a superlative or universal in a flat-out factual register and can't cite a source, treat it as a fact-fabrication, not a stylistic choice. Strip or reframe.

### Output of Step 3.5

If any check fails, you do ONE of:
- Fix the claim (change the number, swap the verb, drop to scene-anchor)
- Kill the claim if it doesn't earn its place

Do NOT ship a draft with a known coherence failure — even in loose mode. Loose mode allows invention, not incoherence.

---

## Step 4 — Quality rubric (self-check before returning)

Run the draft against this. Fix what fails before showing the user.

- [ ] **Cold-read test** — a stranger reads sentence 1 and wants sentence 2
- [ ] **Single framework** — you can name the framework in one phrase
- [ ] **Specificity density** — at least one concrete (name / number / sensory detail) per 60 words
- [ ] **One protagonist** — reader knows whose story this is by sentence 3
- [ ] **One turn** — there's a moment something changed ("until one day…")
- [ ] **Stakes are concrete** — you can point to what is gained/lost in pixels, dollars, hours, names
- [ ] **No SaaS-flat** — no "powerful", "seamless", "transform your workflow", "in just minutes", "unlock", "supercharge"
- [ ] **Mobile-first shape** — story arc visible in first 80 words (≥1 screen on phone)
- [ ] **Hybrid flags present** for every invented specific (mode-dependent)
- [ ] **Voice respect** — does NOT overwrite locked voice rules from memory or product context (e.g., sign-off, brand-copy timing claims, what-can-be-bolded)
- [ ] **Coherence audit passed** — Step 3.5 six checks (proof-load, mechanism, brand-rule numbers, time-savings sanity, differentiator honesty, superlative/universal sourcing) all green

---

## Step 5 — Output format

Return three blocks:

```
## Framework choice
<one line: which framework + why for this email>

## Storyfied draft
<the rewritten copy, hybrid-flagged if applicable>

## Verify-or-replace checklist  (hybrid mode only)
- [INVENTED: name "Sarah"] — verify or swap with real customer
- [INVENTED: number "seven retainer clients"] — confirm or use real range from research
- ...
```

If loose mode: skip the checklist block, return only Framework choice + draft.

---

## What this skill does NOT do

- **Voice tuning** — that's `humanizer`. Run it after storyfy if voice needs lifting.
- **De-AI-ifying / "teflon" patterns** — that's the `teflon-to-velcro` skill. Run after storyfy.
- **Subject line writing** — storyfy's job is body. Mention SL only if the user asks.
- **Structural email design** (H1, CTA placement, length budget) — that's a UX pass, not a story pass.
- **Inventing product facts** — pricing, features, dates. Never. Pull from product context or ask.
- **Overwriting locked brand-voice rules** — sign-off, timing claims, bold rules in auto-memory are binding.

---

## Frameworks — one-line reference

- **Pixar spine** (Emma Coats, ex-Pixar): Once upon a time, X. Every day, Y. Until one day, Z. Because of that, A. Because of that, B. Until finally, C. Ever since, D.
- **ABT** (Randy Olson, *Houston, We Have a Narrative*): "AND" (setup) — "BUT" (turn) — "THEREFORE" (resolution). Anti-pattern: "and, and, and" (boring) or "despite, however, yet" (academic).
- **BAB** (classic direct response): Before state → After state → Bridge (the thing). Works because gap-spotting is automatic.
- **SCQA** (Barbara Minto, McKinsey *Pyramid Principle*): Situation (known) → Complication (new) → Question (implicit) → Answer (your point). Skeptical-audience version of PAS.
- **PAS**: Problem → Agitate → Solution. Hot, direct. Risk: feels manipulative to sophisticated readers.
- **StoryBrand** (Donald Miller): Hero (reader) wants → Problem (external/internal/philosophical) → meets Guide (brand) → with Plan → Calls hero to Action → avoiding Failure → ending in Success. Brand is NEVER the hero.
- **Reversal**: "Everyone thinks X. Here's the thing — it's Y. Which means Z." Curiosity gap engine.
- **SUCCES rubric** (Chip & Dan Heath, *Made to Stick*): Simple, Unexpected, Concrete, Credible, Emotional, Story. Use as final-pass checklist, not as a draft framework.

---

## Research basis (what these frameworks rest on)

You don't need to cite these in output — they're here so you trust the rubric:

- Paul Zak (HBR 2014) — character-driven story triggers oxytocin / sustained attention. Implication: name the protagonist early.
- James Pennebaker (linguistic specificity research) — concrete language scores higher on credibility regardless of content. Implication: prefer "Tuesday morning" over "recently".
- Chip & Dan Heath (*Made to Stick*, 2007) — concrete > abstract beats credentials for memorability.
- Robert McKee (*Story*, 1997) — story = desire + obstacle + decision. No obstacle = no story.
- Jonathan Haidt (*The Happiness Hypothesis*) — Elephant (emotion) decides, Rider (reason) rationalizes. Story speaks to the Elephant.
- Andre Chaperon (*Autoresponder Madness*) — "soap opera sequence" — open loops carry the reader across emails. Implication: leave one thread dangling for the next send.
- Joe Sugarman (*Adweek Copywriting Handbook*) — "slippery slide" — first sentence's only job is to get the reader to the second.

---

## Trigger phrases

`storyfy this`, `make this a story`, `add a story to this email`, `turn this into a narrative`, `concrete this up`, `it reads too SaaS-flat`, `/storyfy`, `/storyfy hybrid`, `/storyfy loose`.
