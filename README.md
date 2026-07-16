# Build with FlyMy.AI 🛠️

**We kill $15/mo subscriptions.** Each demo here is a real app built from **one prompt** - Claude as the builder, **[FlyMy.AI](https://flymy.ai) agentic cloud** as the backend - with the receipts published: code, agent recipe, and a BUILD_LOG with our real bill.

```mermaid
flowchart LR
    U(["🧑‍💻 you<br/><b>one prompt</b>"]) --> C
    subgraph BRAIN["🧠 Claude + FlyMy.AI MCP"]
        C["your coding agent"]
    end
    C -->|one line, one MCP| CLOUD
    subgraph CLOUD["☁️ FlyMy.AI agentic cloud"]
        direction TB
        M["🎨 models · 🤖 agents · 🔌 100+ tools"]
        A["agents that provision,<br/>run and watch it 24/7"]
    end
    CLOUD --> OUT(["📦 a real product<br/>on <b>your</b> accounts, billed to you"])

    classDef you fill:#0b7285,stroke:#0b7285,color:#fff;
    classDef brain fill:#5f3dc4,stroke:#5f3dc4,color:#fff;
    classDef cloud fill:#1864ab,stroke:#1864ab,color:#fff;
    classDef out fill:#2b8a3e,stroke:#2b8a3e,color:#fff;
    class U you; class C brain; class M,A cloud; class OUT out;
```

| Demo | Kills | Their price | Our price | Savings |
|---|---|---|---|---|
| [WhisperFly](https://github.com/FlyMyAI/whisperfly) 🎙️ | Wispr Flow (hotkey dictation) | $12-15/mo | dictation **$0** + $0.031/note to Notion | **5-16x cheaper** (core feature free) |
| [replifly](https://github.com/FlyMyAI/replifly) 🚀 | Replit (deploy-to-prod) | $25-45/mo + metered Agent ($30-50+/app) | ~$2-5/mo on your own Fly+Neon+Sentry | **4-10x cheaper to run** + flat-rate coding |

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
