# Version History

## v1.1.0: Refactor for Anthropic Agent Skill standard

**Released:** 2026-05-10

This is a structural refactor. No change to the rewrite logic; the skill produces the same output on the same input as v1.0.0.

### Frontmatter
- Moved `License` out of `metadata` to top-level `license: MIT` (lowercase, per standard)
- Added top-level `compatibility` field (platform-agnostic)
- Added `metadata.homepage` (https://smbconsultants.ai)

### Structure
- Added `references/ai-vocabulary.md` with the full AI vocabulary lookup, extracted from former Section 2A and explicitly wired into SKILL.md
- Added VERSION.md and README.md alongside SKILL.md
- Removed the author and homepage block from the SKILL.md body (info now lives in metadata)

### Vocabulary list expansion (in references/ai-vocabulary.md)
Added 22 additional AI tells, organized into four new sections beyond the original "high-priority replacements":
- Corporate and consultancy tells (9 entries)
- Inspirational and aspirational tells (7 entries)
- Marketing and lifestyle tells (2 entries)
- Inflation tells (4 entries)

### Self-consistency fixes
- Removed all em dashes from SKILL.md body. The skill's hard rule is em dash elimination; the instructions now follow their own rule.
- Added an em dash check as Step 3 item 6 in the final review

## v1.0.0: Initial release

Original single-file SKILL.md release. Seven categories of fixes (2A through 2G), full change report at the end of each pass.
