# Build with FlyMy.AI 🛠️

<p align="center">
  <strong>Open-source SaaS killers powered by FlyMy.AI cloud agents.</strong><br />
  We rebuild expensive subscription workflows into transparent, flat-rate systems you own.
</p>

---

## ⚡ Quick Matrix

| Project | Kills / Rebuilds | Their Price | Our Price | Measured Savings | Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| [🎙️ WhisperFly](demos/whisperfly/README.md) | **Wispr Flow** (Voice dictation) | $12–15/mo | **$0** local / **$0.031** cloud | **5–16x cheaper** | **Live** |
| [🚀 replifly](demos/replifly/README.md) | **Replit Deploy** (Deploy-to-prod) | $25–45/mo | **Free-tier** hosting (Neon/Fly) | **4–10x cheaper** runtime | **Live** |
| [🎬 Media Cases](demos/media-cases/README.md) | **Higgsfield-style** video workflows | $15–129/mo | **Pay-per-run** (direct models) | **Raw model cost, no lock-in** | **Live** |

---

## 🧠 How it works

```mermaid
flowchart LR
    U(["🧑‍💻 you<br/><b>one prompt</b>"]) --> C(["🧠 Claude Code / Codex"])
    C -->|one-line MCP| CLOUD["☁️ FlyMy.AI Agentic Cloud"]
    CLOUD --> OUT(["📦 fully-deployed product on your accounts"])
    
    classDef you fill:#0f766e,stroke:#0f766e,color:#fff;
    classDef agent fill:#4c1d95,stroke:#4c1d95,color:#fff;
    classDef cloud fill:#1d4ed8,stroke:#1d4ed8,color:#fff;
    classDef out fill:#166534,stroke:#166534,color:#fff;
    class U you; class C agent; class CLOUD cloud; class OUT out;
```

---

## 📦 The Showcases

### 🎙️ WhisperFly
We killed Wispr Flow. Local-first dictation on your machine combined with a frozen FlyMy.AI cloud agent that cleans up transcripts, adds custom tags, and files everything into your Notion workspace automatically.
*   **Cost:** **$0.031 per note** vs $15/mo.
*   **Stack:** Rust + Tauri (native macOS shell) + Notion integration.
*   **Explore:** [README](demos/whisperfly/README.md) · [Build Log & Receipts](demos/whisperfly/BUILD_LOG.md) · [Prompt](demos/whisperfly/BUILD_PROMPT.md)

### 🚀 replifly
Bring the Replit deploy magic to your own cloud stack. Feed replifly your codebase, and Claude + FlyMy.AI will auto-provision a Fly.io VM, wire a Neon Postgres database, integrate Sentry monitoring, and launch an on-call agent that calls your phone if production goes down.
*   **Cost:** **$2-5/mo** on free tiers vs $25-45/mo platform reserved hosting.
*   **Stack:** Node.js/Python + Fly.io + Sentry + Neon + Twilio.
*   **Explore:** [README](demos/replifly/README.md) · [Build Log & Receipts](demos/replifly/BUILD_LOG.md) · [Prompt](demos/replifly/BUILD_PROMPT.md)

### 🎬 Media Cases
Cinematic AI video workflows without the black box. Run state-of-the-art visual chains (like GPT Image 2.0 → Seedance 2.0) directly through raw model routing. No monthly subscription, no proprietary platform lock-in, and 100% prompt transparency.
*   **Cost:** **Direct pay-per-run model pricing** vs $15-129/mo subscriptions.
*   **Explore:** [README](demos/media-cases/README.md) · [Sample Gallery](demos/media-cases/README.md#outstanding-media-cases-sample-gallery)

---

## 🛠️ Build your own in 1 minute

1. **Connect FlyMy.AI cloud to your local coding agent:**
   ```bash
   claude mcp add --transport http flymyai https://mcp-agents.flymy.ai/mcp
   ```
2. **Tell your agent what subscription to rebuild:**
   *(Use the prompt structures in [BUILD_PROMPT.md](demos/whisperfly/BUILD_PROMPT.md) and the rules in [PLAYBOOK.md](PLAYBOOK.md))*

---

## 📖 Playbook Rules (PLAYBOOK.md summarized)

*   **No raw data in Git:** All media assets must be compressed (720p H.264 videos under 2.0 MB) and hosted via FlyMy.AI CDN.
*   **Only real bills:** Every cost claim must be backed by a real, unedited receipt in `BUILD_LOG.md`.
*   **Sell ownership, not parity:** Polish is the incumbent's advantage. Our advantage is: your keys, your database, your routing, complete portability.
*   **Rebrand forks:** Any forked open-source base must be fully rebranded under the demo's name. Downstream credit goes to `NOTICE.md`.

---

> **Disclaimer:** Not affiliated with, endorsed by, or sponsored by Replit, Inc. or Wispr. "Replit" and "Wispr Flow" are trademarks of their respective owners, used here only to describe the product categories.
