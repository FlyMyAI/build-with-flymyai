# Build with FlyMyAI

<p align="center">
  <strong>Open-source apps + one FlyMyAI cloud agent.</strong><br />
  Rebuild expensive AI SaaS workflows as transparent, remixable systems you own.
</p>

<p align="center">
  <a href="https://flymy.ai"><img alt="FlyMyAI" src="https://img.shields.io/badge/FlyMyAI-agentic_cloud-0A66FF?style=for-the-badge" /></a>
  <a href="https://mcp-agents.flymy.ai/mcp"><img alt="MCP" src="https://img.shields.io/badge/MCP-connectable-111111?style=for-the-badge" /></a>
  <a href="PLAYBOOK.md"><img alt="Playbook" src="https://img.shields.io/badge/Build_Log-required-16A34A?style=for-the-badge" /></a>
</p>

> The pattern is simple: **Claude builds**, **FlyMyAI runs the cloud workflow**, and the repo ships the prompts, receipts, and code so anyone can rebuild it.

```mermaid
flowchart LR
    U(["you<br/><b>one product idea</b>"]) --> C
    C(["Claude / Codex<br/>coding agent"]) --> MCP
    MCP(["FlyMyAI MCP<br/>tools + models + agents"]) --> A
    A(["one frozen<br/>cloud agent"]) --> P
    P(["open-source product<br/>client, docs, receipts"])

    classDef user fill:#0f766e,stroke:#0f766e,color:#fff;
    classDef agent fill:#4c1d95,stroke:#4c1d95,color:#fff;
    classDef cloud fill:#1d4ed8,stroke:#1d4ed8,color:#fff;
    classDef out fill:#166534,stroke:#166534,color:#fff;
    class U user; class C agent; class MCP,A cloud; class P out;
```

---

## The three proofs

<table>
  <tr>
    <td width="33%" valign="top">
      <h3>🎬 Media Cases</h3>
      <p><strong>Cinematic AI video workflows without the black box.</strong></p>
      <p>Higgsfield-style media cases built as inspectable FlyMyAI runs: prompt, model chain, image, video, and source chat are visible.</p>
      <p><strong>Why it matters:</strong> direct model runs, FlyMyAI model discounts, pay-per-run economics, no monthly creative-suite lock-in for the workflow itself.</p>
      <p><a href="https://app.flymy.ai/media/"><strong>Open the live gallery →</strong></a></p>
    </td>
    <td width="33%" valign="top">
      <h3>🎙️ WhisperFly</h3>
      <p><strong>Wispr Flow-style voice notes you can own.</strong></p>
      <p>Local-first dictation client + one FlyMyAI cloud agent for transcription cleanup, keywords, and Notion filing.</p>
      <p><strong>Why it matters:</strong> no telemetry in the app, no third-party APIs in the client, real measured cloud filing cost in the build log.</p>
      <p><a href="https://github.com/FlyMyAI/whisperfly"><strong>View the app →</strong></a></p>
    </td>
    <td width="33%" valign="top">
      <h3>🚀 replifly</h3>
      <p><strong>Build your own Replit-style deploy workflow.</strong></p>
      <p>Not a full Replit clone. A deploy-to-prod agent that provisions Fly.io, Neon, Sentry, browser-checks the app, and wires on-call alerts.</p>
      <p><strong>Why it matters:</strong> the app runs on your accounts, your stack, your cost model, and can leave with you.</p>
      <p><a href="https://github.com/FlyMyAI/replifly"><strong>View the deploy demo →</strong></a></p>
    </td>
  </tr>
</table>

---

## What this repo is

`build-with-flymyai` is the hub for public FlyMyAI demos.

It is **not** a gallery of toy prompts. Each demo is expected to ship:

- a clear incumbent / workflow being challenged;
- a reproducible `BUILD_PROMPT.md`;
- a timestamped `BUILD_LOG.md` with real failures and real bills;
- one FlyMyAI cloud agent or workflow recipe;
- a thin open-source client or public showcase;
- honest claims only - no parity claims without tests.

```text
build-with-flymyai/
├── README.md                       # this hub
├── PLAYBOOK.md                     # rules for every demo
├── AGENTS.md / CLAUDE.md           # instructions for coding agents
├── skills/build-flymyai-app/       # reusable Claude Code skill
├── whisperfly/                     # submodule: voice workflow demo
└── replifly/                       # submodule: deploy workflow demo
```

---

## Demo matrix

| Demo | Category | What it rebuilds | Best public claim | Avoid saying |
|---|---|---|---|---|
| [Media Cases](https://app.flymy.ai/media/) | AI video workflow | Higgsfield-style cinematic prompt pipelines | Transparent, pay-per-run media workflows with model-chain receipts | “full Higgsfield replacement” or “better quality” |
| [WhisperFly](https://github.com/FlyMyAI/whisperfly) | Voice notes | Wispr Flow-style dictation + filing | Local-first voice notes with optional cloud filing | “more accurate” without side-by-side STT tests |
| [replifly](https://github.com/FlyMyAI/replifly) | Deployment | Replit-style deploy-to-prod path | Bring Replit-like deploy magic to your own infra | “we killed Replit” as a full-platform claim |

---

## Build your own FlyMyAI demo

1. **Connect FlyMyAI MCP** to your coding agent:

   ```bash
   claude mcp add --transport http flymyai https://mcp-agents.flymy.ai/mcp
   ```

2. **Pick a workflow with an expensive black box.**
   Voice notes, AI video production, app deployment, reporting, lead enrichment, support triage, internal ops.

3. **Ask your agent to follow the playbook.**
   Start with [`PLAYBOOK.md`](PLAYBOOK.md) and the reusable skill in [`skills/build-flymyai-app/`](skills/build-flymyai-app/SKILL.md).

4. **Ship receipts.**
   Every serious demo needs a build log, prompts, real cost numbers, and an honest “what this is not” section.

---

## Why FlyMyAI is the backend

Most AI tools bundle three things together:

1. a UI;
2. models and integrations;
3. a subscription/credit system.

FlyMyAI lets you split those apart:

- your repo owns the product surface;
- your FlyMyAI agent owns the cloud workflow;
- your model/tool usage is inspectable and measurable;
- your users can copy, remix, and run the same workflow on their own account.

That is why the demos here focus on **ownership**, **transparent prompts**, and **real bills** - not vague “AI magic”.

---

## Positioning rules

We keep the copy sharp, but not fake.

- Use “killed” only where the demo actually replaces the core user-visible workflow.
- Use “Replit-style” for replifly, not “Replit replacement”.
- Use “Higgsfield-style workflows” for Media Cases, not “Higgsfield clone”.
- Say “cheaper” only when the unit economics are scoped: model, duration, resolution, retry count, and our actual bill.
- Never claim accuracy, compliance, or feature parity without tests.

See [`PLAYBOOK.md`](PLAYBOOK.md) for the full rules.

---

## Clone

```bash
git clone --recursive git@github.com:FlyMyAI/build-with-flymyai.git
cd build-with-flymyai
```

Or clone a single demo:

```bash
git clone git@github.com:FlyMyAI/whisperfly.git
git clone git@github.com:FlyMyAI/replifly.git
```

---

## Status

- ✅ WhisperFly - working app, public repo, build log, measured costs.
- ✅ replifly - working deploy proof, public repo, build log, infra flow proven.
- ✅ Media Cases - live gallery, 32 image cases, 19 video cases, prompt transparency.
- 🧭 Next - fold Media Cases docs/scripts into this hub without committing media binaries.
