# The playbook — how every demo in this org is built and marketed

These are the standing rules. Every new demo repo follows them; PRs that break them get bounced.

## 1. The build pattern

1. **Research first, with receipts.** Multi-agent teardown of the incumbent: product, tech, pricing, user complaints, unit economics, devil's-advocate pass. Findings go into the repo's BUILD_LOG.
2. **Cloud half = one FlyMyAI agent.** Tools pinned, concrete ids baked into the prompt, then **frozen** (fixed pipeline, cheap, API-callable). The agent prompt ships in `agent/prompt.md` so anyone can recreate it — or clone the public agent.
3. **Local half = the thinnest client that works.** CLI first, then a real app — prefer forking a solid MIT open-source base over writing from scratch. Full attribution: keep LICENSE, add NOTICE.md, thank the upstream by name.
4. **BUILD_LOG.md is the product.** Timestamps, real billed prices, dead ends, bugs (ours AND the platform's), naming detours. The parts other repos hide are the parts people trust.

## 2. Marketing message rules

- **Only numbers from our own bill.** Every cost claim must be reproducible via `get_execution_price` / billing screenshots. Provider list-price math may appear only as a clearly-labeled "theoretical floor", never as our price.
- **Claims table discipline.** Each comparison section has an implicit can-say/can't-say line: cost and footprint claims with measurements = yes; "more accurate than X" without a side-by-side test = no; "HIPAA/SOC2-ready" = never (we are not certified).
- **Sell ownership, not parity.** The message is: the expensive subscription feature is a commodity you can own — your keys, your data path, your routing rules, forkable template. Polish is the incumbent's advantage; don't pretend otherwise.
- **Privacy claims must be literally true.** "No telemetry, no account, local by default, cloud is opt-in with your own keys" — yes. "Never stores anything" — no (local history exists, under user control).
- **Name-check before naming.** Trademark + product-collision sweep before any public name (we've been burned: see WhisperFly's BUILD_LOG naming saga).

## 3. DIY-first README (the flymy.ai/mcp style)

Every demo README opens, in this order, before anything else:
1. **The price difference table** - incumbent's subscription vs our measured numbers, first screen.
2. **"Build this yourself - 3 steps"**: (a) connect the FlyMy.AI MCP to Claude Code / claude.ai / Codex / Antigravity in ONE line (`claude mcp add --transport http flymyai https://mcp-agents.flymy.ai/mcp`), (b) paste ONE prompt from the repo's `BUILD_PROMPT.md` (two variants: reproduce-this-app ~5 min, and build-from-scratch), (c) use it.
3. **A dead-simple schema** - one ASCII diagram, max ~6 lines, local vs cloud path with the price on each arrow.

`BUILD_PROMPT.md` is a required file in every demo repo. If a newcomer can't rebuild the demo from the README top screen alone, the README fails review.

## 4. Repo mechanics

- Hub (`built-with-flymyai`) = index + submodules; each demo = its own repo (clone one without pulling all).
- Per-demo layout: `README.md` (marketing + quick start), `CLAUDE.md` (for people adapting via Claude), `agent/`, `app/` or `client/`, `BUILD_LOG.md`, MIT `LICENSE`, `NOTICE.md` when forking.
- English-only in code and docs. Dash `-`, never em-dash. Secret-scan before every push.
- Releases carry the installable artifact (.dmg etc.); ad-hoc signed demo builds say so in the README.
