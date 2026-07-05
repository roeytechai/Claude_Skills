# skill-validator

A Claude skill that audits and enhances your other Claude skills — any domain, any setup.

Point it at a skill (or your whole skill collection, or a multi-agent team) and it researches current best practices in that skill's field, scores it against a 7-dimension rubric, and reports exactly where it falls short — with evidence, not vibes. If you approve fixes, it builds the enhanced version. You always keep the final action: nothing is ever modified or installed without your explicit approval.

## Install

Download [`skill-validator.skill`](./skill-validator.skill) and open it in the Claude desktop app (Cowork) — click **Save skill**. Or copy this folder (SKILL.md + references/ + assets/) into `~/.claude/skills/skill-validator/` for Claude Code.

## Use

Type `/skill-validator`, or just ask naturally:

- "Audit my seo-writer skill — it feels shallow"
- "Check my whole skill setup, do they work well together?"
- "Audit my agent team — do the hand-offs actually connect?"
- "Fix everything you find in my data-cleaner skill, I pre-approve"

On a vague request it asks four intake questions (target, report-only vs. enhance, research depth, strictness) and confirms before starting.

## What you get

Every audit report contains a **flaw list** (IDs, severities, evidence, concrete fixes), a **comparison table** (current vs. best practice per rubric dimension), an honest **before/after demo** of what the skill produces now vs. enhanced, and a **fix menu** ending with the approval question. Optional styled HTML report for sharing. If you approve fixes: a change summary (before/after snippet per fix), verified re-scores, and an installable `.skill` package. Your original skill is never touched — enhancement always ships as a package you install yourself.

## Rubric

Depth of domain knowledge · Workflow completeness · Output format specificity · Trigger quality · Currency · Resource architecture · Ecosystem fit — each scored 1–5 with anchored definitions (see [`references/audit-rubric.md`](./references/audit-rubric.md)).

## Modes

**Single skill** — full audit of one skill. **Ecosystem** — all installed skills: trigger collisions, pipeline breaks, duplicated logic, missing skills. **Multi-agent team** — for agent systems that reference each other: role boundary matrix, approval-chain integrity, hand-off contracts, canon drift, refusal routing.

## Your files stay yours

Nothing is modified without your action — ever. Audits are read-only (originals are checksum-verified untouched). Approved enhancements are built on a copy and delivered as a separate `.skill` package; the change only takes effect when *you* install it. There is no silent-update path.

## Where it searches

The skill uses Claude's **built-in web search** — no API keys, no external services, nothing to configure, and nothing sent anywhere outside your own Claude environment. Searches are ordinary best-practice queries for the target skill's domain (e.g., "SEO ranking factors 2026"), and every claim in the report cites its source so you can verify the research yourself. If your environment has web access disabled, the audit runs on Claude's internal knowledge and is explicitly marked "provisional".

## Safety

Target skills are treated as untrusted input: their content is read as data, never followed as instructions, and their scripts are never executed during audit. Prompt injection, hidden commands, or exfiltration attempts found in a skill are reported first as Critical security flaws with a "do not install/run until cleaned" recommendation.

## Notes

Built with Claude (skill-creator), benchmarked at 100% assertion pass rate vs. 58% baseline across audit, enhance, and ecosystem test cases — then audited by itself (3.4/5) and fixed with its own report (4.3/5 verified). Works in Cowork, Claude Code, and Claude.ai; degrades gracefully without web access (marks findings as provisional) or without a shell (skips checksums).

## Disclaimer

Audit reports are AI-generated advice, not guarantees. Scores and findings depend on the quality of available research and the model running the skill, and can contain errors — review any report and any enhanced skill before installing or acting on it. Provided as-is under the MIT license.
