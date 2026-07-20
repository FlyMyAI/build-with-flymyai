# Master Implementation & Merge Plan: build-with-flymyai v2 🚀

This is the comprehensive blueprint for merging and redesigning the two repository demos (**WhisperFly** and **replifly**) along with the **Media Cases** page into a single unified showcase build (**build-with-flymyai**) powered by Vite and React.

---

## 🎨 Visual "Wow-Effect" & Repository Styling Toolkit

After running deep research on repository aesthetics, graphics, and interactive presentation tools, here is the curated toolkit of high-performance visual elements we will leverage:

### 1. Embedded HTML5 Videos with Autoplay & Loop
Instead of heavy static images or massive lagging GIFs, GitHub natively supports HTML `<video>` tags. We will use:
```html
<p align="center">
  <video src="https://storage.googleapis.com/open-inference-results/media/demo_720p.mp4" 
         autoplay loop muted playsinline width="100%" style="border-radius: 8px;">
  </video>
</p>
```
*   **Rules:** Clean 720p resolution, compressed under 2MB (CRF 30–34) to avoid buffering, loop enabled, and styled with rounded corners.

### 2. SVG `<foreignObject>` for Custom Rich HTML & CSS Card Rendering
To bypass GitHub's markdown sanitization and display gorgeous, custom-styled dark cinematic panels, we can wrap standard HTML/CSS inside an SVG file and reference it via an `<img>` tag:
```xml
<svg width="800" height="250" viewBox="0 0 800 250" fill="none" xmlns="http://www.w3.org/2000/svg">
  <foreignObject width="100%" height="100%">
    <div xmlns="http://www.w3.org/1999/xhtml" style="
      background: radial-gradient(100% 100% at 0% 0%, #161b22 0%, #0d1117 100%);
      border: 1px solid #30363d;
      border-radius: 12px;
      padding: 24px;
      font-family: system-ui, sans-serif;
      color: #c9d1d9;
    ">
      <h3 style="color: #58a6ff; margin: 0 0 8px 0;">🎙️ WhisperFly</h3>
      <p style="font-size: 14px; margin: 0 0 16px 0; color: #8b949e;">We killed Wispr Flow. $0.031 per note on our real bill.</p>
      <div style="display: flex; gap: 8px;">
        <span style="background: #238636; color: white; padding: 4px 8px; border-radius: 6px; font-size: 12px; font-weight: bold;">LIVE</span>
        <span style="background: #21262d; border: 1px solid #30363d; color: #c9d1d9; padding: 4px 8px; border-radius: 6px; font-size: 12px;">React + Tauri</span>
      </div>
    </div>
  </foreignObject>
</svg>
```
*   **Wow Effect:** This allows drop shadows, glowing linear-gradient borders, CSS custom animations (like pulsing lights, fade-ins), and perfect typographic hierarchy inside the README file.

### 3. Terminal Session Animators (SVG)
- **`svg-term-cli`**: Converts `asciinema` recordings into highly-responsive, vector-based animated SVGs that play command execution sequences flawlessly in the README.
- **`carbon.now.sh` / `silicon`**: Used to generate gorgeous static code/CLI output images framed in a macOS window container with customizable drop-shadows and dark themes.

### 4. Custom Shields.io Flat Badges
We will standardize all repository badges to the sleek, square aesthetic (`?style=flat-square`) combined with SVG logos (e.g., Notion, Sentry, Neon, Fly.io, Google Cloud) and high-contrast color codes to maintain developer branding.

---

## 🛠️ The Vite Unified Showcase Architecture

The Vite-based frontend at `build-with-flymyai` will act as a B2B Command Center for FlyMy.AI subscription-killers.

### Core Architecture
- **Single Page Application:** A dark-themed, cinematic showcase deck built with React + Vite + Tailwind.
- **Single Typography Font:** 3 sizes maximum (L1: 48-52px, L2: 28-32px, L3: 18-20px).
- **Downward Chronological Timelines:** Steps linked by `↓` using relative durations.
- **No S3 Clutter / No Bloat:** Assets pulled dynamically from GCP storage.

### UI Sections & Navigation
1.  **Header Hero Section:**
    - High-impact pitch: "We build open-source SaaS killers powered by FlyMyAI cloud agents."
    - Dynamic matrices displaying real savings (WhisperFly, replifly, Media Cases).
2.  **Horizontal Filtering System:**
    - Tabs: `[ All Demos ]` `[ WhisperFly ]` `[ replifly ]` `[ Media Cases ]`
3.  **Unified Showcase Cards:**
    - Immersive medium-shot videos with subtle film-grain overlay textures.
    - Click-to-Modal interactions for details.
4.  **Premium Minimalist Modals:**
    - **Visual Showcase:** Auto-playing, looping video preview (720p, under 2MB).
    - **Outcome & Economics:** Direct comparison charts between SaaS models and FlyMyAI runs.
    - **The Prompt & Recipe:** Complete prompt copy with a "Copy Prompt" button.
    - **Launch CTA:** Highlighted button to copy/clone the public FlyMyAI agent straight into the user's account.

---

## 📋 Phase-by-Phase Roadmap

### 📦 Phase 0: Setup & Context Validation (Complete)
- [x] Switched to fresh branch `nrx83_v2` in the `build-with-flymyai` repository.
- [x] Connected FlyMyAI MCP server to Hermes using Sasha's API key.
- [x] Verified MCP discovery successfully (54 tools loaded, connection healthy).
- [x] Completed deep research on visual elements and README styling best practices.

### 📂 Phase 1: Directory Restructuring
Organize the repository to keep docs and assets neatly organized into a mono-docs structure without duplicating bulky application binaries:
```text
build-with-flymyai/
├── README.md                     # Main Hub & Interactive Portal Index
├── PLAYBOOK.md                   # Canonical Rules for B2B Demos
├── AGENTS.md                     # LLM Instruction Set for App-Building
├── demos/
│   ├── whisperfly/
│   │   ├── README.md             # Summary & Links
│   │   ├── BUILD_PROMPT.md       # Exact reproducing prompt
│   │   ├── BUILD_LOG.md          # Real cost receipts & steps
│   │   └── agent/prompt.md       # Agent instructions
│   ├── replifly/
│   │   ├── README.md             # Standardized safe positioning README
│   │   ├── BUILD_PROMPT.md       # Deployment agent prompt
│   │   ├── BUILD_LOG.md          # Real receipts
│   │   └── skill/                # Real "ship-to-production" skill
│   └── media-cases/
│       ├── README.md             # Media showcase workflow instructions
│       ├── data/cases.json       # Clean metadata file
│       └── scripts/              # Media extraction/upload scripts
└── src/                          # Vite + React unified landing page source
```

### 📝 Phase 2: Content Standardization & Copy Polish
- **replifly:** Soften topline claim from "We killed Replit" to *"Rebuilt the deploy-to-prod half of Replit on open infra with one agent"*. Keep the economics focused on runtime infrastructure savings ($2-5/mo vs $25-45/mo).
- **Media Cases:** Focus on transparent, black-box-free cinematic workflows using GPT Image 2.0 & Seedance 2.0, showcasing pay-per-run pricing vs monthly creative suites.
- **WhisperFly:** Preserve the $0.031 per-note receipt, highlighting local dictation + FlyMyAI Notion indexing.

### 💻 Phase 3: Single-Build Vite Implementation
- Initiate a clean Vite-Tailwind-React scaffold under `src/` (or merge landing code).
- Design a high-performance, responsive matrix-grid dashboard using a dark command-center layout.
- Build a central JSON file (`data/matrix.json`) representing all cases and metrics, enabling seamless addition of new demos without touching the UI code.
- Implement the minimal modal with 3 font sizes, looping videos, and direct public agent launch actions.

### 🛡️ Phase 4: Security & Validation Gate
- Run automated scans for sensitive keys (`sk-`, `AIza`, `fly-`, `Bearer `).
- Audit all MinIO paths and replace local development URLs with production GCP URLs.
- Test E2E local build and execute `npm run build` locally before preparing deployment.
