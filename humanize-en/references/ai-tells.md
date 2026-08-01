# AI Tells — Full Reference

Complete catalog of patterns, words, and constructions that signal AI-generated text. Backed by research from EQ-Bench (Slop Score), Kobak et al. 2024 (excess vocabulary in PubMed), Matsui 2024 (medical writing AI-isms), Wikipedia "Signs of AI Writing" project, and Pangram's DAMAGE paper 2025.

This is a lookup reference. When you suspect something is AI-coded but aren't sure, check here.

## Section 1 — Forbidden vocabulary

These words appear in AI-generated text at rates 5-100× higher than human writing. Several have research-backed evidence (Kobak et al. measured "delve" increased 10× in PubMed after ChatGPT release).

### Verbs (do not use)
delve, navigate, foster, leverage, harness, embark, unlock, unleash, underscore, showcase, garner, elevate, streamline, empower, revolutionize, transform, redefine, resonate, illuminate

### Adjectives (do not use)
intricate, robust, vibrant, multifaceted, holistic, comprehensive, seamless, meticulous, commendable, paramount, pivotal, crucial, profound, transformative, groundbreaking, cutting-edge, dynamic, innovative, nuanced, deep-rooted, ever-evolving

### Nouns and metaphors (do not use)
tapestry, realm, landscape, journey, ecosystem, paradigm, fabric, mosaic, kaleidoscope, symphony, ballet, dance, testament, cornerstone, hallmark, mosaic

### Replacement strategies
When you find a forbidden word, replace based on context:
- `delve` → look, dig in, explore, get into
- `navigate` → figure out, handle, work through, deal with
- `leverage` → use
- `foster` → build, create, grow
- `harness` → use
- `robust` → strong, solid, reliable
- `intricate` → complex, detailed, specific
- `pivotal` / `crucial` → important, key, central, big
- `transformative` → drop entirely or "changes everything"
- `tapestry`, `realm`, `landscape`, `ecosystem` → context-specific concrete word, often just delete the metaphor
- `testament` → proof, sign, example
- `showcase` → show
- `underscore` → highlight, prove, show
- `resonate` → land, hit, connect
- `meticulous` → careful, exact, detailed
- `nuanced` → complex, layered, specific
- `game-changer` → drop entirely
- `thought leader` → drop entirely

### Intensifiers and false precision (test before keeping)

Unlike the lists above, these aren't banned outright. They're a tell only when they fake precision or conviction the sentence hasn't earned.

Avoid false-precision intensifiers — words that add emphasis but no meaning. Non-exhaustive list (the category is intensifiers that fake precision or conviction): exact, exactly, precisely, truly, genuinely, really, literally, simply, just, actually, very. Same for scaffolds built on them: "X is exactly what Y", "that exact moment/loop/reason", "precisely because".

Test before keeping any of them: delete the word. If only the emphasis disappears and the meaning is unchanged, leave it out. Keep it ONLY when it defends a genuine doubt about precision — a specific number ("3:00 exactly"), a literal identity ("the exact same wording"), or a correction. No doubt to defend against → cut it.

## Section 2 — Forbidden constructions

These syntactic patterns are AI fingerprints regardless of which words fill them.

### Parallel negation (highest-priority AI tell)
- "It's not X, it's Y"
- "Not just X, but Y"
- "Not only X but also Y"

These create false-profound symmetry. AI loves them. Humans use them occasionally; AI uses them 3-5 times per piece.

**Fix:** rewrite as direct claim. "It's not a tool, it's a revolution" → "This isn't a tool. It changes how the work gets done."

### Triplets of adjectives
"Innovative, transformative, and groundbreaking"
"Fast, scalable, and resilient"
"Clear, concise, and compelling"

**Fix:** cut to one or two. Or replace one with a concrete contradicting element.

### Triplets of structural elements (3 bullets, 3 paragraphs of same shape, 3 examples)
AI defaults to triplets. Use 2, 4, or 5 instead. Or use 3 but break the pattern on the last item — make it longer, more personal, or contradictory.

### Hedge openers
- "It's worth noting that..."
- "It's important to note that..."
- "It's worth mentioning that..."
- "That said,"
- "Having said that,"
- "With that being said,"
- "On the other hand,"
- "However, it's important to consider..."

**Fix:** delete the hedge, keep the substance. "It's worth noting that hiring is hard" → "Hiring is hard."

### Recap / summary closers
- "Ultimately,"
- "In conclusion,"
- "In summary,"
- "All in all,"
- "At the end of the day,"
- "When all is said and done,"
- "To sum up,"

**Fix:** delete the opening word. Or delete the entire closing paragraph and end on the previous sentence.

### Furthermore-family connectors
- "Furthermore,"
- "Moreover,"
- "Additionally,"
- "Consequently,"
- "In addition,"

**Fix:** start a new sentence with the content, not the connector.

### Pompous glue verbs
- "X serves as Y" → "X is Y"
- "X stands as Y" → "X is Y" or "X proves Y"
- "X represents a Y" → "X is a Y"
- "X constitutes Y" → "X is Y"
- "X embodies Y" → "X is Y"

### Generic CTAs and sign-offs
- "Thoughts?"
- "Agree?"
- "What do you think?"
- "Let me know your thoughts."
- "Drop a comment if you agree."
- "Share if this helped."
- "I hope this resonates."
- "I hope this helps."
- "I hope this provides value."

**Fix:** replace with experience-specific question OR delete entirely OR end on punch line.

### Excitement openers
- "I'm thrilled to share..."
- "I'm excited to announce..."
- "Excited to share..."
- "Delighted to..."

**Fix:** replace with the actual fact. "I'm thrilled to share that we raised $5M" → "We raised $5M last week."

## Section 3 — Punctuation tells

### Em-dashes (—)
The single most reliable visual AI tell. AI uses em-dashes 3-10× more than humans, often where commas, periods, or parentheses would be more natural.

**Fix:** replace EVERY em-dash. Pick:
- Comma — for parenthetical clarification
- Period — for emphatic break
- Parentheses — for true aside
- Colon — for setup-payoff
- Semicolon — rarely, for joined related thoughts

Note: en-dashes (–) for ranges are fine. Hyphens (-) for compounds are fine. The forbidden one is the em-dash (—).

### Oxford comma everywhere
AI defaults to Oxford comma in every list. Humans (especially non-American) vary. Not a death-sentence tell, but in combination with other tells — a signal.

**Fix:** mix Oxford and non-Oxford if natural. British convention favors "red, white and blue" without final comma.

### Excessive ellipses
"This was... unexpected. And... life-changing."

AI uses ellipses for fake-profundity. Humans use them sparingly.

**Fix:** delete most. Keep at most one if it genuinely serves a trailing-off moment.

### Quotation overuse for emphasis
AI quotes things that aren't quotes:
- "true" understanding
- this "approach"
- the "right" way

**Fix:** delete the quotes. Use italics if real emphasis is needed (or in LinkedIn, just rely on word choice).

## Section 4 — Structural tells

### Markdown thinking
AI was trained on markdown-formatted text. It "thinks in markdown" — defaulting to headers, bullets, bold even when context (chat, social media, email) renders them as raw asterisks.

**Tells:**
- `**Bold for labels:** explanation`
- `### Subheaders in social media posts`
- Numbered lists for content that flows naturally
- Hyperlinks formatted as `[text](url)` in plain text contexts

**Fix:**
- Strip ALL markdown formatting in LinkedIn, email, social media, casual prose.
- Keep markdown only in genuinely structured technical content (docs, README, articles with sections).
- Even in long-form, use markdown sparingly — humans rarely use 5 headers in a 1500-word piece.

### Recap closing paragraph
Almost every AI-written piece ends with a paragraph that summarizes what was just said. "So to recap, we covered X, Y, and Z. The key takeaway is..."

**Fix:** delete the entire recap paragraph. End on the substantive content.

### Bullet-then-bold-label pattern
```
- **Specificity:** This means using concrete details.
- **Brevity:** Get to the point.
- **Authenticity:** Sound like yourself.
```

This is pure AI structure. Humans rarely write this way unless in formal docs.

**Fix:** convert to flowing prose. "Three things matter: concrete details, brevity, and sounding like yourself. The first is..."

### Topic-statement openers
"Hiring is one of the most challenging aspects of running a startup."
"Marketing has changed dramatically in the last decade."
"Leadership requires many skills."

These are textbook AI openings. Generic claims with no anchor.

**Fix:** rewrite hook to be scene-anchored, contradictory, or specific. See `techniques.md` for hook patterns.

## Section 5 — Tonal tells

### Promotional brochure tone
AI defaults to mildly-promotional, mildly-formal tone — like a corporate newsletter or tourism brochure. Even when discussing failures, AI somehow makes them sound aspirational.

**Tells:**
- Every paragraph ends on an optimistic note
- Difficulties are framed as "opportunities"
- All conclusions are "growth"
- Even the hard stuff has a silver lining

**Fix:**
- Allow real pessimism, frustration, or unresolved tension.
- End paragraphs on tension, not resolution.
- Permit ambiguous or critical positions.

### Universal middle-of-the-road
AI avoids strong positions. It "considers both sides", "balances perspectives", "acknowledges the complexity".

**Fix:**
- Take a clear side.
- Acknowledge counterpoint in ONE sentence (transparent authenticity), then defend the position.
- Don't try to please everyone.

### Inflated significance
- "This marks a pivotal moment..."
- "In the ever-evolving landscape of..."
- "A profound shift is underway..."
- "Stands as a testament to..."

AI inflates ordinary observations into Significant Moments.

**Fix:** strip the inflation. State what happened in plain language. Let significance be implied, not declared.

### Over-helpfulness
AI ends pieces explaining what the reader should now do. "Now that you understand X, you can..." "With this in mind, consider..."

**Fix:** trust the reader. End on the substance. Don't explain the lesson — let the reader extract it.

## Section 6 — Content-level tells

### Generic ICP painting
"The overwhelmed founder, the exhausted executive, the struggling entrepreneur..."

AI loves abstract categorical descriptions of people. Humans tend to remember specific instances.

**Fix:**
- Replace with one specific (real or composite) person with a name, situation, and sensory detail.
- Or with one specific scene: "Founder drowning in her inbox at 11pm" rather than "overwhelmed founder."

### Frameworks and acronyms presented authoritatively
AI loves to introduce a "framework" — usually a triplet (the 3 R's, the 5 P's). Humans use frameworks when they're real, AI invents them mid-flight.

**Fix:** if the framework is real and useful, keep but anchor in a specific case. If it's invented for the piece, scrap it and replace with concrete reasoning.

### Hypotheticals over reality
"Imagine a world where..."
"Consider this scenario..."
"Picture yourself..."

These are AI markers. Humans tell stories about what actually happened, not hypotheticals.

**Fix:** convert to past-tense or present-tense specific. "Imagine being so overwhelmed you forget your sister's birthday" → "Last week, a client told me she forgot her sister's birthday for the third year running."

## Section 7 — How to use this reference

When humanizing, run the input through these checks mentally:

1. **Word scan** — any vocab from Section 1?
2. **Construction scan** — any patterns from Section 2?
3. **Punctuation scan** — em-dashes? excessive ellipses?
4. **Structure scan** — markdown? recap closer? bullet-bold pattern?
5. **Tone scan** — promotional? middle-of-the-road? inflated significance?
6. **Content scan** — generic ICP? invented frameworks? hypotheticals?

For each found tell, apply the specific fix from this reference.

Final note: the goal isn't a checklist. Some texts have all these tells and still feel okay because of strong specifics. Some texts have none of these tells and still feel AI-written because they lack life. Use this reference to fix the **mechanical** problems; use `techniques.md` to add the **substantive** humanity.
