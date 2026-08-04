# reconcile-tasks

A Claude Code skill that reconciles a single project's PLAN.md/TODO.md against its recent git history - finding tasks the commits suggest are already done, presenting them with raw-line evidence, and applying one of four operations per task on your approval.

## When it fires

"what's actually done in project-tracker?", "audit completed work for this project", "any tasks I should check off?", "reconcile the plan with what shipped". Per-project, not fleet-wide.

## What it does

Calls `mcp__project-tracker__get_reconciliation_data`, handles cache freshness, matches unchecked tasks to commits with language judgment (no scoring layer), and presents one entry per task with the verbatim PLAN.md line + line number. On approval applies one of: check, cross out as abandoned, add a note, or leave alone.

Companion to `find-task` (which surfaces tasks to *do*).

The authoritative spec is [`SKILL.md`](SKILL.md).

**Repo:** <https://github.com/mtschoen/skills-reconcile-tasks>
