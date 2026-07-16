---
name: build-flymyai-app
description: Build a subscription-killer app on the FlyMy.AI agentic cloud - research the incumbent, create and freeze ONE cloud agent, wire a thin open-source client, measure real billed costs, and ship a repo in the killer-pitch format. Use when the user asks to build an app / clone a SaaS / "kill" a product with FlyMyAI.
---

# Build a FlyMy.AI-powered app (subscription killer)

Prereq: FlyMy.AI MCP connected (`claude mcp add --transport http flymyai https://mcp-agents.flymy.ai/mcp`). If tools like `create_agent` / `execute_tool` are missing, tell the user to connect and sign in at app.flymy.ai first.

## Procedure

1. **Start BUILD_LOG.md immediately.** Timestamped entries for every step, every real billed price, every dead end. It ships with the repo.
2. **Research the incumbent** (parallel subagents if available): features, pricing tiers, top user complaints, what's local vs cloud, unit economics. Decide the wedge: which core feature becomes free/cheap/owned.
3. **Design ONE cloud agent** that does the whole server-side job:
   - `search_tools` / `list_configured_tools` to find the integrations (Notion, Slack, whisper STT, etc.); ask the user to connect missing ones (send them to https://app.flymy.ai/mcp-configs).
   - Create any target resources first via `execute_tool` (e.g. a Notion database) and bake their concrete ids INTO the agent prompt.
   - `create_agent` with pinned tool ids, a cheap model (o4-mini-class), effort=low, an input_schema for variables, and a prompt that: enumerates the EXACT tool calls, forbids sandbox/exploration, demands compact-JSON-only replies.
4. **Prompt rules that prevent known failures** (bake all four):
   - "COPY <urls/ids> character-for-character - never retype" (small models introduce typos in long strings);
   - prefer plain-text tool actions over hand-built nested JSON (e.g. notion_append_text);
   - "never claim success for something that did not happen - report honest failure fields";
   - reply is compact JSON only.
5. **Test -> verify -> freeze.** `run_agent`, poll `get_run`; VERIFY the side effect for real (read the Notion row/message back, including page body). Fix and re-run until a clean trace (expected number of tool calls, zero retries). Then `freeze_agent` -> compilation id. Re-test the frozen run with `run_frozen`.
6. **Measure.** `get_execution_price` on every test execution. Real billed numbers go into BUILD_LOG and are the ONLY numbers marketing may quote. Compute the per-use price and the X-times-cheaper line vs the incumbent's subscription.
7. **Client.** CLI first to prove E2E (upload -> run-loop -> poll, X-API-KEY auth, base https://backend.flymy.ai/api/v1). Then the app: fork a good MIT open-source base, keep upstream intact, add ONE hook + ONE module (fire-and-forget: never block local UX on the ~40-60s cloud run). NOTICE.md attribution. Settings: enable toggle + API key + agent id (prefill the public agent; user can paste their own) + a connect link to app.flymy.ai/mcp-configs. Hide advanced UI sections, never delete code.
8. **Self-test before handoff**: agent E2E green with verified side effects and pulled prices; app built, packaged (e.g. .dmg), launched, exercised. The human receives a click-through-ready product.
9. **Repo in the killer-pitch format** (see PLAYBOOK.md in github.com/FlyMyAI/build-with-flymyai): first line "We killed <incumbent>.", Safe+Cheap bullets (literally-true privacy, own-bill numbers), <=6-line ASCII schema with prices, "Build it yourself" in 3 steps, required BUILD_PROMPT.md, CLAUDE.md for adapters, MIT license, secret-scan before push.

## Cost sanity table (why measuring matters)

Observed on WhisperFly: provider list prices suggested ~$0.005/note; the real bill was $0.256 naive -> $0.083 (o4-mini) -> $0.031 (gpt-4.1-mini) after optimization (cheaper non-reasoning model, fewer tool calls, literal JSON template). Never publish the floor as the price.
