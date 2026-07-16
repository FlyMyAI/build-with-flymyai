# Build with FlyMy.AI 🛠️

**We kill $15/mo subscriptions.** Each demo here is a real app built from **one prompt** - Claude as the builder, **[FlyMy.AI](https://flymy.ai) agentic cloud** as the backend - with the receipts published: code, agent recipe, and a BUILD_LOG with our real bill.

**First kill: [Wispr Flow](https://github.com/FlyMyAI/whisperfly)** - their price: **$12-15/mo forever**. Ours: **dictation $0** (local, offline) + **$0.031 per voice note filed to Notion** (a feature they don't have). 3-18x cheaper, core feature free.

| Demo | Kills | Their price | Our price |
|---|---|---|---|
| [WhisperFly](https://github.com/FlyMyAI/whisperfly) 🎙️ | Wispr Flow (hotkey dictation) | $12-15/mo | $0.031/note all-in (STT+cleanup+tags+Notion) |

## Build your own, from one prompt

1. Connect FlyMy.AI to your coding agent (Claude Code / claude.ai / Codex / Antigravity) - one line:
   ```bash
   claude mcp add --transport http flymyai https://mcp-agents.flymy.ai/mcp
   ```
2. Grab [AGENTS.md](AGENTS.md) into your project (Claude also reads it via CLAUDE.md) - it teaches your agent the whole pattern: research -> one frozen FlyMy.AI agent -> thin open-source client -> honest BUILD_LOG.
3. Say what to kill. Or start from a demo's `BUILD_PROMPT.md` and adapt.

Skills for Claude Code live in [`skills/`](skills/) - drop them into `~/.claude/skills/` and your Claude knows how to build and bill-check FlyMy.AI agents.

## Rules of the series

[PLAYBOOK.md](PLAYBOOK.md): the build pattern, the killer-pitch README format, honest-claims discipline (only numbers from our own bill), the app UX bar ("launch and go"), and the self-test bar (a human only ever receives a working, click-through-ready app).

## Clone

```bash
git clone git@github.com:FlyMyAI/whisperfly.git                     # one demo
git clone --recursive git@github.com:FlyMyAI/build-with-flymyai.git # everything
```
