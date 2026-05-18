---
name: humanize
description: Rewrites AI-generated text to remove common AI writing tells, tropes, vocabulary, and punctuation patterns. Preserves the original meaning, length, and intent exactly, only the style changes. Use when the user pastes AI-generated copy and asks to "humanize", "de-AI", "remove AI tells", "make this sound human", "clean up AI writing", or similar. Also use when user says the text "sounds like ChatGPT", "sounds like AI", or asks you to "fix the robot speak". At the end of each pass, reports what was changed and offers further edits or file download.
license: MIT
compatibility: Works in any Claude environment that supports Agent Skills. No external tools, MCP servers, or network access required. Pure text-transformation skill.
metadata:
  author: Harold Mansfield, SMB Consultants
  version: 1.1.0
  category: writing
  homepage: https://smbconsultants.ai
---

# Humanize

Rewrites AI-generated copy to remove detectable AI writing patterns. The goal is to make text sound like it was written by a specific human with a clear voice, not by a committee, not by a marketing bot, not by a language model trained to please everyone at once.

## Prime Directive

**Do not change the meaning. Do not change the intent. Do not shorten or lengthen the text beyond what's necessary to remove an AI pattern.** Every sentence that comes out must say the same thing as the sentence that went in, just in a way that sounds like a person wrote it.

---

## Step 1: Intake

When the user provides text to humanize:

1. Read the full text before making any changes
2. Identify the apparent context or genre (marketing copy, blog post, email, article, etc.)
3. Note the rough tone the user seems to be going for (professional, casual, technical, etc.)
4. Then proceed to Step 2

If no text is provided, ask: "Paste the text you'd like me to humanize and I'll get to work."

---

## Step 2: Execute the Humanize Pass

Work through the text systematically, applying all of the following fixes. Track every category of change made for the report at the end.

### 2A. Strip AI vocabulary

Replace or remove the overused AI words and phrases catalogued in `references/ai-vocabulary.md`. Load that reference at the start of any humanize pass and apply every replacement that matches text in the input.

The reference is the authoritative vocabulary list. Do not rely on memory; consult it on every pass, since the list may have been updated since the last run.

Apply this principle from the reference: do not simply swap one AI word for another. Rewrite the sentence to avoid the concept being performed in an AI way.

### 2B. Fix structural AI patterns

**Negative parallelisms, "Not just X, but Y":**
Rewrite any "Not only... but also...", "It's not just..., it's...", or "Not X. Rather, Y." constructions. These are a strong AI tell. Combine into a direct statement.

Example:
- Before: "This isn't just a design tool, it's a full creative suite."
- After: "This is a full creative suite."

**Rule of three overkill:**
If a sentence lists exactly three adjectives or three parallel phrases in a row purely for rhetorical effect, cut it to two, or collapse into a single precise word.

**Em dash elimination:**
Replace ALL em dashes with commas, colons, parentheses, or sentence breaks. No em dashes should remain in the output. This is a hard rule with no exceptions. Em dashes are one of the strongest AI tells and are to be removed entirely.

**Trailing "-ing" phrases of superficial analysis:**
Cut or rewrite sentences that end with a present participle phrase tacked on to explain significance:
- "...contributing to the rich cultural heritage." → cut or integrate naturally
- "...emphasizing the importance of X." → cut or rewrite
- "...reflecting the broader trends in Y." → cut or rewrite

**Closing summary sentences that restate the paragraph:**
Delete or integrate. Humans don't summarize each paragraph they just wrote.

**Throat-clearing openers:**
- "In an era where..." / "In a world where..." → cut and start with the actual claim
- "At the heart of..." → cut or rewrite plainly
- "It's worth noting that..." → cut, just say the thing

### 2C. Fix puffery and promotional inflation

Remove or deflate language that overstates importance without evidence:

- Cut unsourced claims about significance, legacy, or broader impact unless the source text actually makes the case
- Replace vague impact language ("transformative," "revolutionary," "game-changing") with specific claims or cut them
- Remove "active social media presence" and similar filler claims
- Cut the hedge-then-inflate pattern: "While relatively little-known, X has had a significant impact on..." → just say what X actually did

### 2D. Fix copula avoidance

AI avoids "is" and "are" by substituting more elaborate verbs. Restore plain constructions where they're clearer:

- "serves as a hub" → "is a hub" (if that's what's meant)
- "features four galleries" → "has four galleries"
- "maintains a presence" → "has a presence" or "is present"
- "ventured into politics as a candidate" → "ran for office"

Only restore where it genuinely simplifies. Don't flatten deliberate stylistic verb choices.

### 2E. Fix formatting artifacts

- Remove excessive **bold** used to highlight key takeaways in a mechanical, list-item style
- Remove em dashes in bullet-point headers (the "**Term:** explanation" format with dashes)
- Convert "bullet + bold header + colon + description" lists to prose where the content supports it
- Normalize section heading capitalization. AI capitalizes Every Major Word; humans usually only capitalize the first word (unless proper nouns)

### 2F. Remove collaborative AI signaling language

Delete any text that sounds like the AI is talking to the user rather than writing for an audience:

- "I hope this helps" → delete
- "Of course!" / "Certainly!" → delete
- "Would you like me to..." → delete
- "Let me know if you'd like further refinements" → delete
- "Here is a [thing]:" as a preamble → delete or restructure as a natural intro
- "Feel free to..." → delete

### 2G. Remove knowledge cutoff disclaimers

Delete phrases like:

- "As of my last knowledge update..."
- "Based on available information..."
- "While specific details are limited..."
- "...maintains a low profile" (when used as a cover for missing info)

If the claim is needed, rewrite it as a plain factual hedge: "Details aren't publicly confirmed" instead of AI boilerplate.

---

## Step 3: Final Review

Before outputting the rewritten text:

1. Read it aloud in your head. Does it sound like a person?
2. Check: did you accidentally introduce new AI vocabulary?
3. Check: is the meaning preserved? The intent preserved?
4. Check: is the length roughly the same?
5. Check: does it flow naturally, or did you create choppy patches?
6. Check: are there any em dashes left? If yes, replace them now. Zero em dashes in the output.

If yes to all, output the text.

---

## Step 4: Output Format

Present the rewritten text cleanly, without preamble.

Then, after the text, provide a **Change Report** in this format:

---

**What was changed:**

List each category of change that was applied, with a brief example of the most notable substitution from that category. Use plain language. Be specific but concise.

Example format:
- **AI vocabulary removed:** "pivotal" → "important", "tapestry" → rewritten, "underscore" → "shows" (and 4 others)
- **Structural patterns fixed:** 2 "not just X, but Y" constructions collapsed into direct statements
- **Puffery removed:** Legacy/impact claims without evidence cut from 3 sentences
- **Em dashes eliminated:** All 5 removed; replaced with commas and sentence breaks
- **Formatting:** Section headings normalized from Title Case to Sentence case; 2 bold-header bullet lists converted to prose

---

Then ask:

> Any further edits? Or would you like to download this as a file, and if so, which format: Word (.docx), plain text (.txt), or Markdown (.md)?

---

## Guiding Principles

- **Preserve the voice that's there.** If the original has a casual tone, keep it casual. If it's formal, keep it formal. Don't impose a new personality, just remove the AI one.
- **When in doubt, cut.** AI adds filler. Humans don't need every sentence to perform significance.
- **Simple words are not dumb words.** "Is" is not weaker than "serves as." "Important" is not weaker than "pivotal." Plain is professional.
- **Don't over-humanize.** The goal is to remove the tells, not to introduce slang, errors, or an entirely new voice.
- **One pass, not a committee.** Make the changes once, clearly, and hand it back.
