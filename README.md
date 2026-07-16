# Built with FlyMy.AI 🛠️

Real apps built with **Claude Code as the brain** and **[FlyMy.AI](https://flymy.ai) as the cloud runtime** - each one documented end-to-end: the code, the cloud-agent recipe, and an honest BUILD_LOG with timestamps and real billed costs (including every bug we hit on the way).

**The pitch: the feature you rent for $15/mo is a commodity you can own.** Each demo takes an incumbent's core feature, rebuilds it as your-keys/your-data on FlyMy.AI, and publishes the receipts.

Every demo lives in its own repo, so you clone only what you want to play with. This hub is the index (submodules point at the latest state of each demo). Building or contributing one? Read [PLAYBOOK.md](PLAYBOOK.md) - the standing rules for builds, marketing claims, and repo mechanics.

| Demo | What it does | Stack | Cost per use (measured) |
|---|---|---|---|
| [WhisperFly](https://github.com/FlyMyAI/whisperfly) 🎙️ | Hotkey dictation app for macOS: instant local ASR paste + a cloud agent that transcribes, cleans, tags and files every voice note into Notion | Tauri/Rust (Handy fork) + FlyMyAI agent (whisper + notion, o4-mini) | ~$0.08 / voice note |

## The pattern

Each demo follows the same recipe you can reuse:

1. **Research with Claude** - competitor teardown, feasibility, unit economics (multi-agent workflows).
2. **Cloud half on FlyMy.AI** - one agent, tools pinned, concrete ids baked into the prompt, then **frozen** into a fixed pipeline (cheap, fast, API-callable).
3. **Local half** - the thinnest possible client (CLI first, then a real app, often a fork of a good MIT open-source base).
4. **BUILD_LOG.md** - timestamps, real billed prices, dead ends included. That's the part most repos hide; we think it's the useful part.

## Clone one demo

```bash
git clone git@github.com:FlyMyAI/whisperfly.git
```

## Clone everything

```bash
git clone --recursive git@github.com:FlyMyAI/built-with-flymyai.git
```
