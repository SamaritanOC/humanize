![Humanize](https://smbconsultants.ai/wp-content/uploads/2026/04/Humanized-2.png)

# Humanize

**A Claude Cowork Skill**

Strip the AI out of AI written copy. Keep everything else exactly as it is.

## What it does

Humanize is a Claude Cowork skill that rewrites AI generated copy to remove every detectable AI writing pattern the inflated vocabulary, the em dashes, the fake profundity — without touching your meaning, your length, or your intent.

It works through seven categories of AI tells on every pass:

- **AI vocabulary**: "pivotal," "tapestry," "underscore," "delve," "vibrant," and 50+ others
- **Em dashes** :replaced completely with commas, colons, or sentence breaks. No em dashes remain in the output.
- **Puffery and fake significance**: trailing significance claims, hollow legacy phrases, unsupported impact language
- **"Not just X, but Y" patterns**: collapsed into plain, direct statements
- **Mechanical bold formatting**: over-bolded key terms cleaned up to readable prose
- **Chatbot sign-offs**:  "I hope this helps," "Let me know if..." deleted
- **Knowledge-cutoff disclaimers**: AI boilerplate hedges removed or rewritten as plain factual statements

After each pass, the skill delivers a plain-language change report covering exactly what was changed and why. It then asks whether you want further edits or to download the result as a Word doc (.docx), plain text (.txt), or Markdown (.md) file.

## How to use it

No slash commands. Once installed, activate it with natural language:

- "Humanize this"
- "Make this sound human"
- "Remove the AI tells"
- "This sounds like ChatGPT, fix it"
- "Clean up the AI writing"

Paste your text and the skill does the rest.

## How to install

1. Download or clone this repo
2. Open Claude Cowork and go to **Settings**
3. Select **Capabilities**, then **Skills**
4. Click **Upload Skill** and select the `Humanize` folder (zipped)
5. Toggle the skill on and start a new conversation

## Changelog

### v1.1.0 - 2026-05-10

Structural refactor to align with the Anthropic Agent Skill standard. No change to the rewrite logic; the skill produces the same output on the same input as v1.0.0.

- Moved `license: MIT` to a top-level key per standard
- Added top-level `compatibility` field, platform-agnostic
- Added `metadata.homepage` pointing to https://smbconsultants.ai
- Extracted the AI vocabulary list to `references/ai-vocabulary.md` and wired it into SKILL.md
- Added `VERSION.md` and `README.md`
- Removed author/homepage block from SKILL.md body; now lives in `metadata`
- Expanded vocabulary list from ~37 entries to ~59, organized into five sections: high-priority replacements, corporate/consultancy tells, inspirational/aspirational tells, marketing/lifestyle tells, and inflation tells
- Added three new throat-clearing opener patterns: "In an era where...", "At the heart of...", "It's worth noting that..."
- Removed all em dashes from SKILL.md body (self-consistency fix the skill's own hard rule is em dash elimination)
- Added em dash check to the Step 3 final review pass

### v1.0.0 - Initial release

- Humanize rewrites AI generated copy to remove detectable AI writing patterns across seven categories: overused vocabulary, structural patterns, puffery and significance inflation, copula avoidance, formatting artifacts, collaborative chatbot language, and knowledge-cutoff disclaimers
- Em dashes are eliminated entirely
- The skill preserves the original meaning, length, and intent throughout
- After each pass, it delivers a plain-language change report and offers further edits or file download in Word, plain text, or Markdown
- Activated via natural language, no slash commands required

---

Part of The Samaritan Project

This tool was built for and extracted from [The Samaritan Project](https://buymeacoffee.com/thesamaritanproject): a build-in-public, self-hosted, multi-agent OSINT and intelligence research platform built on OpenClaw running on Parrot OS bare metal.

Support The Samaritan Project at [buymeacoffee.com/thesamaritanproject](https://buymeacoffee.com/thesamaritanproject)

---

## License

MIT-free to use, modify, and distribute.

---

## About the developer

[Harold Mansfield](https://linkedin.com/in/haroldmansfield/),  AI Consultant & Integration Specialst | Sec+ CySA+
