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

## 3. The README format (same everywhere, killer-pitch style)

Short. Punchy. In this exact order, all on the first screen:
1. **"We killed <incumbent>."** - first line, verbatim. Then one sentence: built from **one prompt**, Claude as the builder, **FlyMy.AI cloud** as the backend.
2. **Two bullets: Safe + Cheap.** Safe = local-first / no data leaves the machine without opt-in / no account, no telemetry (literally true wording only). Cheap = the X-times-cheaper line computed from OUR bill, with the core feature at $0 when it is.
3. **"How we did it"** - one ASCII schema, max ~6 lines, local vs cloud path with the price on each arrow. One sentence: open-source app + one frozen FlyMy.AI agent, that's the whole product.
4. **"Build it yourself"** - 3 plain-language steps: (a) one-line MCP connect (`claude mcp add --transport http flymyai https://mcp-agents.flymy.ai/mcp`; claude.ai / Codex / Antigravity: same URL), (b) paste ONE prompt from the required `BUILD_PROMPT.md`, (c) use it.
5. Then and only then: numbers table, honest quality paragraph, links to BUILD_LOG / CLAUDE.md.

No long paragraphs above the fold. If a newcomer can't rebuild the demo from the top screen alone, the README fails review.

## 3b. The app UX bar ("запустили и погнали")

- The shipped app opens ready to use: minimal visible settings, everything advanced hidden (hide in UI, do NOT delete code paths - keeps it testable and diff-small vs upstream).
- The FlyMy.AI section is front and center: enable toggle, API key field, agent id field **prefilled with our public agent**, plus a "Connect Notion" (or the demo's sink) button linking to app.flymy.ai/mcp-configs - so the path is: install -> paste key -> go.
- A user can paste THEIR OWN agent id right in the app to repoint it.

## 4. The self-test bar (hand over working things only)

Before anything reaches a human for testing:
- The cloud agent is self-tested END-TO-END on the frozen compilation: run it, verify the real side effect (the Notion row / message / file actually exists, body included), and pull the real billed price via `get_execution_price`.
- The app is built, packaged and launched at least once; every automatable path is exercised by us first. The human's job at the final stage is to CLICK THROUGH a working product, not to debug it.
- Regressions found during self-test get fixed and re-tested before handoff - never shipped with a "known issue" note unless the human explicitly accepts it.

## 5. Repo mechanics

- Hub (`build-with-flymyai`) = index + submodules; each demo = its own repo (clone one without pulling all).
- Per-demo layout: `README.md` (marketing + quick start), `CLAUDE.md` (for people adapting via Claude), `agent/`, `app/` or `client/`, `BUILD_LOG.md`, MIT `LICENSE`, `NOTICE.md` when forking.
- English-only in code and docs. Dash `-`, never em-dash. Secret-scan before every push.
- Releases carry the installable artifact (.dmg etc.); ad-hoc signed demo builds say so in the README.
