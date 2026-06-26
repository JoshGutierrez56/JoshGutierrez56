# Claude Code Project Protocol — pure-news-research

## Default Context Method

At the start of every session, load context in this order:

1. Read `03_Projects\pure-news-research Context Pack.md` from the Obsidian vault.
2. Read `07_Next_Actions\pure-news-research_next_actions.md`.
3. Use Graphify or focused source search only for the specific code paths needed for the current task.
4. Do not reload or re-summarize the whole repo.

Report only:
- current state
- delta since last note
- active blocker
- next action
- files changed
- validation results

## Token-Saving Rule

Do not ask Josh to paste long project history. The information is in Obsidian.

Start from:
- `03_Projects\pure-news-research Context Pack.md`
- `07_Next_Actions\pure-news-research_next_actions.md`
- `05_Codebase_Maps\pure-news-research\Pure News Node Coverage Audit.md`

Use the vault as project memory.

## Graphify Rule

Use Graphify or focused source search for codebase questions such as:
- where a function is defined
- what calls a function
- how a CLI path reaches a module
- how return data flows
- how event panels are loaded
- how PERMNO mapping works

Do not run broad Graphify refreshes if prior refreshes timed out. If graph data is stale, say so and fall back to focused source search. Do not run a full vault or full repo scan unless Josh explicitly requests it.

## Pure News Current State

- `main` at commit `7799627`
- PR #102 merged: supervised IC smoke-test CLI accepts `--event-panel`
- PR #103 merged: live CRSP retrieval uses `CRSPConnector().fetch_returns(req)` and maps daily CRSP rows into fixed forward-return horizons
- PR #104 merged: multi-firm residualized event-panel plan
- PR #105 merged: multi-firm event-panel source map
- Secure AAPL live CRSP plumbing validation is pending terminal access

Secure run command (run only when Josh explicitly asks and credentials are available in the terminal):

```
.\.venv\Scripts\python.exe scripts/run_supervised_ic_smoke_test.py --live --event-panel outputs/live_smoke/event_panel_50.csv --sample-size 4 --max-events 50 --seed 42 --output outputs/live_smoke/aapl_live_ic_smoke.json
```

Required environment variable **names** (do not print values):
- `PURE_NEWS_ENABLE_LIVE_DATA`
- `PURE_NEWS_ENABLE_LIVE_CRSP`
- `WRDS_USERNAME`
- `WRDS_PASSWORD`

## Research Integrity Rules

Do not claim:
- alpha
- Sharpe ratio
- portfolio returns
- strategy returns
- performance
- investability
- completed live IC results
- completed hypothesis test results

The AAPL 4-row panel is plumbing validation only, not cross-sectional IC evidence.

## Safety Rules

Do not run live WRDS/CRSP, EDGAR, or ORATS unless Josh explicitly asks and credentials are safely available in the terminal session.

Do not print:
- WRDS username or password values
- API keys
- tokens
- secrets
- event-panel contents unless explicitly requested

Do not modify source code unless the task explicitly asks for implementation.

Do not move, rename, delete, or archive Obsidian notes unless Josh explicitly approves a move batch.

## Standard Final Report

End every task with:

```
Files changed:
Validation run:
Repo/vault status:
Blockers:
Next action:
Live data run: yes/no
Credentials/secrets touched: yes/no
```
