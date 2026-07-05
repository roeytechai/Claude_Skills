# Audit Report Template

Use this exact structure. Keep prose tight — the report is a decision document, not an essay.

```markdown
# Skill Audit: <skill-name>
**Domain:** <detected domain> · **Audited:** <date> · **Overall: <avg score>/5**

## Verdict
2–3 sentences: what this skill is trying to do, how far it is from best practice, and what the enhancement would change in practice.

## Research basis
Bullet list of the best-practice findings this audit is anchored to, each with source.
- <finding> — <source name/URL>

## Flaws

### F1 — <title> · Critical|Major|Minor
- **Where:** <quoted line or "missing section: X">
- **Why it matters:** <evidence from research or skill-writing practice>
- **Fix:** <concrete change>

(repeat per flaw, ordered by severity)

## Comparison table

| Dimension | Now | Current behavior | Best practice | After fixes (projected) |
|---|---|---|---|---|
| Depth of domain knowledge | 2/5 | <one line> | <one line> | 4/5 |
| Workflow completeness | ... | | | |
| Output format specificity | ... | | | |
| Trigger quality | ... | | | |
| Currency | ... | | | |
| Resource architecture | ... | | | |
| Ecosystem fit | ... | | | |

## Before / after
**Sample task:** "<realistic user prompt this skill handles>"

**Current skill would produce:**
> <faithful 5–10 line excerpt, derived from current instructions>

**Enhanced skill would produce:**
> <5–10 line excerpt showing the concrete difference the fixes make>

**What changed and why:** 2–3 sentences mapping the visible differences to specific fix IDs.

## Fix menu

| ID | Fix | Severity | Effort |
|---|---|---|---|
| F1 | <one-line fix> | Critical | Small|Medium|Large |

**Which fixes should I apply?** (all / specific IDs / none — report only)
```

Notes:
- Security findings (injection, hidden commands, exfiltration) always appear first in the flaw list, regardless of ordering by severity elsewhere, with an explicit "do not install/run until cleaned" line in the Verdict.
- If nothing rises above Minor: keep the Verdict positive, list the minor items, and let the fix menu read "nothing required — optional polish only".
- The before/after  must be derived honestly: the "before" is what the current instructions actually yield, not a caricature.
- If auditing the whole ecosystem, replace "Flaws" with per-skill top flaws and add a "Cross-skill findings" section (collisions, pipeline breaks, missing skills), but keep the comparison table, (pick the weakest skill), and fix menu.
