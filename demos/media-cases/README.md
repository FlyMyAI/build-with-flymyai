# Cinematic AI Video Workflows without the Black Box 🎬

**Premium media cases built as transparent FlyMy.AI runs: prompts, model chain, assets, and source chats included. Pay per run, remix the workflow, keep the receipts.**

We build open-source, subscription-free creative pipelines powered by the **FlyMy.AI cloud**.

---

## ⚡ Our Generative Model Suite

These are the exact state-of-the-art visual models configured on the FlyMy.AI agent platform:

### 🖼️ Image Models
*   **GPT Image 2.0** — Strongest prompt adherence, best for accurate text & logo composition.
*   **Nano Banana Pro** — Higher-tier Nano Banana: strongest text rendering & complex scenes.
*   **Nano Banana 2** — Fast, high-quality image generation & editing with great in-image text.
*   **Seedream 4.5** — Photoreal portraits & legible in-image text. Generate and edit.
*   **Seedream 5.0 Lite** — Newer, lighter & faster Seedream. Generate and edit.
*   **Imagen 4 Fast** — Google image quality, fast — clean photoreal & illustration.
*   **FLUX Kontext** — Instruction-driven in-context image editing (Pro & Max tiers).
*   **GPT Image 1.5** — Cost-sensitive OpenAI image generation (superseded by 2.0).

### 🎬 Video Models
*   **Seedance 2.0** — Cinematic motion. Text/Image/Reference to video — auto by your input.
*   **Veo 3.1** — Google Veo — best realism & motion fidelity. Standard or Fast.
*   **MiniMax Hailuo 02** — Lively, natural motion. Text & image to video.

### 🎵 Audio Models
*   **MiniMax Music** — Original music & songs from a text prompt.

---

## 💸 The Economics

| Creative Component | Subscription Platforms (e.g. Higgsfield) | FlyMy.AI (Pay-per-Run) |
|---|---|---|
| Monthly Subscription | **$15–$129/mo** | **$0** (Flat free infrastructure) |
| Billing Unit | Locked credit packages | Raw, direct-to-model pay-per-run |
| Workflow Visibility | Black-box sliders | Full prompt transparency & chat replays |
| Portability | Proprietary platform lock-in | Complete API & model chain ownership |

---

## 📋 Outstanding Media Cases (Real Receipts)

Here are three real, unedited case runs executed on the FlyMy.AI agent network:

### Case 1: Y2K Cyber-Pop Editorial Image Edit (Face Preservation)
*   **Original Chat:** [💬 app.flymy.ai/agents/chat/iwk-hbbk-sfr](https://app.flymy.ai/agents/chat/iwk-hbbk-sfr)
*   **Primary Model:** `flymyai/gpt-image-2-0_edit` (GPT Image 2.0 Edit)
*   **The Flow:** The goal was to take a reference portrait of a girl and edit her into a high-fashion, Y2K cyber-pop campaign while preserving her facial likeness perfectly. After an initial safety flag due to restrictive model boundaries, a quick conversational refinement step ("yes retry" to explicitly label as "adult woman" and adjust styling) successfully delivered the campaign asset.

<details>
  <summary><b>📖 View Prompts and Dialogue (Word-for-Word)</b></summary>

  **User Prompt:**
  ```text
  analyze this image and correct promt use gpt 2 image edit and this image prompt
  Don’t alter my facial feature. Create me a wide editorial shot of a girl leaning dramatically across a cluttered floor/desk in a chaotic Y2K cyber-pop room, low front-facing angle with cinematic framing. Moody cool-toned lighting mixed with warm highlights, glossy flash photography feel, dreamy magazine-editorial atmosphere. Long sleek jet-black hair with center part, soft pale glam makeup, subtle blush, glossy gradient red lips, large doll-like eyes with soft eyeliner and lashes. Red fitted tank top and dark mini skirt, colorful manicure, slightly messy dramatic pose with arms stretched forward, intense direct gaze at camera. Surrounding scene filled with scattered random objects, cables, gadgets, accessories, glittery props, and bedroom clutter for a chaotic pop-girl aesthetic. Collage-style edit layered with floating heart gems, cut-out eyes, sticker elements, scrapbook graphics, fake text-message popups, polaroid frames, magazine cutout of the girl, bold typography overlays, hyperpop/K-pop editorial vibe, nostalgic Y2K internet aesthetic, glossy fashion-campaign energy. Scale ratio 4:3
  ```

  **Agent Corrected Prompt & Safety Safeguard:**
  The agent corrected the prompt for GPT image edit using the reference. Upon safety system rejection, the agent prompted:
  ```text
  The generation was rejected by the model safety system.
  I can retry with a safer version if you approve. Suggested changes:
  - Use “adult woman” explicitly
  - Make the outfit less sensitive: red fitted top + dark skirt or pants
  - Remove wording like “girl,” “doll-like,” “mini skirt,” and “leaning dramatically across a floor/desk”
  - Keep the same Y2K cyber-pop editorial style and preserve your facial features

  Reply “yes retry” and I’ll generate with the safer prompt.
  ```

  **User Response:**
  ```text
  yes retry
  ```

  **Final Result:**
  *Generated a 4:3 Y2K cyber-pop editorial image edit using the uploaded photo as identity reference.*
</details>

---

### Case 2: "SALTWAVE" Surfer KAIA (Character Turnaround to Consistent Video)
*   **Original Chat:** [💬 app.flymy.ai/agents/chat/ujf-kffv-wbu](https://app.flymy.ai/agents/chat/ujf-kffv-wbu)
*   **Model Chain:** `GPT Image 2.0` (Character Sheet) → `Seedance 2.0` (Image-to-Video)
*   **The Flow:** Designed a detailed, professional IP character design sheet for a sports/surf brand mascot named KAIA. Then, used that multi-panel character sheet as the first-frame/identity reference for a seamless, continuous 15-second cinematic video of her surfing on rolling waves, executing an aerial maneuver, and preserving 100% style, outfit, hair, and surfboard design consistency.

<details>
  <summary><b>📖 View Prompts and Dialogue (Word-for-Word)</b></summary>

  #### 1️⃣ Character Sheet Prompt (GPT Image 2.0):
  ```text
  professional character design sheet,
  sports lifestyle brand concept art,
  anime-inspired 3D illustration,
  Pixar-level rendering quality,
  cinematic lighting,
  high-end surf brand key visual,
  commercial character turnaround sheet,
  clean studio presentation layout,
  fashion + sports hybrid design,
  beach lifestyle advertising aesthetic,
  ultra detailed character concept board,
  production-ready IP design sheet

  ASPECT RATIO:
  16:9

  PROJECT:
  SALTWAVE – “CHASE THE WAVE”
  CHARACTER IP DESIGN

  SUBJECT:
  female surfer character KAIA,
  beach lifestyle athlete,
  California surf culture inspired,
  freedom, ocean energy, optimism,
  youthful sports brand ambassador,
  surfboard lifestyle identity

  MAIN CHARACTER:
  KAIA,
  age 19,
  athletic slim surfer body,
  sun-kissed skin,
  long brown hair tied in ponytail,
  confident smiling expression,
  free-spirited and energetic personality,
  surfing professional aesthetic,
  modern sports brand model character

  OUTFIT DESIGN:
  surf crop top rash guard (white + navy blue),
  minimal bikini bottom (navy + orange accents),
  sports accessories,
  bracelets and ocean-themed jewelry,
  functional surf gear aesthetic,
  wet sand beach styling,
  brand logo “SALTWAVE” integrated

  PROPS:
  surfboard (white with SALTWAVE branding),
  beach ocean environment,
  sunlight reflections,
  surf leash,
  beach accessories,
  summer ocean lifestyle elements

  LAYOUT STRUCTURE:
  left panel – cinematic hero illustration (beach sunset surf pose, ocean waves, wind motion, dynamic hair movement)
  right panel – clean character sheet layout:
  front view full body,
  side view,
  back view,
  3/4 view,
  expression sheet (happy, confident, playful, wink, smile)
  bottom section:
  equipment breakdown (surfboard, accessories, outfit details),
  color palette swatches,
  brand identity elements,
  design notes and annotations

  VISUAL DETAILS:
  highly detailed anime-realistic hybrid rendering,
  soft cinematic sunlight,
  ocean reflections on skin,
  wind motion in hair and fabric,
  clean white studio background for turnaround views,
  dynamic beach environment for hero shot,
  professional industrial design sheet composition,
  fashion brand character presentation style,
  sharp linework + soft rendering mix,
  ultra clean layout hierarchy

  COLOR PALETTE:
  ocean blue,
  sand beige,
  sunset orange,
  coral pink,
  white foam,
  deep navy,
  warm skin tones

  CAMERA:
  hero shot wide angle beach composition,
  studio orthographic character turnaround views,
  front/side/back/profile consistency,
  soft depth of field for hero panel,
  clean flat lighting for design sheet section

  MOOD:
  freedom,
  youthful energy,
  ocean lifestyle,
  optimistic,
  adventurous,
  sunlight warmth,
  sport brand identity

  LAYOUT:
  professional IP character bible sheet,
  clean white background grid system,
  branding panel on left,
  character turnaround on right,
  detail close-ups bottom right,
  equipment section bottom center,
  color palette swatches included,
  presentation board style for animation/game/sports brand pitch

  QUALITY:
  masterpiece,
  ultra detailed,
  8k,
  production concept art,
  AAA game character design sheet,
  professional brand IP presentation,
  cinematic illustration quality
  ```

  #### 2️⃣ Video Prompt (Seedance 2.0):
  ```text
  Use the provided character sheet as the strict reference for identity, hairstyle, facial features, outfit, accessories, body proportions, color palette, and surfboard design.

  Preserve her exact anime appearance:
  * young female surfer
  * warm tan skin
  * large expressive blue eyes
  * long dark brown-black ponytail
  * athletic slim surfer physique
  * cropped navy-and-white rash guard
  * matching bikini bottoms
  * bracelets, necklace, hair accessories
  * identical surfboard design from the character sheet

  Do not redesign, replace, or alter the character. Maintain full visual consistency throughout the entire video.

  STYLE:
  High-end Japanese anime film quality, cinematic anime action, Makoto Shinkai-level environmental lighting, premium modern anime rendering, detailed water simulation, dynamic hair physics, beautiful sunlight reflections, vibrant ocean colors, subtle anime motion blur, dramatic camera choreography.

  SETTING:
  Open ocean during bright sunny daytime.
  Deep blue water, powerful rolling waves, sparkling sunlight reflections, sea spray, drifting mist, glowing highlights on the water surface, energetic tropical atmosphere.

  SHOT FORMAT:
  One uninterrupted continuous 15-second shot.
  No cuts.
  No hidden cuts.
  No transitions.
  No montage.
  Everything happens in a single seamless camera movement.

  OPENING SHOT:
  The video begins with her already surfing.
  The camera starts very close in front of her upper body and face.
  Her ponytail flows in the ocean wind.
  Small water droplets sparkle around her.
  She maintains a calm, confident, fearless expression while balancing naturally on the surfboard.
  The wave moves dynamically beneath her feet.

  CAMERA MOVEMENT:
  The camera smoothly circles around her body from the front to the rear in one continuous motion.
  Once the camera reaches behind her, it drops to surfboard height and remains low for the rest of the video.
  From that point onward, the camera stays extremely close behind the surfboard, slightly offset near the tail and rail, skimming just above the water surface.
  Never rise to a high angle.
  Always maintain the feeling of chasing the surfboard from behind at wave level.

  ACTION FLOW:
  After the camera settles behind her, she lowers into a deep surfing stance and accelerates rapidly across the wave.
  She leans forward aggressively while maintaining elegant athletic balance.
  One hand reaches down and lightly skims the water surface.
  Water spray bursts backward toward the camera lens.
  The surfboard carves sharply through the wave while the camera remains tightly locked behind it.
  As speed increases, she approaches a larger wave section and launches into a stylish professional aerial maneuver.
  The entire jump remains within the same uninterrupted shot.
  As she leaves the wave, time shifts into dramatic anime-style slow motion.
  The camera remains low and close beneath the action, following the board from behind.
  Floating water droplets sparkle in the sunlight.
  Her ponytail and clothing flutter dynamically.
  While airborne, she rotates her upper body toward the camera, briefly making eye contact.
  She grabs the surfboard with one hand and strikes an elegant, confident anime hero pose.
  The surfboard remains clearly visible throughout the maneuver.
  She then rotates naturally back into position and lands cleanly on the wave.
  A huge burst of water spray explodes around the board upon impact.
  The camera stays low behind the surfboard and follows the landing closely.

  FINAL MOMENT:
  She immediately accelerates again.
  Still viewed from the same low trailing surfboard-level perspective, she charges toward larger waves ahead.
  Sunlight flashes across the ocean surface.
  Sea spray splashes across the lens.
  The wave face rises dramatically in front of her.
  The video ends while she is still surfing at full speed in the same continuous shot.

  No text.
  No subtitles.
  No logos.
  No watermark.
  Anime cinematic masterpiece.
  Ultra-consistent character identity.
  High-quality Japanese animation.
  Character consistency is the highest priority. Maintain the exact character-sheet appearance in every frame. Never change face shape, eye color, hairstyle, outfit, accessories, body proportions, or surfboard design
  ```
</details>

---

### Case 3: Broom-Flight FPV Flight Path (Image Annotation to Motion Tracking)
*   **Original Chat:** [💬 app.flymy.ai/agents/chat/aoj-ggzo-wnb](https://app.flymy.ai/agents/chat/aoj-ggzo-wnb)
*   **Model Chain:** `GPT Image 2.0` (Annotated Image) → `Seedance 2.0` (Reference-to-Video)
*   **The Flow:** Generated a wide, highly-detailed dusk establishing shot of a fantasy castle featuring a custom-overlaid red painted annotation line representing a broom flight path. Then, we used Seedance 2.0's reference-to-video tracking to translate that visual red flight path into a highly dynamic, 10-second FPV first-person video that followed the path exactly, flying past towers, diving under viaduct arches, and skimming across a dark lake.

<details>
  <summary><b>📖 View Prompts and Dialogue (Word-for-Word)</b></summary>

  #### 1️⃣ Castle and Flight Path Prompt (GPT Image 2.0):
  ```text
  Ultra-wide photorealistic aerial establishing shot of an entire fantasy wizarding castle landscape at dusk — a sprawling stone castle with many towers and turrets on a hillside, a magical sports pitch with tall ring-shaped golden goal hoops set on the grounds to one side, a great multi-arch stone viaduct bridge spanning a deep ravine, a large dark lake below, pine forest and jagged mountains beyond. Tiny broom-riders are airborne over the distant pitch, and a faint golden glint (a small flying golden orb) hovers near a far tower. Lanterns and lit windows glow warm across the castle. Shot like a sweeping large-scale fantasy aerial, virtual 18mm wide lens, deep focus, atmospheric haze giving real distance and scale.

  Lighting: low warm dusk sun from the horizon as the dominant source, cool blue shadow filling the ravine and lake, warm window and lantern glow on the castle stone. Color grade: warm amber highlights against deep cool dusk blues, grand and cinematic, clean deep shadows, fine film grain. Ultra-photorealistic textures — weathered stone, slate roofs, water, forest canopy — large-scale fantasy realism, no AI gloss.

  Overlay a single bold red painted line, roughly 8px thick, as a broom flight-path annotation spanning the whole landscape: starting at the sports pitch in the lower corner, climbing up over the goal hoops and stand roofs, swooping down toward the castle and along its battlements past a tall tower, diving down under the arch of the stone viaduct bridge, leveling out and skimming low straight across the lake, then curving up around a far tower to the tiny golden glint, ending with a small red arrowhead at the orb where the line kicks sharply upward. One continuous line with clearly readable climb, swoop, under-bridge dip, lake skim, and spiral-up
  ```

  #### 2️⃣ Reference-to-Video Motion Tracking Prompt (Seedance 2.0):
  ```text
  First-person FPV camera mounted on a flying broomstick, just behind the rider. The rider's cloak and one gripping hand stay visible in the lower frame for the entire shot. Ultra-high-speed single continuous take. Follow the drawn flight path exactly, with no deviation, skipped beats, or simplification. (Any red line, arrows, or path markings are flight-path reference only and must be fully erased from the final footage.)

  The broom launches off the sports pitch and climbs up over the ring-shaped goal hoops and the stand roofs, a golden orb glinting far ahead. It swoops down toward the castle, skimming along the battlements and banking past a tall tower. It dives and threads under the arch of a great stone viaduct bridge, the underside rushing overhead. It levels out and skims low straight across the lake, water spraying just beneath the broom. Finally it chases the orb up and around a far castle tower, and the rider's hand reaches into frame and snatches the golden orb from the air as the broom pulls up sharply and rises into the dusk sky.

  Carry the rush of the climb, the stomach-drop of the swoop, the tight whoosh under the bridge, the spray off the lake, and the triumphant spiral up at the end. Wind, lantern light, lake mist and a golden glint streak past the lens. Ultra-photorealistic textures, vast landscape scale, smooth flowing motion, strong sense of speed, continuous coherent space. No facial distortion, no text, no watermarks.
  ```
</details>

---

## 🛠️ Adding a New Case

To add a new visual case to our landing page showcase, follow this 4-step workflow:

1.  **Extract Chat Metadata:** Copy the public agent chat link from [app.flymy.ai](https://app.flymy.ai) and extract the exact model prompts, negative prompts, and configurations.
2.  **Compress Video/Image Assets:** Keep the repository clean. Compress your video assets into **720p H.264 (CRF 30–34, under 2MB)** before publishing:
    ```bash
    ffmpeg -i input.mp4 -vcodec libx264 -crf 32 -preset slow -acodec copy output.mp4
    ```
3.  **Upload to FlyMy.AI CDN:** Upload the media file using your API key:
    ```bash
    curl -X POST https://backend.flymy.ai/api/v1/agents/agent-file-chat-upload/ \
      -H "X-API-Key: YOUR_API_KEY" \
      -F "file=@output.mp4" \
      -F "external_id=your-uuid-here"
    ```
4.  **Update the Showcase Database:** Add the metadata and CDN links to `demos/media-cases/data/cases.json`, and run the build script.
