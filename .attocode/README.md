# Swarm settings for this project


# JUST ANOTHER TEST RUN FOR FUN FOR ATTOCODE'S SWARM MODE

- **Config**: `swarm.yaml` — orchestrator, workers, budget, permissions, resilience, facts.
- **Task**: See repo root `TASK.md` for the AI coding agent landscape research task.

## Purpose

Research-heavy swarm task designed to exercise the built-in `web_search` tool.
Workers search the web extensively, synthesize findings, and write markdown reports.
Expected runtime: ~20 minutes with 3 concurrent research workers.

## Key features used

- **Facts system** (`facts:` in swarm.yaml) — Grounds all workers in temporal reality (current date, year, model names). Without this, workers hallucinate outdated dates and cite stale training data as current.
- **Artifact verification** — Quality gate checks that target files actually have content on disk before scoring. Empty files auto-fail (score 1) without even calling the judge.
- **Temporal grounding in judge prompts** — The quality gate judge knows the current date and penalizes content that references outdated years.

## Run swarm

```bash
# Create report output directory first
mkdir -p report

# From repo root (recommended: safe permissions + trace)
attocode --swarm --permission auto-safe --trace "$(cat TASK.md)"

# Paid models only (if you hit rate limits)
attocode --swarm --paid-only --permission auto-safe "$(cat TASK.md)"
```

## Resume a session

```bash
attocode --swarm-resume <session-id>
```

Session state is under `.agent/swarm-state/` when persistence is enabled.

## Output

Reports are written to `report/`:
- `00-executive-summary.md` — Key findings (written last)
- `01-open-source-agents.md` — 10 open-source agents compared
- `02-commercial-agents.md` — 13 commercial tools with pricing
- `03-benchmarks-and-evals.md` — SWE-bench, HumanEval, etc.
- `04-architecture-patterns.md` — ReAct, multi-agent, context engineering
- `05-model-providers.md` — LLM comparison matrix for code
- `06-developer-experience.md` — Surveys, adoption, pain points
- `07-market-analysis.md` — Funding, M&A, market size
- `08-recommendations.md` — Actionable takeaways

## Lessons from first run

1. **Workers need temporal grounding** — Without knowing the current date, workers wrote "as of 2024" data and cited training-era information as current. Fixed by the `facts` system.
2. **Quality gate was rubber-stamping** — The judge scored 5/5 on tasks that produced empty (0-byte) files. Fixed by artifact verification that checks files on disk before calling the judge.
3. **File name mismatches** — The task decomposer created different file names than TASK.md specified. Fixed by aligning TASK.md filenames exactly.
4. **"Budget excuse" workers** — Some workers spent their tokens explaining why they couldn't do the task instead of doing it. The philosophy and persona prompts now emphasize writing complete content.
5. **Downstream task starvation** — When task-1 permanently failed, task-8 and task-9 (which depended on all research) hung forever. Need better dependency failure propagation (TODO).
