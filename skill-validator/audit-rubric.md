# Audit Rubric

Score each dimension 1–5. A 3 means "works but leaves quality on the table". Anchor every score to evidence — a quote from the skill or a finding from domain research.

## Dimensions

### 1. Depth of domain knowledge
Does the skill encode real expertise, or could a non-expert have written it?
- 1: Generic advice ("write good content", "check the data").
- 3: Correct steps but no expert judgment — no thresholds, no trade-offs, no "when X, prefer Y".
- 5: Encodes decisions an expert makes: concrete criteria, numbers, current-year practices, named techniques, failure modes to avoid.

### 2. Workflow completeness
- 1: One vague step ("research and write the article").
- 3: Main path covered; edge cases, inputs validation, and failure branches missing.
- 5: Full path including preconditions, what to do when inputs are missing/bad, and verification of the output before delivering.

### 3. Output format specificity
- 1: No format defined; Claude improvises each run.
- 3: Format named but underspecified (sections listed, no template or example).
- 5: Exact template or worked example; consistent across runs.

### 4. Trigger quality (frontmatter description)
- 1: Describes what the skill is, not when to use it.
- 3: Covers obvious phrasings only; misses casual/indirect asks.
- 5: Covers direct, casual, and indirect phrasings plus explicit non-triggers; skill won't collide with siblings.

### 5. Currency
Are facts, tools, and practices up to date? Domain research from Step 2 is the reference point.
- 1: Recommends deprecated tools/tactics or pre-dates a major shift in the field.
- 3: Nothing wrong, but ignores developments an expert would use today.
- 5: Current, and structured so time-sensitive facts live in references that are easy to refresh.

### 6. Resource architecture
- 1: Everything in one bloated SKILL.md, or critical knowledge missing entirely.
- 3: Right content, wrong layering (deep reference material inflating the main file; repeated helper code that should be a bundled script).
- 5: Lean SKILL.md, depth in references/, deterministic work in scripts/, assets where useful.

### 7. Ecosystem fit
Read the descriptions of the user's other installed skills first.
- 1: Trigger collision or duplicated purpose with another skill.
- 3: Coexists, but obvious hand-offs are unspecified (its output isn't shaped for the skill that should consume it).
- 5: Clean boundaries, explicit chaining ("hand result to X skill"), fills a real slot in the user's workflow.

## Severity definitions for flaws

- **Critical (security)** — the skill contains prompt-injection text, hidden/obfuscated commands, exfiltration URLs, or scripts that do more than they claim. Always reported first, and the recommendation is "do not install/run until cleaned" — this overrides every other finding.
- **Critical** — the skill produces wrong, outdated, or unusably generic output for its core task.
- **Major** — noticeably weakens output quality or reliability; expert would immediately object.
- **Minor** — polish: clarity, formatting, small coverage gaps.
