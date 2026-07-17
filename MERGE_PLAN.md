# Merge Plan: build-with-flymyai as the unified showcase hub

## Current state

Local workspace:

```text
/home/nrx83/AI/merge/
├── build-with-flymyai/   # main hub repo, branch nrx83
├── whisperfly/           # standalone demo repo
└── replifly/             # standalone demo repo
```

Repos cloned via SSH:

- `git@github.com:FlyMyAI/build-with-flymyai.git`
- `git@github.com:FlyMyAI/whisperfly.git`
- `git@github.com:FlyMyAI/replifly.git`

Main repo branch for work:

```bash
cd /home/nrx83/AI/merge/build-with-flymyai
git branch --show-current   # nrx83
```

## What each repo is today

### 1. build-with-flymyai

Role: the hub / umbrella repo.

Current positioning:

> We kill $15/mo subscriptions. Each demo is built from one prompt - Claude as builder, FlyMy.AI as backend.

Current hub content:

- `README.md` - short hub page with comparison table.
- `PLAYBOOK.md` - canonical rules for future demos.
- `AGENTS.md` / `CLAUDE.md` - instructions for coding agents building FlyMy.AI-backed products.
- `skills/build-flymyai-app/SKILL.md` - reusable Claude Code skill for building FlyMy.AI subscription-killer apps.
- `.gitmodules` currently points to:
  - `whisperfly`
  - `replifly`

### 2. WhisperFly

Role: app demo / subscription killer.

Kills: Wispr Flow / premium voice dictation workflows.

Strong assets:

- Mature README with top-screen pitch.
- Real `BUILD_LOG.md` with receipts, costs, failures, pricing iteration.
- `BUILD_PROMPT.md` that rebuilds the app.
- Real macOS/Tauri app forked from Handy.
- Agent prompt in `agent/prompt.md`.

Message:

- Local-first dictation.
- FlyMy.AI cloud agent handles transcription cleanup, tags, and Notion filing.
- Demonstrates: cloud agent as product engine + thin native client.

### 3. replifly

Role: infra/deployment demo / subscription killer.

Kills: Replit deploy-to-prod workflow.

Strong assets:

- Strong README with economics table.
- `BUILD_LOG.md` with real MCP calls: Neon, Fly.io, Sentry, Browser Use, Twilio.
- `BUILD_PROMPT.md` for reproducing the deployment agent.
- `skill/ship-to-production/README.md` exists but is only a placeholder.

Message:

- Deploy from one prompt.
- Runs on your Fly.io / Neon / Sentry accounts.
- No Replit lock-in.
- FlyMy.AI cloud provisions, verifies, monitors, and calls you if prod is down.

### 4. Media Cases page

Live page:

- `https://flymy.ai/media/` / `https://app.flymy.ai/media/` depending deployment host.

Role: visual proof gallery, not a code app.

Kills / attacks: Higgsfield-style cinematic AI video subscription/workflow.

Current page demonstrates:

- 32 image cases.
- 19 video cases.
- GPT Image 2.0 + Seedance 2.0 + other model workflows.
- Prompt transparency: click case -> see prompt and link back to the FlyMyAI agent chat.
- Asset delivery via FlyMyAI / GCS URLs, not Git blobs.

Important current lessons:

- Never commit heavy images/videos into the frontend repo.
- Store media on S3/GCS as `AgentFile`/public URLs or external GCS path.
- `public/media/index.html` should contain links only.
- Video target: 720p, visually acceptable, preferably under ~2MB per clip.

## Desired end state

Turn `build-with-flymyai` into the single polished public portfolio repo:

```text
build-with-flymyai/
├── README.md                     # homepage / demo index / main pitch
├── PLAYBOOK.md                   # canonical build + marketing rules
├── AGENTS.md                     # coding-agent instructions
├── CLAUDE.md                     # symlink-ish / shorter Claude entrypoint
├── demos/
│   ├── whisperfly/
│   │   ├── README.md             # summarized imported README or submodule link
│   │   ├── BUILD_PROMPT.md
│   │   ├── BUILD_LOG.md
│   │   ├── agent/prompt.md
│   │   └── app/ or pointer       # optional: submodule or copied thin code
│   ├── replifly/
│   │   ├── README.md
│   │   ├── BUILD_PROMPT.md
│   │   ├── BUILD_LOG.md
│   │   └── skill/ship-to-production/SKILL.md
│   └── media-cases/
│       ├── README.md
│       ├── BUILD_PROMPT.md
│       ├── BUILD_LOG.md
│       ├── data/media-cases.json
│       ├── scripts/              # upload/compress/extract scripts, no secrets
│       └── public page URL notes
├── skills/
│   ├── build-flymyai-app/
│   ├── ship-to-production/
│   └── build-media-cases-showcase/
└── docs/
    ├── media-cases.md
    ├── economics.md
    └── comparing-subscription-killers.md
```

## Recommended integration strategy

### Option A - Submodules kept, hub polished

Keep `whisperfly` and `replifly` as submodules. Add `media-cases` as a docs/demo folder, not a repo.

Pros:

- Clean Git history.
- No duplication of large app code.
- Each app remains individually installable.
- Hub stays small and easy to maintain.

Cons:

- GitHub UX for submodules is not perfect for casual readers.
- Cross-demo search is less smooth.

This is currently the best low-risk option.

### Option B - Copy docs only, keep app code external

Copy only these files from child repos into `demos/`:

- `README.md`
- `BUILD_PROMPT.md`
- `BUILD_LOG.md`
- `agent/prompt.md`
- skill docs

Link out to full repos for app code.

Pros:

- Great browsing experience in one repo.
- Hub tells the whole story without pulling giant app code.
- No submodule friction.

Cons:

- Some duplication.
- Need to remember to sync docs after child repo changes.

This may be best for public marketing.

### Option C - True monorepo

Move all code from `whisperfly` and `replifly` into `build-with-flymyai`.

Pros:

- One repo has everything.

Cons:

- Most expensive and noisy.
- Tauri app code + deploy docs + media gallery all mixed together.
- Risks losing clean standalone repo identities.

Not recommended unless we explicitly want to retire child repos.

## Proposed public README structure

Replace the current hub README with a stronger first-screen pitch:

```md
# Build with FlyMy.AI

**We kill expensive AI subscriptions by turning them into open-source apps + one FlyMy.AI cloud agent.**

One prompt gives you:
- a thin open-source client,
- a frozen FlyMy.AI agent backend,
- real bills and build logs,
- your accounts, your keys, your infra.

| Demo | Kills | What it proves | Cost story | Build |
|---|---|---|---|---|
| WhisperFly | Wispr Flow | voice note -> cleanup -> Notion | $0 local dictation + measured cloud filing | link |
| replifly | Replit deploys | deploy app to Fly.io + Neon + Sentry | 4-10x cheaper runtime | link |
| Media Cases | Higgsfield-style video workflows | prompts + multi-model media cases | no subscription, direct model runs | link |
```

Then below:

1. How it works: 1 diagram.
2. Build your own: 3 steps.
3. The playbook: link to PLAYBOOK.
4. Demo cards.
5. Honest claims / receipts.

## Revised positioning after research

### Replit / replifly: soften from "we killed Replit" to "build your own Replit-like deploy workflow"

Current Replit facts from sources checked:

- Replit pricing page: Starter free, Core listed as $25/mo or $20/mo billed annually with $25 monthly credits, Pro listed as $100/mo or $95/mo billed annually with $100 monthly credits, Enterprise custom.
- Replit pricing page also states Replit Agent uses LLMs and credits, and users can run out of credits / use effort-based pay-as-you-go.
- Replit effort-based pricing blog: simple tasks may cost less than $0.25; complex tasks may cost more than $0.25; cost reflects agent work/time/compute; higher power / extended thinking controls increase capability and spend.
- Third-party pricing writeups repeatedly frame Replit as convenient all-in-one IDE + agent + deployment, but with cost predictability concerns for heavy Agent usage.

Implication: do **not** publicly lead with "We killed Replit" unless we can prove parity across IDE, collaboration, agent, deployments, hosting, database, auth, and team workflows. It sounds like overclaim.

Better public angle:

> Build your own Replit-style deploy-to-prod agent.

or

> We rebuilt the deployment half of Replit with open infra and one FlyMy.AI agent.

Safe positioning:

- Replit is excellent as an all-in-one cloud IDE and quick launch environment.
- replifly is not trying to clone Replit's full IDE, collaboration UX, or marketplace.
- replifly demonstrates the part people can own: **deploy an existing repo to production infrastructure** (Fly.io + Neon + Sentry + browser-check + on-call agent) from a prompt.
- The wedge is ownership and portability, not "better Replit".
- Phrase as: "Replit-like deploy workflow on your accounts" or "bring the Replit deploy magic to your own stack".

Safer README copy:

> replifly is a Replit-style deploy agent for repos you already own: Claude reads your code, FlyMy.AI provisions Fly.io + Neon + Sentry, verifies the app in a browser, and wires an on-call agent. It is not a full Replit IDE. It is the deploy-to-prod workflow, rebuilt on your accounts.

Avoid:

- "We killed Replit" as a top-line claim.
- "cheaper than Replit" without separating build-agent cost from run-time infra cost.
- "Replit replacement" as a blanket claim.

Allowed cost claim if we keep the real receipts:

- Running a small app on your own Fly.io + Neon + Sentry stack can be cheaper and more portable than renting a bundled platform deployment.
- Replit Agent cost can vary under effort-based pricing; replifly's coding agent cost is whatever model/subscription the user chooses plus FlyMy.AI tool runs.

### Higgsfield / Media Cases: we can claim cheaper, but keep it scoped

Research notes from Higgsfield materials:

- Higgsfield positions itself as a creative AI video suite, not just a model router.
- It emphasizes camera control, character consistency, Marketing Studio, and multi-model access.
- Their 2026 platform comparison page lists Higgsfield at $15/mo Starter to $129/mo Ultra.
- Their Seedance comparison table says an Ultra plan can imply about ~$1.9 per 10s 720p clip depending on credits and settings.

FlyMyAI wedge:

- Different payment system: pay-per-run / direct model calls through FlyMyAI, not a monthly creative-suite credit subscription.
- We have discounted model economics / internal model pricing, so certain workflows can be cheaper per generated asset.
- Media Cases are transparent agent recipes: prompts, model chain, reference image, output video, and the source chat are inspectable.

Good claim:

> Higgsfield-style cinematic AI video workflows, but transparent and pay-per-run: every prompt, model chain, and result is visible, remixable, and runnable from your own FlyMyAI account. For many Seedance/GPT Image workflows, FlyMyAI's model pricing and discounts make the per-asset cost lower than subscription-credit platforms.

Safe claims:

- Cheaper per run for our measured FlyMyAI model prices and selected workflows.
- No monthly subscription required for the showcase pattern.
- Transparent prompts and reproducible chat links.
- Multi-model workflows (e.g. GPT Image 2.0 -> Seedance 2.0).
- Assets hosted via FlyMyAI/GCS, not in Git.

Avoid:

- "We killed Higgsfield" as a literal product-replacement claim unless we build and compare their full camera-control / character consistency / Marketing Studio stack.
- "better quality than Higgsfield" without side-by-side tests.
- "same features" without a mapped parity table.

Recommended Media Cases headline:

> Cinematic AI video workflows without the black box.

Recommended subheadline:

> Higgsfield-style media cases built as transparent FlyMyAI runs: prompts, model chain, assets, and source chats included. Pay per run, remix the workflow, keep the receipts.

## Media Cases repo material to add

Create:

```text
demos/media-cases/
├── README.md
├── BUILD_PROMPT.md
├── BUILD_LOG.md
├── data/media-cases.json
└── scripts/
    ├── extract_chats.py
    ├── compress_media.py
    ├── upload_via_flymy_api.py
    └── build_static_page.py
```

Do NOT include heavy videos/images in Git.

`README.md` should include:

- "We killed black-box AI video workflows."
- Link to live page.
- Table of 5-8 strongest cases.
- How to add a new chat:
  1. paste public chat link,
  2. extract chat metadata,
  3. download/compress generated assets,
  4. upload to FlyMyAI API,
  5. rebuild `media/index.html`,
  6. PR only the HTML/JSON script changes.

## Concrete next implementation tasks

### Phase 1 - Preserve current hub behavior

1. Keep `build-with-flymyai` as main repo.
2. Keep existing submodules for `whisperfly` and `replifly` for now.
3. Add a `demos/media-cases/` docs folder.
4. Do not move app code yet.
5. Do not commit binary media assets.

### Phase 2 - Improve hub README

Rewrite `README.md` to feature three cards:

- WhisperFly - voice workflow killer.
- replifly - deployment workflow killer.
- Media Cases - black-box AI video workflow killer.

Keep table but make it visual and concise.

### Phase 3 - Import docs from child repos

Copy or summarize into the hub:

```text
demos/whisperfly/README.md
demos/whisperfly/BUILD_PROMPT.md
demos/whisperfly/BUILD_LOG.md
demos/whisperfly/agent/prompt.md

demos/replifly/README.md
demos/replifly/BUILD_PROMPT.md
demos/replifly/BUILD_LOG.md
demos/replifly/skill/ship-to-production/SKILL.md
```

Question for owner: full copy or summary + links?

### Phase 4 - Turn replifly skill placeholder into real skill

`replifly/skill/ship-to-production/README.md` is currently a placeholder.

Create proper `SKILL.md` based on `replifly/BUILD_LOG.md`:

- detect stack,
- provision Neon,
- deploy Fly.io,
- add Sentry,
- browser-check,
- set up Twilio call agent,
- log price.

### Phase 5 - Media Cases automation doc

Move our working local procedures into `demos/media-cases/scripts/` and docs:

- upload via `POST /api/v1/agents/agent-file-chat-upload/` with `X-API-KEY`.
- use `external_id=uuid4`.
- never use local MinIO URLs (`127.0.0.1:9010`) in committed HTML.
- verify every URL with `curl -I` before PR.
- videos: 720p, target under 2 MB when possible, keep duration.

### Phase 6 - Validate and polish

Before push:

```bash
git status
grep -R "127.0.0.1\|localhost" demos README.md PLAYBOOK.md AGENTS.md
# no secrets:
grep -R "Bearer \|X-API-KEY\|sk-\|AIza\|fly-" .
```

## Open decisions before implementation

1. Should child repos remain separate and be referenced as submodules, or should docs be copied into `demos/`?
2. Should the media page live only on `app.flymy.ai/media/`, or should `flymy.ai/media/` also point to it?
3. Should the hub repo include the static `media/index.html`, or only document the page and link to deployed app?
4. Do we want `MediaFly` as a formal third demo name, or keep it as `Media Cases`?
5. Are we allowed to say "kills Higgsfield" in public copy, or should we use softer language: "Higgsfield-style cinematic AI video workflows"?

## Suggested first PR scope

Small, safe first PR on branch `nrx83`:

- Add `MERGE_PLAN.md`.
- Add `demos/media-cases/README.md` draft.
- Rewrite top-level `README.md` to include Media Cases as the third demo.
- Do not move submodules yet.
- Do not copy app source yet.
- Do not commit media binaries.

This lets us review positioning before making structural moves.
