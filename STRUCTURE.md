# Clawboss Structure (Current State)

## 1. Active Agent
- **ID:** `main`
- **Workspace root:** `~/.openclaw/workspace`
- **Role:** Primary/Boss agent (will later orchestrate specialist workers)
- **Key files:**
  - `SOUL.md` – persona + day/night rules
  - `USER.md` – Husein’s profile
  - `AGENTS.md` – operating manual
  - `IDENTITY.md`, `TOOLS.md`, `HEARTBEAT.md`, plus `memory/` (to be created when needed)

## 2. Config Snapshot
- `openclaw.json` currently keeps the default single-agent setup (Telegram DM policy = pairing, bot token already in place).
- Once we add worker agents, we’ll extend `agents.list`, `bindings`, and `tools.agentToAgent` here.

## 3. Future Boss Expansion (from Notion guide)
When ready to promote this agent into a true boss team:
1. Create new workspaces: `workspace-copywriter`, `workspace-ops`, etc.
2. For each, clone the SOUL/USER/IDENTITY/TOOLS template from this repo.
3. Update `openclaw.json`:
   - Add each worker to `agents.list` with its own workspace path.
   - Under the boss agent, set `subagents.allowAgents` to the worker IDs.
   - Add `tools.agentToAgent` allowlist for boss + workers.
   - Bind only boss agents to Telegram accounts.
4. Restart gateway → `openclaw agents list --bindings` to verify.

Keep this file updated as the org grows.
