# AGENTS.md — building apps on the FlyMy.AI agentic cloud

You are a coding agent building an app whose backend is a FlyMy.AI cloud agent. Follow this file; it encodes everything the WhisperFly build learned the hard way.

## Setup

The FlyMy.AI MCP must be connected (`https://mcp-agents.flymy.ai/mcp`, HTTP transport, OAuth sign-in). Key tools: `search_tools`, `list_configured_tools`, `execute_tool`, `create_agent`, `run_agent`, `get_run`, `freeze_agent`, `run_frozen`, `get_execution_price`, `set_agent_public`, `copy_agent`.

## The build pattern

1. **Research first.** Tear down the incumbent: features, pricing, user complaints, unit economics. Write findings into `BUILD_LOG.md` with timestamps as you go - the log is a deliverable, not scratch.
2. **One cloud agent, frozen.** Design a single FlyMy.AI agent that does the whole server-side job. Pin its tools (pass explicit tool ids to `create_agent`), bake concrete ids (database ids, channel ids) into the prompt, set a cheap model (the task is usually mechanical), effort=low. Run once, VERIFY the real side effect happened, then `freeze_agent` - frozen compilations are fixed pipelines: cheap, fast, API-callable.
3. **Thin local client.** CLI first (fastest E2E proof), then a real app - prefer forking a solid MIT open-source base over writing from scratch. Keep upstream code untouched; add ONE hook + ONE module. Full attribution: keep LICENSE, add NOTICE.md.
4. **Measure, don't estimate.** After every test run call `get_execution_price` and put the REAL billed number in BUILD_LOG. Marketing may only quote these numbers; provider list prices are a clearly-labeled "theoretical floor" at best.

## Agent-prompt rules (each one fixed a real production failure)

- **"COPY <url/id> character-for-character"** - small models RETYPE long URLs and ids with typos instead of copying them. Say it explicitly in the prompt.
- **Prefer plain-text/high-level tool actions** over hand-built JSON structures (e.g. `notion_append_text`, not raw `notion_append_block_children`) - small models format nested API JSON wrong.
- **"Never claim success for something that did not happen"** - require honest failure fields (e.g. `"append_failed": true`) or the agent will report success on partially-failed runs.
- **Enumerate the exact tool calls** ("execute EXACTLY these N calls, nothing else; never call sandbox") - otherwise the loop explores, and every extra step costs money and time.
- Reply shape: compact JSON only, so clients can parse `agent_result` directly.

## Client HTTP contract (X-API-KEY auth, base https://backend.flymy.ai/api/v1)

```
POST /agents/agent-file-chat-upload/       multipart: file, external_id       -> {public_url}
POST /agents/tasks/{agent_uuid}/run-loop/  {"variables": {...}}               -> {id}
GET  /agents/executions/{id}/              poll ~2s until completed/failed    -> {agent_result}
```

Fire-and-forget from the client's hot path: never block local UX on the cloud round-trip (~40-60s per frozen run).

## Quality bars (from PLAYBOOK.md, enforced)

- **README format**: first line "We killed <incumbent>."; one sentence "built from one prompt, Claude as the builder, FlyMy.AI agentic cloud as the backend"; Safe + Cheap bullets (literally-true privacy wording; X-times from OUR bill); <=6-line ASCII schema with prices on arrows; "Build it yourself" in 3 steps; `BUILD_PROMPT.md` is required.
- **App UX**: opens ready to use; advanced settings hidden in UI (never delete code paths); the FlyMy.AI section front-and-center with the agent id prefilled and a connect link to `https://app.flymy.ai/mcp-configs`.
- **Self-test before handoff**: agent E2E verified (side effect checked, price pulled), app built + launched + exercised. The human clicks through a working product; they never debug it.
- English-only code and docs, `-` not em-dash, secret-scan before push, MIT + attribution for forks.
