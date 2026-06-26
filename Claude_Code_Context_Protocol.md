# Claude Code Context Protocol

> Mirror of the Claude Code project protocol. Place this file in the Obsidian vault at:
> `00_System\Claude Code Context Protocol.md`

## Related System Notes

- [[OpenClaw Context Protocol]]
- [[Graphify Retrieval Protocol]]
- [[Context Packs]]
- [[pure-news-research Context Pack]]
- [[Pure News Node Coverage Audit]]

---

## Default Context Method

At the start of every Claude Code session, load context in this order:

1. Read the relevant Obsidian context pack (`03_Projects\<project> Context Pack.md`).
2. Read the relevant next-actions note (`07_Next_Actions\<project>_next_actions.md`).
3. Use Graphify or focused source search only for the specific code paths needed.
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

For pure-news-research, start from:
- `03_Projects\pure-news-research Context Pack.md`
- `07_Next_Actions\pure-news-research_next_actions.md`
- `05_Codebase_Maps\pure-news-research\Pure News Node Coverage Audit.md`

## Graphify Rule

Use Graphify or focused source search for codebase questions such as:
- where a function is defined
- what calls a function
- how a CLI path reaches a module
- how return data flows
- how event panels are loaded
- how PERMNO mapping works

Do not run broad Graphify refreshes if prior refreshes timed out. If graph data is stale, say so and fall back to focused source search.

## Safety Rules

Do not run live WRDS/CRSP, EDGAR, or ORATS unless Josh explicitly asks and credentials are safely available in the terminal session.

Do not print credential values, API keys, tokens, or secrets.

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

---

*Vault path: `00_System\Claude Code Context Protocol.md`*
